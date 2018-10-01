---
layout: default
---


# What is it?

Instabot Trader is a system that allows you to automate executing trades on Bitfinex,
Deribit and Bitmex.

You can use this automatically trade from TradingView alerts, emails, SMS or
from a simple static web page with a button on it. Set up complex orders in
a single click, such as opening a long and setting up a take profit order and
stop loss order at the same time.

You can place limit or market orders, as well scaled orders (even on exchanges
that don't support this directly). You can cancel open orders, set stop loss
and take profit orders, manage position sizing, send yourself SMS alerts when
things happen, post messages to a slack channel and a whole lot more.

In summary, this allows you to automate any trading strategy, or give you access
to setting up complex trades at the click of a button.

## Show me...

This all works by sending Instabot Trader a message. Here are some example
messages to give you a favour...


### Place a limit order

Place a simple limit order to buy 1.5 BTC on Bitfinex on the BTCUSD pair.
The order will be placed $20 below the current price.

```
bitfinex(BTCUSD) {
  limitOrder(side=buy, offset=20, amount=1.5);
}
```

### A simple market buy

Market buy BTC. Use 20% of my total balance for the purchase.

```
bitfinex(BTCUSD) {
  marketOrder(side=buy, amount=20%);
}
```


### A more complex example.

This time we'll open a leveraged long position on Deribit on the BTC-PERPETUAL
contact. When the commands finish we want to be long with 10,000 contracts.
Instabot Trader will buy or sell however many contracts are needed to end up
with 10,000 contracts, so we don't need to know if we were already long, or
even short at the time these commands are executed.

This example also tries to get into the position as cheaply as possible by
taking the following steps...

* First, place a scaled order made up of 30 limit orders spread over a $50
  range, starting just below the current price).
* Next, wait an hour and cancel any of the above orders that have not been
  filled yet.
* Place a market order to reach the final target position size if needed.
  (if all the limit orders were filled, this would do nothing)
* Finally, send an SMS to our phone with details of our current position and PnL.

```
deribit(BTC-PERPETUAL) {
  scaledOrder(from=5, to=55, orderCount=30, position=10000, tag=example);
  wait(1h);
  cancelOrders(tagged, example)
  marketOrder(position=10000);
  account();
}
```


#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://assets-cdn.github.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
