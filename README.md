# ai-product-skills

适用于产品/AI产品同学的工作流 | Workflow skills for AI product managers

---

## 中文

### 仓库结构

```
ai-product-skills/
├── product-methodology/        # 产品方法论 + 方案审查
│   ├── PRINCIPLES.md           # 产品原则（通用）
│   ├── SOP.md                  # 产品方案 SOP（通用）
│   ├── REVIEW.md               # UI/体验 Review 清单（通用）
│   └── review-plan-SKILL.md    # 海外版方案审查 skill
└── intern-experience/          # 实习经历沉淀（产品经理实习生专用）
    ├── cv-skill.md             # 工作记录 → 简历项目经历
    └── intern-introduction.md  # 面试口头介绍 + 模拟考核
```

### Skills 列表

本仓库包含六个 skill，分为三类：

| 类别 | Skills | 适用范围 |
|------|--------|----------|
| 产品方法论 | PRINCIPLES / SOP / REVIEW | 通用，适用于任何产品 |
| 方案审查 | /review-plan | 专门针对海外版产品方案 |
| 实习经历沉淀 | cv-skill / intern-introduction | 产品经理实习生，简历 + 面试准备 |

#### 产品方法论（`product-methodology/`） — 通用

一套完整的产品方法论体系，三个文档各司其职、互相引用，适用于任何产品方向：

| 文件 | 用途 | 说明 |
|------|------|------|
| `PRINCIPLES.md` | 产品原则 | 从用户四个本质（懒、急、挑、晒）推导出 8 条原则 + 元原则"非必要勿增实体" |
| `SOP.md` | 产品方案 SOP | 从想法到可执行方案的四步流程：压想法 → Demo/PRD → 瘦身 → 边界梳理 |
| `REVIEW.md` | UI/体验 Review 清单 | 五层 checklist（心智层、感知层、交互层、流程层、容错层），做 demo 前当生成约束，做完后当验收 gate |

**使用方式：**

- **做方案前**：读 `PRINCIPLES.md`，用原则校准方向
- **做方案时**：按 `SOP.md` 四步流程推进
- **做 demo 前**：把 `REVIEW.md` 喂给 Claude Code 当生成约束
- **做完后**：用 `REVIEW.md` 逐层自检验收

#### 实习经历沉淀（`intern-experience/`） — 产品经理实习生专用

包含两个互相配合的 skill：

**cv-skill.md — 工作记录 → 简历项目经历**

将实习期间散落各处的工作记录（飞书待办、方案文档、会议纪要、OKR 等），整理为**可直接粘进简历的 bullet points**。

- 从琐碎记录中提取关键事实（做了什么、方法、产出、量化结果）
- 按项目维度结构化梳理，提炼 2-3 个最能打的卖点
- 输出三个版本：一句话版 / 标准版（3-4 行） / 详细版（5-6 行）
- 中英文双版本
- 内置面试官视角质量检查：分量感、专业度、结果可信度

**intern-introduction.md — 面试口头介绍 + 模拟考核**

基于 cv-skill 输出的项目经历，生成面试时的口头介绍话术和高频考核问答。

- STAR 框架口头介绍（2-3 分钟，Action 占 40-50% 篇幅）
- 5-8 个模拟考核问题（需求判断、用户理解、方案设计、数据思维等）
- 每个问题配参考回答（结论先行 + 展开逻辑 + 落地举例）
- 产品思维检查清单自检

**使用场景：**
- **日常积累**：每 1-2 周用 cv-skill 整理一次，避免最后想不起来做了什么
- **阶段性整理**：实习结束前，一次性整理所有记录为简历文本
- **面试准备**：用 intern-introduction 生成口头话术和模拟问答，针对目标岗位定制

#### /review-plan — 海外版专用

一个专门针对**海外版产品方案**的 Claude Code skill。从**创新性**、**海外市场适配性**、**方案完整性**三个维度逐项检查，给出具体问题和可操作的改进建议。

**适合谁用：**
- 需要自主审查方案、没有 mentor review 的场景
- 正在为海外用户设计功能
- 希望用结构化清单来发现方案盲区

**使用流程：**
1. 将产品方案从飞书（或其他文档工具）导出为 Word 文件
2. 在 Claude Code 中调用 `/review-plan`，提供文件路径
3. Claude 按 6 大类清单逐项检查，在对话中输出结果
4. 和 Claude 讨论、迭代
5. 讨论完毕后，Claude 生成一份 Word 审查报告

**6 大检查类别：**

| # | 类别 | 关注点 |
|---|------|--------|
| 1 | 需求层 | 出发点对不对？优先级、时间线、上下文是否清晰 |
| 2 | 创新性 | 差异化够不够？是真实用户需求还是单纯跟随竞品？ |
| 3 | 海外适配性 | 本地化、文化敏感性、合规（GDPR 等） |
| 4 | 方案细节 | 文案质量、交互完整性、多端一致性 |
| 5 | 角色切换 + "所以呢"测试 | 用户/研发/运营视角，关键决策是否站得住脚 |
| 6 | 上线预判 | 用户路径验证、老用户兼容、效果指标 |

### 安装

将对应 skill 文件夹复制到 Claude Code 的 skills 目录：

```bash
# 个人使用（所有项目通用）
cp -r product-methodology ~/.claude/skills/
cp -r intern-experience ~/.claude/skills/

# 仅限当前项目
cp -r product-methodology .claude/skills/
cp -r intern-experience .claude/skills/
```

### 自定义

`product-methodology/review-plan-SKILL.md` 中有一个"产品背景信息"区域，预留了占位符。填入你自己的产品背景信息，可以获得更有针对性的审查：

- 产品定位
- 目标市场和用户画像
- 功能规划清单
- 海外版和国内版的主要差异
- 运营侧的要求和节奏
- 技术/合规约束

---

## English

### Repository Structure

```
ai-product-skills/
├── product-methodology/        # Product methodology + plan review
│   ├── PRINCIPLES.md           # Product principles (universal)
│   ├── SOP.md                  # Product plan SOP (universal)
│   ├── REVIEW.md               # UI/UX review checklist (universal)
│   └── review-plan-SKILL.md    # Overseas plan review skill
└── intern-experience/          # Intern experience (for PM interns)
    ├── cv-skill.md             # Work records → resume bullet points
    └── intern-introduction.md  # Interview oral intro + mock Q&A
```

### Skills

This repo contains six skills in three categories:

| Category | Skills | Scope |
|----------|--------|-------|
| Product Methodology | PRINCIPLES / SOP / REVIEW | Universal, applicable to any product |
| Plan Review | /review-plan | Specifically for overseas product plans |
| Intern Experience | cv-skill / intern-introduction | For PM interns, resume + interview prep |

#### Product Methodology (`product-methodology/`) — Universal

A complete product methodology system — three docs, each with a clear role, cross-referencing each other. Applicable to any product direction:

| File | Purpose | Description |
|------|---------|-------------|
| `PRINCIPLES.md` | Product principles | 8 principles derived from four user truths (lazy, impatient, picky, sharing) + meta-principle "don't add what you don't need" |
| `SOP.md` | Product plan SOP | Four-step process from idea to execution: compress idea → demo/PRD → trim → boundary check |
| `REVIEW.md` | UI/UX review checklist | Five-layer checklist (mental model, perception, interaction, flow, error recovery) — use as generation constraints before building, validation gate after |

**How to use:**

- **Before planning**: Read `PRINCIPLES.md` to calibrate direction
- **While planning**: Follow the four-step process in `SOP.md`
- **Before building a demo**: Feed `REVIEW.md` to Claude Code as generation constraints
- **After building**: Self-review against `REVIEW.md` layer by layer

#### Intern Experience (`intern-experience/`) — For PM Interns

Two complementary skills:

**cv-skill.md — Work Records → Resume Bullet Points**

Converts scattered internship work records (task lists, docs, meeting notes, OKRs) into **resume-ready bullet points**.

- Extracts key facts from messy records (what you did, methods, deliverables, metrics)
- Organizes by project, distills 2-3 strongest selling points per project
- Outputs three versions: one-liner / standard (3-4 bullets) / detailed (5-6 bullets)
- Chinese + English dual output
- Built-in quality check from an interviewer's perspective: impact, professionalism, credibility

**intern-introduction.md — Interview Oral Intro + Mock Q&A**

Generates interview oral presentation scripts and mock Q&A based on cv-skill output.

- STAR framework oral introduction (2-3 min, Action at 40-50% of content)
- 5-8 mock interview questions per project (requirements judgment, user understanding, solution design, data thinking, etc.)
- Reference answers for each question (conclusion first + logic + concrete examples)
- Product thinking self-check checklist

**Use cases:**
- **Regular accumulation**: Use cv-skill every 1-2 weeks so nothing is forgotten
- **End-of-internship summary**: Batch process all records into resume text
- **Interview prep**: Use intern-introduction to generate oral scripts and mock Q&A, customize for target roles

#### /review-plan — Overseas-specific

A Claude Code skill specifically designed for reviewing **overseas product plans**. It checks your plan from three dimensions: **innovation**, **overseas market fit**, and **completeness**, then provides specific issues and actionable suggestions.

**Who is this for:**
- PMs who need to self-review plans without a mentor
- Anyone designing features for international users
- Those who want a structured checklist to catch blind spots

**How it works:**
1. Export your product plan from Feishu (or any doc tool) as a Word file
2. Call `/review-plan` in Claude Code and provide the file path
3. Claude checks the plan against a 6-category checklist and outputs results in chat
4. Discuss and iterate together
5. When done, Claude generates a Word review report

**6 review categories:**

| # | Category | Focus |
|---|----------|-------|
| 1 | Requirements | Is the starting point right? Priority, timeline, context clarity |
| 2 | Innovation | Is it differentiated enough? Real user need or just following competitors? |
| 3 | Overseas fit | Localization, cultural sensitivity, compliance (GDPR etc.) |
| 4 | Plan details | Copy quality, interaction completeness, multi-platform consistency |
| 5 | Role switch + "So what" test | User / dev / ops perspectives, decision justification |
| 6 | Launch readiness | User path validation, backward compatibility, success metrics |

### Install

Copy the skill folder to your Claude Code skills directory:

```bash
# Personal use (all projects)
cp -r product-methodology ~/.claude/skills/
cp -r intern-experience ~/.claude/skills/

# Project-specific only
cp -r product-methodology .claude/skills/
cp -r intern-experience .claude/skills/
```

### Customize

The `product-methodology/review-plan-SKILL.md` file contains a "Product background" section with placeholders. Fill in your own product context for more targeted reviews:

- Product positioning
- Target market and user personas
- Feature roadmap
- Differences between domestic and overseas versions
- Ops requirements and timeline
- Technical / compliance constraints

---

## License

MIT
