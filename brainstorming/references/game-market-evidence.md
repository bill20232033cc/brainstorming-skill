# Game market evidence (for step ③)

How to get hard, linkable numbers for a game comparison table, and how to tell a
real mobile version from SEO noise. Every figure goes into the table linked, or
downgraded to 待核实 / 估算 — never asserted bare.

## Source map (query in this order)

| Fact | Source | Notes |
|---|---|---|
| Review count, positive %, tags, sysreq, supported OS | `web_extract` the Steam store page | Store page gives "Recent Reviews" and English-region reviews separately; cite the region you quote. |
| Dev / publisher / engine / appid / release date | `steamdb.info/app/<id>/` | Extracts cleanly without login; a wrong appid returns a different game's page — check the title matches. |
| All-time peak + monthly concurrent players | `steamcharts.com/app/<id>` | Cross-check against SteamRaw/SteamPeaks; two agreeing sources = safe to state. |
| Copies sold / gross revenue | `steamrev.com`, `thegamecensus.com`, `indielist.games` | **Third-party estimates only** — always render with a 估算/⚠️ tag and an as-of date. |
| Console SKUs, price, release date, eShop rating | Publisher newsroom + the platform store page (nintendo.com, playstation.com, xbox.com) | Publisher blog often states price and date for *all* consoles in one paragraph. |
| Dev team size, engine, development history | Wikipedia + publisher/press interviews | Wikipedia release dates frequently disagree with the store/SteamDB date — trust the store and say so. |
| Community mechanics depth (behaviors, life cycle, systems) | Game's Fandom wiki / Steam guide | Good for describing *how* a game works; not a source for sales or dates. |

Bilingual every query: 中文平台词（评测/玩法/手机版/售价）+ English keywords,
because Chinese-language coverage of niche indie games is thin and English
coverage never surfaces 平台 availability.

## Mobile availability — three impostors to rule out

Before writing "no mobile version", check in this order:
1. **App Store / Google Play**: search the exact English title. No official
   listing = no mobile version.
2. **TapTap page ≠ mobile version.** TapTap hosts pages for PC/console games;
   a `下载量 0` entry with screenshots of another platform is a catalog page.
3. **SEO content farms.** Queries like `<game> mobile / play on Android` surface
   "how to play on your phone" articles whose only answer is *stream it via
   Steam Link / GeForce NOW*. Treat "you can't install it, only stream it" as a
   confirmation of absence, not as a mobile version.
Only claim availability from the publisher's own site badges or the store page.

## Reading the numbers before you cite them

- **High sales + low peak CCU** = long-tail single-player title: it sells copies,
  it does not hold an audience. Say what that implies for the reader's own goal
  (a jam submission is judged on a screenshot-worthy moment, not on DAU) instead
  of leaving the two numbers sitting next to each other.
- **A platform the competitor cannot reach is an asset.** When a rival's engine
  (heavy 3D physics, large active-unit caps) excludes it from your target store,
  state that explicitly — it turns "we are smaller" into "we are uncontested here".
- **Engine/team size are scope evidence.** Use them to anchor schedule realism in
  the round's reality-check question, not as trivia.

## Same-event entrant survey (contest concepts)

For a contest entry, the relevant "does this exist" question is partly *who
else is entering the same event right now*. Search the organizer's own forum
for entrants' devlogs before proposing: it tells you which tracks are crowded
(three teams on the same puzzle gimmick) and which niche is empty. An empty
niche is a signal to weigh, not a mandate — nobody may have chosen it because
it does not play well.

Forum pages are usually bot-blocked to a direct fetch, so what you get back is
a **search-engine-indexed sample**. Label it as a sample, never as a census;
the category mix is the finding, the count is not.
