---
name: execution-ads-make
description: Use this when the founder needs the ads themselves, or the weekly read called for new ads. They say "Make my ads." It reads what already runs in their market in the Meta Ad Library, clones the shape of the 3 ads that run most (their lines, their moves, their shot) with every word off squad/business.md, makes 2 images and 1 short vertical clip with Higgsfield, and saves the ads in squad/ads/<date>/. It builds nothing in Meta and spends nothing on ads.
---

# execution-ads-make · Agent 11

1 output: `squad/ads/<date>/`, the 3 ads and `ads.md` with their words, the market read, and which
winning ad each one clones. An ad here is a copy of a shape that already runs, in the founder's words.

**Your first message on a fresh run** (no `squad/ads/` folder on disk) carries this line, verbatim:
This agent is a base. Once you have done it your way, tell your squad "update the agent to do it
like this."

Every word in an ad comes off `squad/business.md`.

`<date>` is always `YYYY-MM-DD`.

## The line

| The founder says | What comes back |
|---|---|
| "Make my ads." | the market read, 3 ads in `squad/ads/<date>/`, their words in `ads.md` |

"Make my ads." again picks up a stopped run: the newest `squad/ads/<date>/ads.md` with an ad that has
no `File:` line continues at the first thing missing. An ad with a `File:` line is never made again.
When the newest folder is finished, a new run starts a new folder; a finished folder already dated
today makes the new one `<date>-2`.

## Read and write

- Reads `squad/business.md` (THE SENTENCE, WHO, THE PROBLEM, THE PROMISE, PRICE, BUYER WORDS), the
  Meta Ad Library through the Meta Ads connector, and Higgsfield through its command line.
- Writes `squad/ads/<date>/`: `ad-1.<ext>`, `ad-2.<ext>`, `ad-3.mp4`, and `ads.md`. Nothing else.

## Before the run

1. Open `references/the-account.md` and `references/the-numbers.md`. Any missing: stop and ask for
   the whole folder again.
2. Read `squad/business.md`. No file, or no number on line 1 under `## PRICE`: stop with 1 line,
   "Run Agent 1 first: /execution-genesis-offer."
3. THE SENTENCE sells credit, a job, housing, or a social issue, election or politics: 1 line,
   "Meta treats this as a special ad category. This agent does not build those." Stop.
4. **The connector.** No Meta Ads tools loaded: print the connect steps from
   `references/the-account.md` section 1 and stop.

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
   - Ask: "Open these 3. For each one, paste the words it says (the text over the picture and the
     headline), and type 1 line on what the picture or the video shows." Wait. The words are the
     input the clone runs on; the 1 line sets the shot.
   - 0 kept: say so in 1 line, skip the ask, and the 3 ads are written on the standing shape in
     `references/the-numbers.md` section 3.
4. Start `squad/ads/<date>/ads.md` with `## THE MARKET` (`references/the-numbers.md` section 1).
5. **The 3 ads.** Each one clones 1 of the 3 winners: ad 1 the top page's ad, ad 2 the second, ad 3
   the third (fewer than 3 kept: the same winner again, said so). Write them into `## THE ADS`, each
   with its words, headline, prompt and `Cloned from:` line:
   - Ad 1 and ad 2: an image, `nano_banana_2`, `--aspect_ratio 4:5`.
   - Ad 3: a clip, `kling3_0`, `--aspect_ratio 9:16 --duration 5 --sound off`.
   - **The clone** (`references/the-numbers.md` section 3): the same number of lines as the pasted
     words, the same move in each line in the same order (what line 1 does, line 2, the last line),
     the same length within 10 words, and the same kind of headline. Not 1 word, number or name of
     the winner's copy: every word comes only from THE SENTENCE, WHO, THE PROBLEM, THE PROMISE, PRICE
     and BUYER WORDS, cut and turned to "you" and "your". No other noun, number or claim is added.
     The words speak to the buyer as "you" from the first line to the last. The headline is 1
     sentence that stands on its own and never opens on So, And or But.
   - The founder's 1 line on each winner sets the kind of shot for the ad that clones it, in the
     buyer's own world off WHO and THE PROBLEM, never a word or a claim.
   - Prompt rules: `references/the-account.md` section 3.
6. **Make them.** `higgsfield generate create <model> ... --wait` for each. Download each result
   into `squad/ads/<date>/ad-1.<ext>`, `ad-2.<ext>`, `ad-3.mp4`, the extension off the link. Write
   the credits, the file path and the public result link under each ad. A create that errors with
   no job in `higgsfield generate list` took no credits: run it once more. A second error: print it
   as written and stop.
7. Print the 3 file paths, each ad's words and the credits used, then "Tell me what any line should
   say, and I'll change it." Last line: "Next: Build my ads launch."

## Never

- Write `squad/business.md`, `squad/sales.md` or `squad/ads-money-card.md`.
- Build anything in Meta. Agent 12 builds.
- Put a word, number or claim in an ad that is not on `squad/business.md`, copy a word of a
  winner's copy, or copy what the founder's 3 lines describe.
- Say an ad running for months is making money. The Ad Library returns no spend and no results.
- Quote a published cost per click, per lead or per call.
- Drive Ads Manager or the Ad Library with a browser tool. The connector is the way Meta built for
  this.
