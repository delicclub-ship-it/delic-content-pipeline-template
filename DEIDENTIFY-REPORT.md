# 去識別化報告 | De-identification report

> 記錄範本「刪走咗咩、改寫咗咩、原本嚟自邊個源檔」。
> 源檔全部用相對路徑引用；本報告自身亦唔含任何黑名單字串（見文末自查）。

## 方法來源 | Method sources

範本嘅方法層改寫自以下源文件：

- `documentation/playbooks/motion-graphic-reel-pipeline.md` — 9 步 3 閘、真相檔原則、驗收表、safe zone
- `documentation/playbooks/workspace-execution-runbook.md` — 角色分工、每步 DoD、閘口與綠燈制、量產節奏、pitfalls
- `documentation/playbooks/script-readthrough-audit.md` — 語法檢查表兩層結構（機械掃描＋語意 Q1–Q15）
- `documentation/CONSTITUTION.md` — 禁字機制、status 階梯概念
- `documentation/configuration.json` — 格式規範、替代表機制概念
- `documentation/ROLES.md` / `documentation/WORKFLOW.md` — 角色框架概念

## 刪走／改寫類別 | Removed & rewritten

| # | 類別 | 原本出現喺 | 處理 |
|---|---|---|---|
| 1 | 企劃名稱（書名級品牌名，全 repo 大量出現） | 幾乎全部源文件標題／內文 | 全刪；範本一律用「本 pipeline / this template」 |
| 2 | 作者筆名及人手審批者稱謂 | CONSTITUTION.md、runbook、audit playbook、configuration.json `author` 欄 | 全刪；改「作者／人手審批者／版權持有人」 |
| 3 | 外部導師名／外部課程名／推薦語境 | CONSTITUTION.md 作者身份節 | 全刪（範本唔需要） |
| 4 | 品牌水印網域字串 | configuration.json `brand_watermark` | 改 `{{your-brand-watermark}}`；唯一保留位：README CTA（作者指定嘅推廣連結） |
| 5 | TTS 聲音 ID／模型名／語言參數 | configuration.json `tts_defaults` | 改 `{{tts-provider}}` 設定；淨保留「聲音設定集中管理」機制 |
| 6 | 動畫模型名／價格上限 | configuration.json `animation_defaults` | 泛化成「動態渲染服務」 |
| 7 | 視覺風格 prompt 全文字串 | configuration.json `deck_visual_style` | 改 `{{your-visual-style}}`；淨保留「風格 baked-in＋pre-flight 檢查」機制 |
| 8 | 主題表／分類框架／預設 hashtags／章節 hashtag 格式 | configuration.json `themes`／`legacy_categories`／hashtags 欄 | 改 `{{your-topic-taxonomy}}`／`{{your-hashtag-policy}}` |
| 9 | Persona 名稱及 tone 描述 | configuration.json `personas` | 概念保留（兩種敘事聲音＋混合模式），名稱全刪，納入 `{{voice-guide}}` |
| 10 | 書單／學者名／實戰引用例句 | audit playbook Q7、Q12、pitfalls 表 | 例子全部新寫（中性內容）；語言現象本身保留 |
| 11 | Workspace ID 代碼及事故案例細節 | runbook、reel pipeline playbook | 改 `{{id}}`；事故泛化成「曾發生繞過閘口嘅事故，所以閘口係硬規則」 |
| 12 | Mac 絕對路徑（含用戶名） | playbooks 嘅 bash 例子（亦見 `documentation/MEMORY.md`、`.claude/settings.local.json`、`documentation/playbooks/brain-sync.md`、多隻 `scripts/*.py|sh`） | 全刪；範本零絕對路徑 |
| 13 | 專有服務組合（TTS 供應商、deck 生成服務、字幕工具鏈指令） | playbooks、configuration.json | 通用開源工具保留（語音識別、ffmpeg/ffprobe 類概念）；專有服務改佔位符 |
| 14 | 外部品牌完整工作流程圖、付費課程講義、預設工作區 | `documentation/playbooks/full-pipeline-overview.md` 及相關檔（**未採用任何內容**） | 完全未帶入；文末 grep 確認 0 |
| 15 | 官方合作暗示字眼 | （防範性條目） | README 有獨立作品聲明；範本零合作字眼 |
| 16 | 帳戶／電郵／電話／bot ID／API key／數據庫 ID 類字串 | （防範性條目） | 範本零此類內容；文末 grep 確認 0（源文件掃描亦 0，呢類資料唔喺已掃描目錄入面） |

## 保留判斷 | Kept (with rationale)

- 通用平台規格：直式 1080×1920 safe zone、h264/aac 編碼、字幕行寬概念 → 公開平台規格，非私人資料
- 通用開源工具概念：語音識別、媒體檢查工具 → 方法必需，非專有
- 粵語語言現象及例句 → 語言知識；例句全部新寫，唔帶任何原項目句子
- 9 步／3 閘／覆蓋率門檻（90%/80%）等數字 → 方法參數，非私人資料

## 自查 | Self-check

喺本範本資料夾（排除 `.git`）對 12 個黑名單詞做 grep（大小寫不敏感），全部 0 出現：
用戶名兩段（2）＋數字串（3）＋電郵域名（1）＋外部名字（1）＋帳戶字串（1）＋Mac 絕對路徑前綴（1）＋企劃名稱／外部課程核心概念名／外部流程圖品牌名（3，用描述代替原文）。
黑名單詞原文唔寫入本報告——報告自身都要過同一個 grep；實際指令同輸出見交付摘要。

## 遺留事項 | Open items（出街前處理）

- LICENSE 仍係佔位：待版權持有人確定（建議 CC BY 4.0）。
- README CTA 含品牌網域連結：呢個係指定保留嘅推廣連結，唔算泄漏。
- 「Grok Bot」字眼僅為用途描述；已附獨立作品聲明。
- 未經作者批准，本範本唔可以公開。
