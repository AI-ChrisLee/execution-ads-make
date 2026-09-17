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
Check: pass | fail · <reason> | dropped · <reason>
### Ad 2 · image 4:5
...
### Ad 3 · clip 9:16, 5 seconds
...
```

A failed ad gets 1 remake. Its Prompt, Credits, File, Link and Check lines are written over, with 1
line kept above them: `First make: fail · <reason> · <n> credits`. A remake that fails too reads
`dropped` and is never built.

Agent 12 reads this file: the country off `## THE MARKET`, and the words, headline, link and check
of every ad off `## THE ADS`. It builds only the ads that read `pass`, and only when every ad reads
`pass` or `dropped`.

## 2. The claims check, per ad

Each ad passes only when all 5 hold. A fail names the line that broke and why.

1. Every noun, number and claim traces to THE SENTENCE, WHO, THE PROBLEM, THE PROMISE, PRICE or
   BUYER WORDS. Cut words, and words turned to "you" and "your", pass.
2. A price, when the ad shows one, is line 1 under PRICE, word for word.
3. Nothing promised past THE PROMISE. Never money the buyer will make, never a guarantee.
4. No customer, review, result, count or date that is not on `squad/business.md`. A buyer-words line
   is never dressed as a review. No moment the founder never had, and 1 quote is never written as
   many people saying it ("owners tell me" off 1 line fails).
5. The image shows no text, no logo, no face turned to the camera, no blurred or pixelated face,
   no status bar or app screen, and copies nothing the founder's 3 lines describe from the 3
   market ads. Zoom into every part of the image before you write pass. Any letter shape in focus
   fails, however small: a sticky note, a paper, a magazine cover, a display. Light shapes in the
   far background pass only when no letter, number or logo shape can be made out at full zoom. A
   sign across the street with block letters or a logo on it fails, however soft. The clip is
   checked the same way on 3 frames, pulled with
   `ffmpeg -ss <t> -i squad/ads/<date>/ad-3.mp4 -frames:v 1 squad/ads/<date>/ad-3-<t>.png` at 0.2,
   2.5 and 4.8 seconds. Any frame that fails fails the clip. Its path is printed so the founder can
   watch it too.

## 3. Banned, in any run

| Claim | Why |
|---|---|
| A published cost per click, per lead or per call | nobody publishes an honest one for a solo founder's offer; the ceiling comes off their own price |
| "An ad running for months is an ad making money" | the Ad Library returns no spend and no results |
| "This ad won" | 1 ads link counts bookings for the whole campaign, never per ad |
