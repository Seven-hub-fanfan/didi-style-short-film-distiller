# didi-style-short-film-distiller

> 基于对 B 站 UP 主 [**DiDi_OK**](https://space.bilibili.com/412615990) 14 部 AI 影像作品的深度蒸馏，产出一套可复用的「日常名词 + 宇宙级权限」AI 短片高概念创作方法论，以 [Agent Skill](https://www.anthropic.com/news/agent-skills)（`SKILL.md` 格式）形式打包。

## 这是什么

一个即插即用的 Agent Skill 包，把 DiDi_OK 累计约 5259 万播放的 14 部作品（代表作《牌子》2122 万、《垃圾站》1082 万、《箭头》780 万）实证有效的创作方法沉淀成可让 AI 助手直接调用的工程化文本。

它不是一份阅读材料，而是一个「让 AI 陪你做 DiDi_OK 风格 AI 短片」的脚手架：

| 你带着这些需求进来 | Skill 会走这条流程 |
|---|---|
| 「帮我想一个 AI 短片选题」 | 流程 A：按概念公式产 3–5 个候选，每个附自评分 |
| 「我有一个 idea，帮我扩成完整脚本」 | 流程 B：六拍表格填充 + 反转选型 + 视觉锚点 + 工具组合 |
| 「帮我看看这个脚本会不会爆」 | 流程 C：11 项 checklist 打分 + 三条改写动作 |

## 方法论骨架

- **核心配方一句话**：挑一个最普通的日常名词，授予它宇宙级权限。
- **六拍叙事公式**：权威播报 → 单点验证 → 跨国蒙太奇 → 建制出场 → 金句 → 反转收束。
- **三型结尾反转**：元反转（观众进入系统）/ 温柔反转（宇宙收进小人物愿望）/ 笑点反转（生活化滑稽）。
- **视觉五律**：伪纪录片是母语；1–2 秒快切；一致性靠符号不靠角色；长台词压进静态双人戏；奇观清单收敛。
- **AI 工具组合**：VEO3 / Sora / Runway / Nano Banana 出图 / Suno 配乐，每一拍推荐用法不同。

完整方法论见仓库里的 [`SKILL.md`](./SKILL.md) 与 `references/` 各文档。

## 目录结构

```
didi-style-short-film-distiller/
├── SKILL.md                              # 总纲，触发时加载
└── references/
    ├── concept-formula.md                # 选题公式 + 六项自检 + 常见错误概念改写表
    ├── six-beat-structure.md             # 六拍每拍的目的/做法/陷阱/时长取舍
    ├── ending-twist-patterns.md          # 三型反转判定树 + 混合陷阱
    ├── visual-and-tools.md               # 伪纪录片语法 + AI 工具组合建议
    └── reference-works.md                # 14 部作品逐条拆解 + 按诉求查表
```

`SKILL.md` 使用标准 [Agent Skills](https://www.anthropic.com/news/agent-skills) 前置元数据（`name` + `description`），任何支持 SKILL.md 约定的 Agent 平台都可以直接加载。

## 使用方法

### 方式 A：Codex CLI

```bash
cd ~/.codex/skills
git clone https://github.com/Seven-hub-fanfan/didi-style-short-film-distiller.git
```

之后在 Codex 会话里提到 DiDi_OK、AI 短片、高概念短视频、VEO/Sora/Runway 短片创作等关键词，Skill 会自动被 Codex 加载并作为方法论指导使用。

### 方式 B：Claude Code

```bash
cd ~/.claude/skills
git clone https://github.com/Seven-hub-fanfan/didi-style-short-film-distiller.git
```

Claude Code 会按 SKILL.md 前置元数据的 `description` 字段进行渐进式加载：`description` 常驻上下文，正文和 `references/` 仅在触发时加载。

### 方式 C：手工搬到其他 AI 平台

`SKILL.md` 的正文是纯 Markdown，可以直接贴进 ChatGPT / Gemini / DeepSeek 等平台的 system prompt 或 project 说明里当风格约束使用。`references/` 里的内容按需引用即可。

### 方式 D：当作方法论文档直接阅读

不使用任何 Agent 工具也完全可以。建议阅读顺序：

1. `SKILL.md`（一次通读，15 分钟）
2. 挑对你当前需求最相关的一份 reference（例如你要拍 7 分钟长片就先读 `references/six-beat-structure.md`）
3. 有具体选题时再回到 `references/concept-formula.md` 自检

## 数据与分析口径

- 采样：DiDi_OK 公开投稿中 2025-06 至 2026-09 的 14 部独立视频（15 条链接去重后）。
- 分析方式：浏览器逐条打开 B 站页面 + 下载 MP4 逐镜多模态观看 + 五部长片抽帧拼图二次校验。
- 播放量、点赞数取自 B 站公开 API（`api.bilibili.com/x/web-interface/view`），截至 2026-09-21。
- 详细蒸馏报告（含每部作品分析、母题图谱、传播轨迹）不在此仓库；本仓库只保留可执行的方法论产出物。

## 免责与致敬

- 本 Skill 是**基于公开作品的第三方研究总结**，与 DiDi_OK 官方无任何隶属关系，也未获得其审阅或背书。
- 所有对具体作品的引用均属评论、教学与研究用途。作品版权归 DiDi_OK 所有，作品页面链接请访问 [DiDi_OK 的 B 站主页](https://space.bilibili.com/412615990)。
- 使用本 Skill 产出的作品应清晰标注 AI 生成属性；不得声称与 DiDi_OK 有合作或授权关系。

## License

MIT — 方法论本身可自由使用、修改与再分发；使用时请保留本仓库来源信息。
