# ai-product-skills

适用于产品/AI产品同学的工作流 | Workflow skills for AI product managers

---

## 中文

### Skills 列表

#### /review-plan

一个用于审查 AI 产品方案的 Claude Code skill。从**创新性**、**海外市场适配性**、**方案完整性**三个维度逐项检查，给出具体问题和可操作的改进建议。

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
cp -r review-plan ~/.claude/skills/

# 仅限当前项目
cp -r review-plan .claude/skills/
```

### 自定义

`SKILL.md` 中有一个"产品背景信息"区域，预留了占位符。填入你自己的产品背景信息，可以获得更有针对性的审查：

- 产品定位
- 目标市场和用户画像
- 功能规划清单
- 海外版和国内版的主要差异
- 运营侧的要求和节奏
- 技术/合规约束

---

## English

### Skills

#### /review-plan

A Claude Code skill for reviewing AI product plans. It checks your plan from three dimensions: **innovation**, **overseas market fit**, and **completeness**, then provides specific issues and actionable suggestions.

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
cp -r review-plan ~/.claude/skills/

# Project-specific only
cp -r review-plan .claude/skills/
```

### Customize

The `SKILL.md` file contains a "Product background" section with placeholders. Fill in your own product context for more targeted reviews:

- Product positioning
- Target market and user personas
- Feature roadmap
- Differences between domestic and overseas versions
- Ops requirements and timeline
- Technical / compliance constraints

---

## License

MIT
