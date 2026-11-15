# 審批檢查表 | Approval checklists（三閘）

> 每個閘開始前：AI 助理交齊報告 → 你逐項過 → 只可以回 approve / tweak / reject。
> 未回覆之前，助理唔可以繼續。

## 閘一：腳本審批 | Gate 1: script review

- [ ] 全部變體（3–5 條）**一次過睇晒**，唔係逐條擠牙膏
- [ ] 每條變體有 hook 方向摘要，方便比較
- [ ] 結構完整：開場 → 主體 → 收尾，收尾有明確金句／CTA
- [ ] 字數喺 {{word-count-range}} 內
- [ ] 機械檢查報告 0 FAIL（禁字清單、語法檢查、TTS pause marker 如適用）
- [ ] 冇虛構引用／冇抄襲疑點

決定：

- **approve** → 入步驟③定稿入庫
- **tweak** → 你手改（或口頭改），助理重跑全部機械檢查
- **reject** → 成批重做；記低唔啱咩，等下輪變體改善

## 閘二：設計方向 | Gate 2: design direction

- [ ] 時點正確：對時數據齊、**未批量渲染**
- [ ] 動態預覽＋首幀靜態圖齊備
- [ ] CJK 字體已明確宣告（唔好信預設 fallback），以實際環境測過
- [ ] 全部文字喺 safe zone 內（見 `PIPELINE.md` §6）
- [ ] 每行字幕字數 ≤ {{max-chars-per-line}}
- [ ] 視覺風格同 {{your-visual-style}} 一致

決定同閘一。

## 閘三：收貨 | Gate 3: final acceptance

- [ ] 成片由頭到尾**睇一次**（唔係抽睇）
- [ ] 每個 section 抽一幀：字喺安全區內、冇空白段、字形正確
- [ ] 字幕同步：抽查開頭／中段／結尾各一處
- [ ] 音頻：音量一致、冇爆音；TTS 讀音替代表冇漏（人耳驗收）
- [ ] 技術驗收報告過（編碼／解像度／時長）
- [ ] 發佈前檢查表已過（`checklists/pre-publish-checklist.md`）

決定：

- **approve** → 入排程
- **tweak** → 開清單逐項改，改完重新驗收
- **reject** → 分清係內容層（返閘一邏輯）定製作層（返步⑥–⑧）

## 通用停止條件 | Universal stop conditions

- 任何檢查表有未過項：唔好過閘。
- 閘三未過：唔好開下一條變體／下一集。
- 助理話「應該得啦」：唔算數，以你親自驗為準。
