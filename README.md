# LOVEFU 使用心得回饋問卷（前端）

LOVEFU大島樂眠「最真實的心得回饋」問卷的靜態前端，部署於 GitHub Pages。

- 表單送出與檔案上傳由 Google Apps Script 後端處理（回覆寫入內部 Google Sheet，照片影片自動歸檔到 Google Drive）
- 大檔影片採瀏覽器直傳 Google Drive（resumable upload），失敗時自動改走 Apps Script 分段轉傳
- 純靜態頁面，本 repo 不含任何金鑰或內部資料

維護：修改 `index.html` 後 push 到 main，GitHub Pages 會自動更新。

## 部署檢查清單（重新部署時必看）

1. Apps Script 部署「網頁應用程式」時：執行身分＝我、誰可以存取＝**任何人**（選錯會整個表單掛掉）
2. 部署後把新的 `/exec` 網址填入 `index.html` 的 `API_URL`（頁面有防呆，網址沒設好會鎖住表單）
3. 上線前開無痕視窗實測一筆：填表＋傳一張照片＋一支影片，確認試算表出現新列、檔案進資料夾
