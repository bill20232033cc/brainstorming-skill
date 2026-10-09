# Tool & jam feasibility checks (step ② sub-question class)

How to answer "can I actually build X with tool Y in the time I have" — the
question that shows up mid-brainstorm once a deadline, a platform and a skill
level collide. Split it into three layers and answer all three in order; each
layer has its own source and its own failure mode.

## Layer 1 — 规则层: what is permitted

Ask the organizer/platform, not the community.

| Fact | Where to look |
|---|---|
| Theme, dates, eligible platforms, upload deadline, prize categories | The event's **official announcement topic page** (TapTap: `taptap.cn/app/<id>/topic?type=official`), plus its 奖项说明 and 答疑帖 sub-topics |
| Engine / dimension / 2D-3D restrictions | The same announcement; if it lists accepted *channels* (PC / Android / H5 / platform-tool games) rather than engines, engines are unrestricted — say so |
| Dual-platform bonus prizes | Awards page: usually requires ticking two upload targets on one game page |
| What the demo must contain to be judged, and any minimum play count | **奖项说明 + 答疑帖**, not the theme announcement | Rubric elements are a concept gate, not feedback to apply later |

Write the answer as "规则允许，所以这是工期问题不是合规问题" — conflating the two
is what makes a schedule debate look like a research task.

Rubric core-loop elements (for example 目标 / 规则 / 挑战 / 反馈, plus a minimum
play count for some prizes) belong to 规则层 as well: a concept that cannot
supply them is dead before scope planning starts, so surface that gap in the
same reply as the feasibility verdict rather than as a later caveat.

Pitfall: the announcement topic page may be bot-blocked to a headless fetch.
Search engines index the announcement text (including its emoji-formatted
sections) — quote from the indexed snippet and link the topic page for the
reader, rather than burning time on anti-bot workarounds.

## Layer 2 — 工具层: what the tool exposes

Official product docs only, and read the pages that carry costs and limits:

- **Product overview** → headline capabilities (does it claim the asset class
  you need, e.g. 3D 模型 / Spine / video).
- **素材与资源 / assets** → accepted formats, per-file size caps, whether AI can
  generate the asset type, whether bundled multi-file assets import whole.
- **运行环境与数据 / runtime** → runtimes the game ships to (browser/WASM
  preview vs native client vs server), save/storage APIs, environment isolation.

Every capability claim gets a doc link in the reply. Official docs state what
is *supported*; they never state how far it can be pushed — that is layer 3.

## Layer 3 — 实测层: what survives contact

Community evidence, in this order:

1. **Platform's own weekly/避坑 columns** — the topics they pick ("如何优化
   2D 渲染", "存档设计与云同步") reveal where the current pain is.
2. **Creator devlogs for the same event** — what tool chain did the people
   already shipping actually use? A devlog naming a mainstream engine is
   evidence the accepted channels are engine-agnostic.
3. **Resource-application / project-ambition posts** — if a project advertises
   itself as the platform's *first* of its kind ("首款 3D 开放世界") with a
   multi-week phased plan, treat that as "no one has done it yet at jam pace".
4. **Individual reviews** ("目前更适合 2D 休闲小游戏") — useful as a tilt, never
   as a verdict; one voice.

**Runtime fragmentation is the recurring trap.** Platforms that preview in a
browser and ship to a native client routinely support an asset or playback
feature on one and not the other (video, for instance, often works in preview
and silently no-ops on device). Before promising a capability, check the same
feature on *both* runtimes and require a fallback.

## Closing: the 档位 table

End with one table — routes down the side, each with a probability band and its
cost — and label the whole table **我的判断，不是市场数据**. Bands are honest
estimates from the three layers; the point is the ordering, not the digits.
Finish with one sentence naming the binding constraint (skills + days, not the
rules), and state the fallback route that still meets the theme.

## Reading a borrowed reference work

When the user wants to borrow a mechanic from an existing title, split it into
components before critiquing: the *mechanic skeleton* (what the system does,
the player's leverage over it) is usually portable; the *implementation mass*
(physics fidelity, asset volume, team size, engine) is the original's moat and
is what you decline. Also check prior art for the specific twist you are
adding — finding none means **没有找到直接先例**, not that none exists; render it
that way.
