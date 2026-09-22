# The ads file, and what an ad may say

Every word in an ad comes off `squad/business.md`. Nothing here is a benchmark somebody published.

## 1. The ads file

`squad/ads/<date>/ads.md`, written as each step finishes:

```
# Ads · <YYYY-MM-DD>

## THE MARKET
Searched: "<words>" · <country> · ACTIVE · <N> of about <M> ads · <K> pages kept
1. <page name> · "<headline>" · started <date> UTC · <ad_snapshot_url>
   Words pasted: <the words the founder pasted, as pasted>
   What it shows: <the founder's line>
2. ...
3. ...

## THE ADS
### Ad 1 · image 4:5
Cloned from: <page name> · <n> lines · <the moves, in order: a question, the cost, what you get, the ask>
Words: <message>
Headline: <headline>
Prompt: <prompt>
Credits: <n>
File: squad/ads/<date>/ad-1.<ext>
Link: <public result link>
### Ad 2 · image 4:5
...
### Ad 3 · clip 9:16, 5 seconds
...
```

Agent 12 reads this file: the country off `## THE MARKET`, and the words, headline and link of
every ad off `## THE ADS`. It builds every ad with a `File:` line.

## 3. The clone

An ad that runs on 40 pages in the founder's market is the market's own test of what stops a thumb.
So the founder's ad copies its shape and keeps none of its words.

1. Read the pasted words as lines. Name what each line does in 2 to 4 words: a question to the buyer,
   the cost of the problem, what you get, a number, who it is for, the ask. That list, in that order,
   is the shape.
2. Write the founder's ad line for line on that shape, each line doing the same job with the
   founder's words off `squad/business.md`: a question to the buyer comes off THE PROBLEM or a BUYER
   WORDS line turned to "you"; the cost of the problem off THE PROBLEM; what you get off THE PROMISE
   line 1 or WHAT HE GETS; a number off PRICE or WHAT HE PAYS NOW; who it is for off WHO line 1; the
   ask names the booking call.
3. The same number of lines, the length within 10 words, and the headline of the same kind (a
   question stays a question, a number stays a number).
4. `Cloned from:` under the ad: the page name, the line count, the moves in order.

No winner kept: the standing shape, 4 lines: who it is for and the problem in 1 line · what you get ·
the day off THE PROMISE · the ask.

## 2. Banned, in any run

| Claim | Why |
|---|---|
| A published cost per click, per lead or per call | nobody publishes an honest one for a solo founder's offer; the ceiling comes off their own price |
| "An ad running for months is an ad making money" | the Ad Library returns no spend and no results |
| "This ad won" | 1 ads link counts bookings for the whole campaign, never per ad |
| A word of a winner's copy in the founder's ad | the shape is the market's, the words are the founder's; a copied line is someone else's claim |
