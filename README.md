# AI Content Production Pipeline Template

A method-only playbook for producing scripted content (long-form video,
image carousels, short vertical videos) with an AI chat bot as your
**production assistant** — and a human as the only approver.

It was reverse-engineered from a real production system used for a
100-episode content project, then **fully de-identified**: no content, no
brand material, no credentials — only the method survived (see
`DEIDENTIFY-REPORT.md`).

## What's inside

| Piece | What it gives you |
|---|---|
| `bot-instructions.md` | Paste-ready role prompt for your Grok Bot (or any LLM bot): it walks the pipeline with you and enforces the gates |
| `PIPELINE.md` | The full method: role map, 9-step core loop, 3 human approval gates, truth-file principles, file conventions, safe zones, pitfalls |
| `checklists/approval-checklist.md` | What to check at each of the 3 gates before approving |
| `checklists/cantonese-grammar-checklist.md` | Two-layer quality checklist for colloquial written Cantonese (skip if not your language) |
| `checklists/pre-publish-checklist.md` | Final pass before anything goes into the publish calendar |
| `DEIDENTIFY-REPORT.md` | Exactly what was removed or placeholder-ized, and from which source files |
| `LICENSE` | CC BY 4.0 — reuse and adapt with attribution |

## Who it's for

- **Solo creators and tiny teams** producing scripted video with AI assistance.
- Anyone who wants the AI to draft and the human to approve — every gate is a hard stop.
- Works for any language; ships with an extra checklist for colloquial written Cantonese.

## How to use

1. Open `bot-instructions.md`, fill in every `{{placeholder}}`, and paste the whole block into your bot's instruction field.
2. Keep `PIPELINE.md` as your process reference; adapt the file conventions to your own tools.
3. One piece of content = one full run of the 9-step loop (steps ①–⑨ in `PIPELINE.md`).
4. At every gate (🛑), open the matching checklist in `checklists/` before you approve.
5. Do not start the next variant or the next episode until Gate 3 (final acceptance) passes.

## Core principles

- **One text-truth file, one time-truth file.** The locked script is the only source for every derivative; the corrected subtitle file is the only source for timing. To change something, change the truth file and re-run the generation step — never hand-edit generated artifacts.
- **Gates are hard stops.** After each gate the assistant reports and waits. "Looks fine to me" from the assistant is not approval.
- **Mechanical thresholds are non-negotiable.** Timing coverage ≥ 90%, subtitle line-length caps, zero forbidden words — failing a threshold means going back to fix the source, not overriding the check.
- **Draft → human approval → publish.** Nothing ships without a human gate.

## Limitations

- **Method only.** No automation scripts are included — you wire your own TTS, speech-to-text and rendering tools into the steps.
- **Placeholders must be filled** (`{{...}}`) before the bot instructions work for your brand.
- **The Cantonese checklist is language-specific.** Skip it for other languages.
- **A human approver must exist.** This is a human-in-the-loop pipeline, not an autonomous one.
- **CC BY 4.0 requires attribution** — keep the credit and link when you reuse or adapt (see `LICENSE`).

---

# 繁體中文說明

## 呢份係乜

一套**去識別化嘅內容製作 pipeline 範本**：由揀題、腳本、配音、字幕、動態圖，到審批、排程嘅完整方法。核心係一條 **9 步 3 閘**嘅 loop——AI 助理代出草稿，人手喺三個閘口審批，過咗閘先可以繼續。方法取材自一個真實行過嘅量產系統，所有私人資料已剷走（逐項見 `DEIDENTIFY-REPORT.md`）。

## 適合邊類人

- 用 AI 協助做腳本影片（長片／圖卡／直式短片）嘅個人創作者或細團隊
- 想要「AI 出草稿、人手把關」嘅人——每個閘都係硬停位
- 任何語言都用得；另附粵語口語語法檢查表

## 點樣用

1. 打開 `bot-instructions.md`，填好所有 `{{佔位符}}`，成段貼入你個 Grok Bot（或任何 LLM bot）嘅指示欄。
2. `PIPELINE.md` 留做流程參考；檔案約定按你自己嘅工具調整。
3. 一條內容＝行一次 9 步 loop；每個閘口（🛑）先開 `checklists/` 對應檢查表，批完先繼續。
4. 閘三收貨之前，唔好開下一條變體／下一集。

## 限制

- **淨係方法**：唔包自動化腳本；TTS／語音識別／渲染工具自己接入。
- **佔位符要填**：`{{...}}` 唔填，bot 指示唔會啱你個品牌用。
- **粵語檢查表只啱粵語內容**：其他語言跳過佢。
- **假設有人手審批者**：呢條 pipeline 唔係全自動。
- **CC BY 4.0 要署名**：轉用或改作要保留出處（見 `LICENSE`）。

---

## Links | 連結

- Delic Club Grok Bot: <https://www.delicclub.ai/grokbot?utm_source=github&utm_medium=referral&utm_campaign=template-launch>

Independent Delic Club work. No official partnership with Grok, xAI or Anthropic.
