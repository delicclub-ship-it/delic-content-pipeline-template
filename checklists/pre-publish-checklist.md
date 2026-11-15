# 發佈前檢查表 | Pre-publish checklist

> 過晒閘三先開始呢張表；全過先可以入排程。

## 內容層 | Content

- [ ] 禁字／禁短語掃描：0 出現
- [ ] 語法檢查表 0 🔴（`checklists/cantonese-grammar-checklist.md`）
- [ ] 字形檢查：{{繁體輸出語境}} 冇簡體字混入
- [ ] 跨格式主旨一致（長片／圖卡／短片講緊同一個 core message）
- [ ] 引用／書名／史實抽查過（Q7／Q12）

## 技術層 | Technical

- [ ] 字幕同 master 音軌對齊：抽查頭／中／尾三處
- [ ] 編碼驗收：video h264 · {{resolution}} · yuv420p；audio aac；兩條 stream
- [ ] 字幕每行字數 ≤ {{max-chars-per-line}}
- [ ] 音量一致、冇爆音
- [ ] TTS 讀音替代：抽查開場／金句／結尾

## 品牌層 | Brand

- [ ] 水印／品牌標識：{{your-brand-watermark}}（如有）
- [ ] Hashtags：{{your-hashtag-policy}}
- [ ] CTA／連結正確
- [ ] 署名政策：{{your-byline-policy}}（邊啲集可以自我介紹、邊啲唔可以）

## 排程層 | Scheduling

- [ ] 所有計劃出嘅格式齊：{{your-formats}}
- [ ] 工作檔 status 行晒階梯：drafting → validated → final → all_done
- [ ] 入發佈曆，日期時間已確認
- [ ] 大檔（音頻／成片）確定唔會誤入版本控制（.gitignore 檢查過）
- [ ] 防遺漏總檢：sections 數／產物檔數 grep 過一次；多版本產物 MD5 對比（如適用）
