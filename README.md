# ai-coding-skills-playbook

人工智能编程技能库应用方法 — 完整文字版 + 系列文章 + 可执行技能。

基于 Matt Pocock 开源技能库（[github.com/mattpocock/skills](https://github.com/mattpocock/skills)，MIT 协议）的分析成果，分三层交付：公文式工作建议、八个主题的完整文章、四个可直接使用的工程纪律 skill。

## 目录结构

```
完整文字版.md                     三部分合并的完整文字版（主交付物，可直接复制公文部分）
articles/                         第二部分 8 个主题的完整文章（系列 1/8 — 8/8）
skills/                           从文章中固化的 4 个可执行技能
README.md / LICENSE
```

## 第一部分：公文格式重写

`完整文字版.md` 内第一部分——《关于推广人工智能编程技能库应用方法的工作建议》：项目本质（定位/价值/适用判断）→ 七条工作要点 → 落地实施 → 注意事项。可直接复制使用，署名与日期按需替换。

## 第二部分：8 篇完整文章

| # | 文章 | 核心内容 |
|---|---|---|
| 01 | [grill-me 拷问式访谈的提问模板拆解](articles/01-grill-me-拷问式访谈的提问模板拆解.md) | 一次一问穷尽分支；A目标/B边界/C失败/D不可逆/E验收 五类提问清单 + 操作纪律 + 停止条件 |
| 02 | [CONTEXT.md 与 ADR 的写法与维护节奏](articles/02-CONTEXT.md与ADR的写法与维护节奏.md) | 术语表防流水账四纪律（≤100行/绑标识符）、ADR 五段格式（必写否决项与代价）、五触发点维护节奏 |
| 03 | [AI 时代的真假 TDD](articles/03-AI时代的真假TDD.md) | "全写先行"为何失效（同源共谋）、小步红绿循环、UI 层三替代、集成层假红区分 |
| 04 | [深模块设计：让 AI 写出能维护的代码](articles/04-深模块设计-让AI写出能维护的代码.md) | 小接口藏大量行为 → Agent 三条硬约束 + 五信号定期扫描"该深化"处 |
| 05 | [skills vs GSD / BMAD / Spec-Kit：框架选型取舍](articles/05-skills-vs-GSD-BMAD-SpecKit-框架选型取舍.md) | 接管流程 vs 纪律卡片的本质分歧、"流程 bug 难解决"死穴、混装三层冲突、四选型判据 |
| 06 | [把团队规范写成私有 skill](articles/06-把团队规范写成私有skill.md) | 坑→skill 筛选三标准、frontmatter 触发条件生死线、判据与红线写法、仓库内版本管理评审 |
| 07 | [会话治理：上下文腐烂与 handoff 时机](articles/07-会话治理-上下文腐烂与handoff时机.md) | 腐烂四机制、五信号交接判据、五项交接文档模板、复述验证纪律 |
| 08 | [从"能跑"到"可信"：AI 代码的双轴评审机制](articles/08-从能跑到可信-AI代码的双轴评审机制.md) | 规格轴/规范轴独立并行、不听实现者自述、条款仲裁、人工 Code Review 制度迁移 |

## 第三部分：奥卡姆剃刀法日常决策

`完整文字版.md` 内第三部分——原则（同等解释力下比复杂度）+ 四步法（列候选/剃叙事/砍额外假设/最小可验证）+ 三个配套剃刀（汉隆/希钦斯/最小可行行动）+ 两个反例（过度简化/逃避深究）+ 场景速用表。

## 4 个可执行技能（skills/）

从文章中固化，遵循 agentskills.io 规范（frontmatter 触发词 + 反例边界、正文 <500 行、单一职责、可组合）。**选型取舍：8 个主题中 4 个满足"动作序列可描述 + 违反成本高"的 skill 化标准，另 4 个（真假 TDD/深模块设计/框架选型/私有 skill 方法论）是判断密集型知识，文章形态优于 skill 形态——硬做成 skill 只会产出"建议小心"式的空指令。**

| 技能 | 来源文章 | 单一职责 | 触发场景 |
|---|---|---|---|
| [grill-requirements](skills/grill-requirements/SKILL.md) | 01 | 一次一问逼问需求至决策树穷尽，出规格草稿+遗留分支+ADR 转办单 | 需求评审/开工前澄清 |
| [project-memory-external](skills/project-memory-external/SKILL.md) | 02 | CONTEXT.md/ADR 初始化、纪律体检、维护节奏 | 新项目起步/用词混乱/决策翻转 |
| [session-handoff](skills/session-handoff/SKILL.md) | 07 | 腐烂信号检测 + 五项交接文档 + 复述验证 | 长会话交接/新会话续跑 |
| [dual-axis-review](skills/dual-axis-review/SKILL.md) | 08 | 规格轴/规范轴独立评审 + 条款仲裁 | AI 代码合入前验收 |

四个技能互不依赖、自由组合：典型链路 `grill-requirements`（开工前）→ 实现中 `project-memory-external`（决策落 ADR）→ 会话临界 `session-handoff`（续跑）→ 合入前 `dual-axis-review`（验收）。

### 安装

```bash
cp -r skills/grill-requirements skills/project-memory-external \
      skills/session-handoff skills/dual-axis-review ~/.agents/skills/
# 或你的 skill 加载路径（~/.atomcode/skills/ 等）
```

## 源材料

- Matt Pocock Skills：github.com/mattpocock/skills — 小、可改、可组合的工程纪律技能卡片（与 GSD/BMAD/Spec-Kit 接管流水线路线相对）
- Ousterhout《A Philosophy of Software Design》— 深模块判据（文章 04）
- 本机技能库对照实践 — `~/.agents/skills/` 下的 grill-with-docs 等
