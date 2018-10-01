---
layout: default
---


# What is it?

Instabot Trader is a system that allows you to execute trades on Bitfinex,
Deribit and Bitmex, that are triggered from anything that can make an HTTP
request.

You can use this automatically trade from TradingView alerts, emails, SMS or
from a simple web page that submits a form to the bot.

You can place simple limit or market order, or more complex scaled orders.
Cancel open orders, manage position sizing, send yourself SMS alerts when things
happen, post messages to a slack channel.

## Show me...

Here are some sample messages to give you a favour (eg, imagine texting the
  following text to the bot)...

```
Place a simple limit order to buy 1.5 BTC on Bitfinex on the BTCUSD pair.
The order will be placed $20 below the current price.

bitfinex(BTCUSD) { limitOrder(side=buy, offset=20, amount=1.5); }

```

```ruby
Market buy BTC. Use 20% of my total balance for the purchase.
bitfinex(BTCUSD) { marketOrder(side=buy, amount=20%); }
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
