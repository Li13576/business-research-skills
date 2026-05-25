# Humanities Research Skills

**專為會計學與經濟學研究生設計的 Claude Code 學術工具套件**

*An academic research toolkit for accounting and economics graduate students, powered by Claude Code.*

---

## 這是什麼？

Humanities Research Skills 是一套跑在 Claude Code 上的 Skill 套件，
整合六大功能，支援從研究問題釐清到論文定稿的完整學術研究流程。

最大特色：**串接 Stata MCP，讓 Claude 直接操作 Stata 執行量化分析。**

---

## 六大 Skill

| Skill | 功能 | 觸發範例 |
|-------|------|---------|
| 🔍 deep-research | 深度研究，14 代理，9 種模式 | 「幫我研究審計師任期與盈餘管理的關係」|
| 📚 literature-review | 文獻綜述，從零到可貼進論文 | 「幫我做信息不對稱的文獻綜述」|
| 📊 quantitative-analysis | 量化分析，串接 Stata MCP | 「幫我跑固定效應回歸」|
| ✍️ academic-writing | 論文寫作，無 AI 味中文學術文 | 「幫我寫第三章研究設計」|
| 🔬 academic-paper-reviewer | 審稿，7 代理模擬期刊委員會 | 「幫我審這篇論文」|
| 🔄 research-pipeline | 全流程調度，一鍵跑完 | 「幫我跑完整研究流程」|

---

## 跟其他工具的差異

| 維度 | 一般 AI 工具 | 本套件 |
|------|------------|--------|
| 學科定位 | 通用 | 會計／經濟學專攻 |
| 量化分析 | 無法執行 | 串接 Stata MCP 直接跑 |
| 中文資料庫 | 不支援 | CNKI、CSSCI 搜尋規範 |
| 引用格式 | 基本支援 | GB/T 7714 + APA 7.0 |
| 期刊等級 | 不辨別 | CSSCI T1 / SSCI Q1 分級 |
| 誠信查核 | 無 | 強制兩次假引用偵測 |
| 日誌記錄 | 無 | 研究日誌 + Stata 執行日誌 |

---

## 快速開始

### 1. 安裝 Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

### 2. 安裝 Stata MCP（量化分析功能需要）

```bash
claude mcp add stata-mcp --scope user -- uvx stata-mcp
```

### 3. 下載本套件

```bash
git clone https://github.com/你的用戶名/humanities-research-skills.git
cd humanities-research-skills
```

### 4. 啟動 Claude Code

```bash
claude
```

### 5. 開始使用

```
# 全流程
幫我跑完整研究流程

# 單一功能
幫我研究 ESG 披露對審計費用的影響
幫我做碳信息披露的文獻綜述
幫我跑固定效應回歸
幫我寫第三章研究設計
幫我審這篇論文
```

---

## 檔案結構

```
humanities-research-skills/
├── .claude/
│   └── CLAUDE.md                    ← 入口，統一調度
│
├── deep-research/
│   └── SKILL.md                     ← 深度研究
│
├── literature-review/
│   └── SKILL.md                     ← 文獻綜述
│
├── quantitative-analysis/
│   └── SKILL.md                     ← 量化分析（Stata MCP）
│
├── academic-writing/
│   └── SKILL.md                     ← 論文寫作
│
├── academic-paper-reviewer/
│   └── SKILL.md                     ← 審稿
│
├── research-pipeline/
│   └── SKILL.md                     ← 全流程調度
│
├── shared/                          ← 共用規範
│   ├── handoff_schemas.md
│   ├── citation_standards.md
│   ├── writing_quality_check.md
│   └── journal_tiers.md
│
└── README.md
```

---

## 系統需求

- Claude Code（最新版）
- Claude Max 計畫或 API 金鑰（建議：full pipeline 耗用 token 較多）
- Stata（量化分析功能需要，支援 Stata 16+）
- Python 3.8+（Stata MCP 需要）

---

## 使用場景範例

**場景 1：碩士論文第二章**
```
幫我做「審計師任期與盈餘管理」的文獻綜述，
目標是 CSSCI 期刊，需要找 20-30 篇文獻，
輸出可以直接貼進論文第二章的格式。
```

**場景 2：量化分析**
```
我的研究問題是「企業社會責任披露對融資成本的影響」，
樣本是 2010-2022 年 A 股上市公司，
幫我設計變數、跑固定效應回歸、做穩健性檢驗。
```

**場景 3：投稿前審稿**
```
幫我審這篇論文，重點看方法論，
特別是內生性處理和穩健性檢驗。
```

---

## 注意事項

- 本套件生成的所有引用請自行驗證，AI 有捏造引用的風險
- 量化分析結果僅供參考，請結合專業判斷使用
- full pipeline 模式耗用 token 較多，建議使用 Claude Max 計畫

---

## 授權

CC-BY-NC 4.0 — 可自由使用和修改，不可商業使用，請保留出處。

---

## 致謝

本套件的設計參考了 [Imbad0202/academic-research-skills](https://github.com/Imbad0202/academic-research-skills)，
在其基礎上針對會計／經濟學領域進行了深度改造，並加入了 Stata MCP 串接功能。

---

*如有問題或建議，歡迎提交 Issue 或 Pull Request。*
