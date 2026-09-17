---
name: ads-execution-make
description: Use this when the founder's ads money card exists and they need the ads themselves, or the weekly read called for new ads. They say "Make my ads." It reads what already runs in their market in the Meta Ad Library, makes 2 images and 1 short vertical clip with Higgsfield after a credit line and a yes, checks every word and every picture against squad/business.md, and saves the ads with the claims check in squad/ads/<date>/. It builds nothing in Meta and spends nothing on ads.
---

# Ads Execution Make · Agent 11

1 output: `squad/ads/<date>/`, the 3 ads and `ads.md` with their words, the market read and the
claims check under each ad.

**Your first message on a fresh run** (no `squad/ads/` folder on disk) carries this line, verbatim:
This agent is a base. Once you have done it your way, tell your squad "update the agent to do it
like this."

Every word in an ad comes off `squad/business.md`. **Nothing is generated on Higgsfield before the
cost line and a yes.**

`<date>` is always `YYYY-MM-DD`.

## The line

| The founder says | What comes back |
|---|---|
| "Make my ads." | the market read, 3 ads in `squad/ads/<date>/`, each with its claims check in `ads.md` |

"Make my ads." again picks up a stopped run: the newest `squad/ads/<date>/ads.md` with an ad that has
no `Check:` line continues at the first thing missing. An ad with a `File:` line is never made again,
and anything not yet made gets its own cost line and yes. When the newest folder is finished, a new
run starts a new folder; a finished folder already dated today makes the new one `<date>-2`.

## Read and write

- Reads `squad/ads-money-card.md` (the account), `squad/business.md` (THE SENTENCE, WHO, THE
  PROBLEM, THE PROMISE, PRICE, BUYER WORDS), the Meta Ad Library through the Meta Ads connector, and
  Higgsfield through its command line.
- Writes `squad/ads/<date>/`: `ad-1.<ext>`, `ad-2.<ext>`, `ad-3.mp4`, the clip's 3 check frames, and
  `ads.md`. Nothing else.

## Before the run

1. Open `references/the-account.md` and `references/the-numbers.md`. Any missing: stop and ask for
   the whole folder again.
2. Read `squad/business.md`. No file, or no number on line 1 under `## PRICE`: stop with 1 line,
   "Run Agent 1 first: /the-winning-offer."
3. THE SENTENCE sells credit, a job, housing, or a social issue, election or politics: 1 line,
   "Meta treats this as a special ad category. This agent does not build those." Stop.
4. Read `squad/ads-money-card.md`. Missing: 1 line, "Run Agent 10 first: Set up my ads money." Stop.
5. **The account read.** Call `ads_get_ad_accounts`. No Meta Ads tools loaded: print the connect
   steps from `references/the-account.md` section 1 and stop. Read the card's account and print its
   line only when it stops the run: not both enabled and queryable stops it, with Meta's reasons
   exactly as written.

## "Make my ads."

1. **Higgsfield.** Run `higgsfield account status`. Not installed, not signed in, or no paid plan:
   the steps in `references/the-account.md` section 3, then "type Make my ads. again". Stop.
2. **The country.** Read the country off the 2 lines under `## WHO`. They name none: ask 1 line,
   "Which country do your buyers live in?"
3. **The market read.** 1 call to `ads_library_search`: `search_terms` = 2 to 4 words naming what
   THE SENTENCE sells, `countries` = that country, `ad_active_status` ACTIVE, `limit` 50.
   - Print "N of about M ads" (N returned, M Meta's estimate) and the words searched.
   - Drop every page that does not sell an offer like this one, judged off the page name and the
     headline. The search returns no body text, so a blank headline is judged off the page name
     alone, and a page name that does not name an offer like this one is dropped. Print how many
     pages are kept.
   - Rank the kept pages by how many of the returned ads each one runs, ties by page name. The
     search returns the newest ads first, so a start date says when an ad went up, never how long
     a page has run it. Print the top 3: page name, headline, start date in UTC as the search
     returns it (written <date> UTC), `ad_snapshot_url`.
   - Ask: "Open these 3 and type 1 line on each: what the picture or the video shows." Wait.
   - 0 kept: say so in 1 line and skip the ask.
4. Start `squad/ads/<date>/ads.md` with `## THE MARKET` (`references/the-numbers.md` section 1).
5. **The 3 ads.** Write them into `## THE ADS`, each with its words, headline and prompt:
   - Ad 1 and ad 2: an image, `nano_banana_2`, `--aspect_ratio 4:5`.
   - Ad 3: a clip, `kling3_0`, `--aspect_ratio 9:16 --duration 5 --sound off`.
   - The words and the headline come only from THE SENTENCE, WHO, THE PROBLEM, THE PROMISE, PRICE
     and BUYER WORDS. Words may be cut and turned to "you" and "your". No other noun, number or
     claim is added. The words speak to the buyer as "you" from the first line to the last. The
     headline is 1 sentence that stands on its own and never opens on So, And or But. The
     founder's 3 lines set the kind of shot, never a word or a claim.
   - Prompt rules: `references/the-account.md` section 3.
6. **The cost, first.** Run `higgsfield generate cost` for each of the 3 and print 1 line: "3 ads:
   N credits." Wait for yes. Anything else makes nothing.
7. **Make them.** `higgsfield generate create <model> ... --wait` for each. Download each result
   into `squad/ads/<date>/ad-1.<ext>`, `ad-2.<ext>`, `ad-3.mp4`, the extension off the link. Write
   the credits, the file path and the public result link under each ad. A create that errors with
   no job in `higgsfield generate list` took no credits: run it once more. A second error: print it
   as written and stop.
8. **The claims check.** Open each image, and the clip's 3 frames (`references/the-numbers.md`
   section 2, rule 5). Check every ad, its words and what it shows, against `squad/business.md`
   (`references/the-numbers.md` section 2). Write `pass` or `fail` with the reason under each ad. A
   fail gets its prompt fixed and 1 remake, with its own cost line and yes first. A remake that
   fails too reads `dropped` with its reason and is never built (`references/the-numbers.md`
   section 1).
9. Print the 3 file paths, each ad's words and its check, then "Tell me what any line should say,
   and I'll change it." Last line: "Next: Build my ads launch." Every ad dropped: 1 line instead,
   "No ad passed the check. Type Make my ads. to make 3 new ones."

A changed line is a changed ad: its check runs again before the last line prints.

## A CSV the founder hands it

"Read my claims check from <file>.csv", a CSV in the columns `ad,type,headline,make,credits,check,reason`:
make nothing, spend nothing, and print 1 line per ad (pass, or fail on the first make with its
reason and the remake's result), then the total: passed of made, remakes, credits. Write nothing.
Last line: "Next: Build my ads launch."

## Never

- Generate on Higgsfield before the cost line and a yes.
- Write `squad/business.md`, `squad/sales.md` or `squad/ads-money-card.md`.
- Build anything in Meta. Agent 12 builds, and only the ads that read `pass`.
- Put a word, number or claim in an ad that is not on `squad/business.md`, or copy what the
  founder's 3 lines describe.
- Say an ad running for months is making money. The Ad Library returns no spend and no results.
- Quote a published cost per click, per lead or per call.
- Drive Ads Manager or the Ad Library with a browser tool. The connector is the way Meta built for
  this.
