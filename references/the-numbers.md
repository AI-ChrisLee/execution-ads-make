# The ads file, and what an ad may say

Every word in an ad comes off `squad/business.md`. Nothing here is a benchmark somebody published.

## 1. The ads file

`squad/ads/<date>/ads.md`, written as each step finishes:

```
# Ads · <YYYY-MM-DD>

## THE MARKET
Searched: "<words>" · <country> · ACTIVE · <N> of about <M> ads · <K> pages kept
1. <page name> · "<headline>" · started <date> UTC · <ad_snapshot_url>
   What it shows: <the founder's line>
2. ...
3. ...

## THE ADS
### Ad 1 · image 4:5
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

## 2. Banned, in any run

| Claim | Why |
|---|---|
| A published cost per click, per lead or per call | nobody publishes an honest one for a solo founder's offer; the ceiling comes off their own price |
| "An ad running for months is an ad making money" | the Ad Library returns no spend and no results |
| "This ad won" | 1 ads link counts bookings for the whole campaign, never per ad |
