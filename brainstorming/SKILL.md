---
name: brainstorming
description: "Use when the user asks to brainstorm or 拷问我 ideas."
version: 1.0.0
author: Hermes Agent
license: MIT
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [brainstorm, ideation, concept-design, game-jam, market-evidence]
    category: creative
    related_skills: [research, grounded-citations]
---

# Brainstorming / 拷问我 Sessions

How to run ideation with this user: ground in their own materials, answer theory
questions directly, put market evidence before any concept, then interrogate with
a structured question round instead of handing over a plan.

## When to Use

- 头脑风暴 / "拷问我" / "从头开始设计" / 选题 / "看看如何开发" — concept work where
  the user wants to be questioned, not briefed.
- Not for: pure fact lookups (use `research`), or writing the deliverable itself
  (use `grounded-citations` for anything citing outside facts).

## Procedure

① **Ground before you ask anything.** Collect the user's own material first:
`session_search` for prior discussions on the topic, local notes
(`~/Documents/notes` and similar), profile facts. Every question in the first
round must reference something real from their experience or artifacts —
generic icebreakers waste the round.

② **Answer embedded sub-questions first.** Mid-brainstorm the user often fires
a factual/theoretical question to calibrate shared vocabulary ("is X an example
of Y?"). Answer it directly — retrieve first if it is a fact — then continue.
Deferring or sidestepping it derails everything built on that vocabulary.

Two sub-question classes get a fixed shape rather than an ad-hoc paragraph:
- **Capability / feasibility ("can I build X with tool Y", "is a 3D version
  realistic in the time left")** → three layers, checked in order: **规则层**
  (official rules and submission channels: what is permitted), **工具层**
  (official docs: what the tool actually exposes), **实测层** (community
  devlogs and the platform's own weekly 避坑 columns: what survives contact).
  Close with a 档位 table of probabilities per route, explicitly labelled
  **我的判断，不是市场数据**, then name the binding constraint — it is almost
  always schedule, never the rules. Full method in
  `references/tool-and-jam-feasibility.md`.
- **"Tell me about game Z"** → full depth: the evidence table,
  platform-by-platform availability, hard numbers. Thin answers read as stalling.

③ **Evidence before concept.** For "does anything like this exist / can this
run", search BEFORE proposing or critiquing: bilingual queries (中文平台词 +
English), covering every platform they care about (for games: Steam AND
TapTap). Deliver a comparison table with hard data — ratings, sales/peak
counts, team size/engine where relevant — each row linked. Downgrade any number
you cannot source to 待核实 instead of asserting it (`grounded-citations`
owns the citation mechanics). Only after the table do you propose.

For a **contest entry**, add a second evidence pass: search the organizer's own
forum for what the other entrants are already building. A crowded track vs an
empty niche is a design input, not trivia — and an empty niche is a signal to
weigh, not a mandate, since nobody may have chosen it because it does not play
well. Forum pages are usually bot-blocked to a direct fetch, so the result is a
search-engine-indexed **sample**: label it as a sample, never as a census; the
category mix is the finding, not the count.

Source map, mobile-availability checks, and how to read sales-vs-CCU numbers
live in `references/game-market-evidence.md`.

④ **拷问我 round: 5–6 sharp questions, each with a one-line "why I ask".**

*Preamble — decompose the reference work first.* If they named an existing
work to borrow from ("借 X 的进化/涌现/手感"), split it into components **before**
writing the round, and mark each 可借 / 不可借 with its cost: the mechanic
skeleton is usually borrowable, the engine-level cost that is the original's
护城河 (physics fidelity, content volume, team size) is not. Deliver the result
as a boundary sentence they can reuse as a pitch — "它做的是 A 层的 X，你做的是
B 层的 X" — and state what the borrowed element must additionally satisfy to
count as the jam's theme (a borrowed system counts only if its direction is
produced by unscripted interaction, not by the player pressing the button that
names the outcome).

Open-ended, no option lists — they answer narratively. Cover:
1. Which layer/dimension the core mechanic lives on — name the alternatives
   and their cost差 so the choice is real.
2. State the entire ruleset in ≤5 sentences. If they cannot, the concept is
   not thought through — that is where you start cutting.
3. Where the theme's authenticity comes from in THEIR real life (their own
   logs/experiences, not your invention).
4. What they would sacrifice — the systems they love most.
5. The moment players will screenshot or retell — the shareable event.
6. Schedule reality check — days remaining vs their actual skill level.

⑤ **Synthesize from their answers**: 2–3 concept drafts or a GDD skeleton,
each one paragraph plus what it costs in scope, mapped to their standing
constraints (scope red lines, submission/platform requirements).

Two checks come **before** you draft anything:

- **Resolve the contradictions in the answers first.** The answer round's real
  output is where their choices conflict with each other or with their own
  written material — they name a main carrier, then admit its cost is the thing
  they underestimated; they set a population floor their own headline scenarios
  can't reach. Name each conflict, force one decision on it, and put whatever
  stays open back in front of them as the next questions. Drafting over a
  contradiction ships it into the document, where it becomes invisible.
- **Recompute the remaining-time budget from today's date plus the stated
  deadline** before pricing any plan. A "N days left" figure carried over from
  an earlier message is a snapshot that silently goes stale, and every hour
  estimate built on it is wrong.

When the concept needs an outside yardstick rather than another opinion from
you (is this actually emergent, is anything too simple), use
`references/game-design-frameworks.md` — Schell's lenses plus how to pull the
list from the source.

## Pitfalls

- **Never force a link between their idea and a theme/trend.** If they
  challenge a connection, concede it is weak in the same reply and rebuild the
  link from the actual mechanism or drop it — defending a weak connection
  costs the session's credibility and gets the whole analysis re-opened.
- **"从头开始，不要再使用之前的内容" is a hard reset.** Discard all prior
  candidates, framing, and priority pools for the rest of the session; do not
  quietly reintroduce them in later rounds.
- **Concepts they explicitly rejected stay rejected.** New proposals must
  come from the current answers, not from reviving shelved ones.
- **A theory question is design input, not a detour.** "Is X really Y?" is
  usually them testing the concept's foundation — a hedged or evasive answer
  propagates into every later decision, so settle it first and plainly.
- **Do not propose on an unverified market claim.** If step ③ has not run,
  label what is assumed; market facts get cited or marked, never asserted.
- **Never let a round evaporate.** When the user answers a sub-question instead
  of the pending round, that round is still pending: re-number **all** pending
  questions in one message, one entry per question keeping its one-line "why",
  and append only the genuinely new questions, each labeled as an add-on.
  Re-asking the same questions in fresh prose doubles the answer load and
  invites the user to skip the originals. If the sub-question changed an early
  one's premises, say which and re-ask that one; do not silently rewrite it.
- **Deliver sub-question answers at full depth.** A "tell me about X" mid-brainstorm
  is a calibration request, not small talk — it wants the same evidence table,
  platform-by-platform availability, and hard numbers the main analysis gets
  (see the two fixed shapes in step ②). Answering it thinly reads as stalling and
  undermines the interrogation that follows.
- **"It's not fun" is a constraint problem before it is a theme problem.** When
  they challenge a concept's value, name the missing constraint (a goal,
  scarcity, feedback, something the player actually controls) and price the
  cheapest fix *before* proposing a re-theme — swapping the theme discards the
  only material that came from their own life, which step ① and question 3 both
  depend on.
