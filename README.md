# brainstorming — 头脑风暴 / 拷问我（Hermes Agent Skill）

> Use when the user asks to brainstorm or 拷问我 ideas.

一个用于**概念设计 / GameJam 选题 / 拷问式讨论**的 Hermes Agent 技能。
它不直接给方案，而是先把用户自己的材料落地、把市场证据摆上桌，再用一轮结构化的
问题把对方「拷问」一遍，最后才综合出 2–3 个概念草案。

## 安装

### 方法 A：`hermes skills install`（推荐）

```bash
# 标识符形式
hermes skills install bill20232033cc/brainstorming-skill

# 或直接指向 SKILL.md 的 URL
hermes skills install https://raw.githubusercontent.com/bill20232033cc/brainstorming-skill/main/brainstorming/SKILL.md
```

需要指定分类 / 覆盖名称时：

```bash
hermes skills install <identifier> --category creative --name brainstorming
```

### 方法 B：手动拷贝

```bash
git clone https://github.com/bill20232033cc/brainstorming-skill.git
cp -r brainstorming-skill/brainstorming ~/.hermes/skills/creative/
```

**目录结构必须保持**：`SKILL.md` 在技能根目录，`references/` 是它的子目录。

### 验证

```bash
hermes skills list | grep brainstorming    # Source=local / status=enabled
```

或在任意对话里 `/skills` 查看；已安装的技能会自动变成斜杠命令 → `/brainstorming`。

## 目录结构

```
brainstorming/
├── SKILL.md                                   技能主体（5 步流程 + 陷阱）
└── references/
    ├── game-market-evidence.md                步骤③ 市场取证的源表与「手机版」三类假阳性识别
    └── tool-and-jam-feasibility.md            步骤② 「能不能做出来」的三层判定法（规则/工具/实测）
```

## 流程概览

1. **Ground** — 先收集用户自己的材料（历史会话、本地笔记、个人档案），第一轮问题必须锚在真实材料上
2. **答内嵌子问题** — 中途抛出的事实/理论问题当场查证后直接回答，不拖延
3. **证据先于概念** — 中英双语检索（Steam + TapTap），带硬数据的对比表，来源不明的数字降级为「待核实」
4. **拷问一轮 5–6 个问题**，每个附一行「为什么问这个」，全部开放式
5. **综合** — 从对方的回答里长出 2–3 个概念草案或 GDD 骨架，每个附范围成本与砍单预案

## 主要陷阱

- 不要硬把用户的想法和某个趋势绑定；被质疑就连着承认并重建或放弃
- 「从头开始」是硬重置，后续不得悄悄复活被否掉的方案
- 理论型提问是设计输入，不是岔路——先给确定答案再继续
- 未完成步骤③ 就不得基于未核实的市场结论提方案

## License

MIT
