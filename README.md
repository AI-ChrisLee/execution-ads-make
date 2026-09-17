# execution-ads-make · Agent 11

This agent is a base. Once you have done it your way, tell your squad "update the agent to do it
like this."

The second of 3 ads agents. It reads what already runs in your market, makes 3 ads with Higgsfield,
and checks every word and every picture against your offer page before any of it goes near Meta.

## Before you start

- Agent 10 has written `squad/ads-money-card.md`.
- The Meta Ads connector from Agent 10.
- A paid Higgsfield plan. The 3 ads cost about 10 credits, and the agent prints the real number
  before it makes anything.

## Install

Installed with the one line on aichrislee.com/free, then quit and reopen Claude Code.

Higgsfield runs through its command line. The first "Make my ads." installs it and opens Higgsfield
in your browser so you sign in once.

## Run it

**"Make my ads."** It searches the Meta Ad Library for live ads in your country that sell what you
sell and shows you the top 3. You open them and type 1 line on each. It writes 3 ads off your offer
page, prints the credit cost, and waits for your yes. Then it makes 2 images and 1 short vertical
clip, runs the claims check on each one, and saves everything in `squad/ads/<date>/`. A failed ad
gets 1 remake; a second fail drops it.

Next: Agent 12, "Build my ads launch."

## What it never does

It never spends a credit without your yes. It never puts a word, number, customer or promise in an
ad that is not on your offer page. It never builds anything in Meta.

The full procedure is `SKILL.md`.
