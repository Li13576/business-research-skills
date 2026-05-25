# Business Research Skills

**专为商科生设计的 Claude Code 学术工具套件**

*An academic research toolkit for business students, powered by Claude Code.*

---

## 这是什么？

Business Research Skills 是一套跑在 Claude Code 上的 Skill 套件，
整合六大功能，支持从研究问题厘清到论文定稿的完整学术研究流程。

一条流水线：**找文献 → 整理文献 → 跑 Stata 回归 → 写论文 → 审稿 → 定稿，全程自动调度。**

最大特色：**可直接串接 Stata MCP，让 AI 能操作 Stata 执行量化分析、生成结果表格、记录研究日志，不需要你手动切换工具。**

---

## 六大 Skill

| Skill | 功能 | 触发范例 |
|-------|------|---------|
| 🔍 deep-research | 深度研究，14 代理，9 种模式 | 「帮我研究审计师任期与盈余管理的关系」|
| 📚 literature-review | 文献综述，从零到可贴进论文 | 「帮我做信息不对称的文献综述」|
| 📊 quantitative-analysis | 量化分析，串接 Stata MCP | 「帮我跑固定效应回归」|
| ✍️ academic-writing | 论文写作，无 AI 味中文学术文 | 「帮我写第三章研究设计」|
| 🔬 academic-paper-reviewer | 审稿，7 代理模拟期刊委员会 | 「帮我审这篇论文」|
| 🔄 research-pipeline | 全流程调度，一键跑完 | 「帮我跑完整研究流程」|

---

## 跟其他工具的差异

| 维度 | 一般 AI 工具 | 本套件 |
|------|------------|--------|
| 学科定位 | 通用 | 商科专攻（会计／经济学）|
| 量化分析 | 无法执行 | 串接 Stata MCP 直接跑 |
| 中文数据库 | 不支持 | CNKI、CSSCI 搜索规范 |
| 引用格式 | 基本支持 | GB/T 7714 + APA 7.0 |
| 期刊等级 | 不辨别 | CSSCI T1 / SSCI Q1 分级 |
| 诚信查核 | 无 | 强制两次假引用检测 |
| 日志记录 | 无 | 研究日志 + Stata 执行日志 |

---

## 快速开始

### 1. 安装 Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

### 2. 安装 Stata MCP（量化分析功能需要）

```bash
claude mcp add stata-mcp --scope user -- uvx stata-mcp
```

### 3. 下载本套件

```bash
git clone https://github.com/你的用户名/business-research-skills.git
cd business-research-skills
```

### 4. 启动 Claude Code

```bash
claude
```

### 5. 开始使用

```
# 全流程
帮我跑完整研究流程

# 单一功能
帮我研究 ESG 披露对审计费用的影响
帮我做碳信息披露的文献综述
帮我跑固定效应回归
帮我写第三章研究设计
帮我审这篇论文
```

---

## 文件结构

```
business-research-skills/
├── .claude/
│   └── CLAUDE.md                    ← 入口，统一调度
│
├── deep-research/
│   └── SKILL.md                     ← 深度研究
│
├── literature-review/
│   └── SKILL.md                     ← 文献综述
│
├── quantitative-analysis/
│   └── SKILL.md                     ← 量化分析（Stata MCP）
│
├── academic-writing/
│   └── SKILL.md                     ← 论文写作
│
├── academic-paper-reviewer/
│   └── SKILL.md                     ← 审稿
│
├── research-pipeline/
│   └── SKILL.md                     ← 全流程调度
│
├── shared/                          ← 共用规范
│   ├── handoff_schemas.md
│   ├── citation_standards.md
│   ├── writing_quality_check.md
│   └── journal_tiers.md
│
└── README.md
```

---

## 系统要求

- Claude Code（最新版）
- Claude Max 计划或 API 密钥（建议：full pipeline 耗用 token 较多）
- Stata（量化分析功能需要，支持 Stata 16+）
- Python 3.8+（Stata MCP 需要）

---

## 使用场景范例

**场景 1：硕士论文第二章**
```
帮我做「审计师任期与盈余管理」的文献综述，
目标是 CSSCI 期刊，需要找 20-30 篇文献，
输出可以直接贴进论文第二章的格式。
```

**场景 2：量化分析**
```
我的研究问题是「企业社会责任披露对融资成本的影响」，
样本是 2010-2022 年 A 股上市公司，
帮我设计变量、跑固定效应回归、做稳健性检验。
```

**场景 3：投稿前审稿**
```
帮我审这篇论文，重点看方法论，
特别是内生性处理和稳健性检验。
```

---

## 注意事项

- 本套件生成的所有引用请自行验证，AI 有捏造引用的风险
- 量化分析结果仅供参考，请结合专业判断使用
- full pipeline 模式耗用 token 较多，建议使用 Claude Max 计划

---

## 授权

CC-BY-NC 4.0 — 可自由使用和修改，不可商业使用，请保留出处。

---

## 致谢

本套件的设计参考了 [Imbad0202/academic-research-skills](https://github.com/Imbad0202/academic-research-skills)，
在其基础上针对商科领域进行了深度改造，并加入了 Stata MCP 串接功能。

---

*如有问题或建议，欢迎提交 Issue 或 Pull Request。*
