---
name: humanities-research-skills
version: 1.0.0
role: entry-point
status: active
language: zh-CN / en
---

# Humanities Research Skills — 會計／經濟學研究工具套件

## 套件簡介

本套件專為會計學與經濟學研究生設計，整合深度研究、文獻綜述、
量化分析（串接 Stata MCP）、論文寫作、審稿五大功能，
支援從研究問題釐清到論文定稿的完整流程。

---

## 可用 Skill 清單

| Skill | 資料夾 | 觸發範例 |
|-------|--------|---------|
| deep-research | .claude/skills/deep-research/ | 「幫我研究 X」|
| literature-review | .claude/skills/literature-review/ | 「幫我做文獻綜述」|
| quantitative-analysis | .claude/skills/quantitative-analysis/ | 「幫我跑回歸」|
| academic-writing | .claude/skills/academic-writing/ | 「幫我寫論文」|
| academic-paper-reviewer | .claude/skills/academic-paper-reviewer/ | 「幫我審稿」|
| research-pipeline | .claude/skills/research-pipeline/ | 「幫我跑完整研究流程」|

---

## 調度規則

當使用者輸入訊息時，按以下順序判斷：

Step 1：是否觸發 research-pipeline？
  觸發詞：「完整研究流程」「從頭到尾」「全流程」
  若是 → 載入 research-pipeline/SKILL.md

Step 2：是否觸發單一 Skill？
  「研究 / 深度研究 / 文獻回顧」→ deep-research/SKILL.md
  「文獻綜述 / 整理文獻」→ literature-review/SKILL.md
  「跑回歸 / 量化分析 / Stata」→ quantitative-analysis/SKILL.md
  「寫論文 / 寫第幾章 / 潤飾」→ academic-writing/SKILL.md
  「審稿 / 審這篇論文」→ academic-paper-reviewer/SKILL.md

Step 3：若無法判斷
  詢問使用者：「您是需要研究、寫作還是審稿方面的協助？」

---

## 全域規則（所有 Skill 通用）

以下規則適用於本套件所有 Skill，優先級高於各 Skill 的個別規則：

### 語言規則
- 使用者用簡體中文 → 全程簡體中文輸出
- 使用者用繁體中文 → 全程繁體中文輸出
- 使用者用英文 → 全程英文輸出
- 計量術語保留英文：OLS、DID、PSM、RDD、IV、FE

### 引用誠信（最高優先級）
- 所有引用必須能在 CNKI 或 Web of Science 中實際查到
- 發現疑似捏造引用立即標記 CRITICAL
- 中文文獻必須標明期刊等級 [CSSCI-T1] [CSSCI] [北大核心]
- 英文文獻必須標明期刊等級 [SSCI-Q1] [SSCI-Q2] [ABS-4*]

### 輸出格式
- 所有最終輸出均為 .docx 格式
- 中文字體：宋體（正文）/ 黑體（標題）
- 英文字體：Times New Roman
- 正文字號：12pt，行距：1.5 倍
- 頁邊距：上下左右各 2.54cm（A4 標準）

### 寫作品質
- 中文輸出必須運行 writing_quality_check
- 禁止套話開頭：「當然」「首先需要指出」「綜上所述」「毋庸置疑」
- 輸出長度依內容複雜度自適應，不設字數上限

### 數據可及性
- 推薦任何數據來源必須說明可及性
- 標記方式：[付費-高校可訪問] [付費-需購買] [免費] [需申請]

---

## Stata MCP 設定

本套件的 quantitative-analysis Skill 串接 SepineTam/stata-mcp。

安裝指令（只需執行一次）：
claude mcp add stata-mcp --scope user -- uvx stata-mcp

確認連線：
claude → /mcp → 看到 stata-mcp 即成功

若未安裝，quantitative-analysis 的 execute 相關模式將無法運行，
但 design 模式（只設計不執行）仍可正常使用。

---

## 共用資源

shared/ 資料夾包含所有 Skill 共用的規範：
- handoff_schemas.md：各階段交棒格式
- citation_standards.md：引用格式規範
- writing_quality_check.md：寫作品質檢查清單
- journal_tiers.md：期刊等級對照表

---

## 版本資訊

| 項目 | 內容 |
|------|------|
| 套件版本 | 1.0.0 |
| 建立日期 | 2026-05 |
| 目標學科 | 會計學、經濟學 |
| Stata MCP | SepineTam/stata-mcp |
| 語言支援 | 簡體中文、繁體中文、英文 |
| 授權 | CC-BY-NC 4.0 |
