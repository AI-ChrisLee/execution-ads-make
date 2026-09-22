# The accounts: Meta Ads and Higgsfield

Every call this agent makes. Read the live tool list every run. When a name here and the live list
disagree, the live list wins and the founder hears 1 line about it.

## 1. Connect Meta Ads, once

The official Meta Ads connector is a custom connector, added in the Claude app:

> Claude, Customize, Connectors, the + button, Add custom connector. Name it Meta Ads, URL
> `https://mcp.facebook.com/ads`. Sign in with Facebook and pick the business that owns the ad
> account.

Then quit Claude Code and open it again in the same folder. Claude Code signed in with the same
Claude account picks up the connector. No developer app, no key to paste.

## 2. The market read

Send the same `client_conversation_id` on every Meta call in a run.

`ads_library_search` returns, per ad, the page name, the headline, the start date in UTC and the
`ad_snapshot_url`, plus Meta's estimate of the total. It returns no body text, no picture, no spend
and no results. The search matches words, not offers, so a page that does not sell an offer like
the founder's is dropped before ranking.

## 3. Higgsfield, through its CLI

A paid Higgsfield plan is required. Unlimited generations on a plan do not cover the CLI: every
ad here spends credits.

**Check:** `higgsfield account status` prints the plan and the credits.

**Not installed:** run `npm i -g @higgsfield/cli`. No `npm`: 1 line, install Node from nodejs.org
first. **Not signed in:** run `higgsfield auth login` yourself. It opens the browser; tell the
founder to sign in there, then "type Make my ads. again".

**Make:**

```
higgsfield generate create nano_banana_2 --prompt "<prompt>" --aspect_ratio 4:5 --wait
higgsfield generate create kling3_0 --prompt "<prompt>" --aspect_ratio 9:16 --duration 5 --sound off --wait
```

`--wait` prints the result link. Download it with `curl -L -o squad/ads/<date>/ad-N.<ext> "<link>"`.
Result links are public with no sign-in (image links made in July still opened in September), so
the same link goes to Meta when Agent 12 builds.

**Prompt rules:**

- 30 to 100 words. The subject first, then the setting, the framing, the light.
- The look of a phone photo, in words: natural daylight, handheld, slightly off-center, an
  ordinary everyday look. Never the words "shot on a phone", which draw a status bar. Every image
  prompt ends "a full-bleed photo, no status bar, no screen interface, no borders".
- Never a phone of any kind, a till, a keypad, a screen or any device with buttons in the frame,
  because the model letters every key and every display. Show the moment around it instead: the
  empty chair, the desk after hours, the waiting room.
- People seen from behind, from the side or small in the frame, so no face reads. Never write
  blur or "no faces in focus" into a prompt: the model paints a censor blur over the faces.
  Never 2 people facing each other across a counter or table, because 1 of them always faces the
  lens.
- Nothing with writing on it anywhere in the frame, because the model scrambles every letter it
  draws. An image prompt with a desk, counter or shelf in it says "a bare counter with no computer,
  no phone, no papers, no signs". The clip prompt never names a thing to leave out, because
  kling3_0 draws every object its prompt names, "no" or not. It names only what is there ("1 lamp
  alone on a bare white counter") and never says front desk or reception.
- 1 room at its quiet hour, with a plain wall, closed blinds or a closed door behind the subject. A
  window with open blinds is written as showing only sky and trees, because a street through the
  glass brings a shop sign with letters on it. Never a busy hour, a hallway, a doorway, a pillar or
  a second room in view, because the model fills every space it can see into with screens, phones
  and signs.
- The buyer's own world off WHO and THE PROBLEM, shown as it is.
- Never text, never a logo, never a face turned to the camera, never a before and after.
- The clip is 1 moment, 5 seconds, no sound, in the same 1 room at its quiet hour. The camera
  holds still inside the room, or pushes in slowly from inside it, and never follows anyone out of
  it.
