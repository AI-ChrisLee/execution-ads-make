# execution-ads-make · Agent 11

This agent is a base. Once you have done it your way, tell your squad "update the agent to do it
like this."

The second of 3 ads agents. It reads what already runs in your market, clones the shape of the 3 ads
that run most, and makes 3 ads with Higgsfield, every word off your offer page.

## Before you start

- Agent 1 has written `squad/business.md`.
- The Meta Ads connector from Agent 10.
- A paid Higgsfield plan. The 3 ads cost about 10 credits, and the agent prints the number it used.

## Install

Installed with the one line on aichrislee.com/free, then quit and reopen Claude Code.

Higgsfield runs through its command line. The first "Make my ads." installs it and opens Higgsfield
in your browser so you sign in once.

## Run it

**"Make my ads."** It searches the Meta Ad Library for live ads in your country that sell what you
sell, drops the pages that sell something else, and shows you the 3 pages that run the most ads. You
open them, paste the words each one says, and type 1 line on what it shows. Then each of your 3 ads
clones 1 of them: the same number of lines, the same moves in the same order, the same kind of
headline, and not 1 of their words. Every word comes off your offer page. It makes 2 images and 1
short vertical clip in your buyer's world and saves everything in `squad/ads/<date>/`, with
`Cloned from:` under each ad.

Next: Agent 12, "Build my ads launch."

## What it never does

It never puts a word, number, customer or promise in an ad that is not on your offer page. It never
copies a word of a winner's copy. It never builds anything in Meta.

The full procedure is `SKILL.md`.
