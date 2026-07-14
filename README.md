# MVP 抽獎機

礁溪老爺酒店年度運動會 MVP 抽獎系統，運動風格主題，透過 Firebase Realtime Database
讓「後台輸入頁面（手機）」與「大螢幕頁面」即時同步。

## 檔案結構

- `index.html` — 首頁，導向大螢幕頁與後台頁
- `screen.html` — 大螢幕投影頁，播放老虎機抽獎動畫
- `admin.html` — 手機後台頁，輸入四項冠軍名單並觸發開獎

## 部署前必做：設定 Firebase

1. 到 [Firebase Console](https://console.firebase.google.com) 建立新專案（免費 Spark 方案）
2. 左側選單「Build → Realtime Database」→ 建立資料庫 → 選離台灣近的地區 → 先選「測試模式」
3. 左側「專案設定」→「一般」→ 新增網頁應用程式（`</>`）→ 複製出現的 `firebaseConfig`
4. 把這組設定貼到 `screen.html` 和 `admin.html` 兩個檔案裡的 `FIREBASE_CONFIG`
   （**兩邊必須完全一樣**，才能連到同一個資料庫）

> ⚠️ 測試模式的資料庫規則 30 天後會自動關閉讀寫權限，正式使用前記得到
> Realtime Database → 規則，改成長期允許讀寫。

## 部署到 Zeabur

1. 在 Zeabur 建立新專案 → 選擇「GitHub」服務類型 → 連接這個 repo
2. 因為專案內沒有特定語言（純 HTML），Zeabur 會自動以靜態網頁模式部署
3. 部署完成後：
   - 首頁：`https://你的網址.zeabur.app/`
   - 大螢幕：`https://你的網址.zeabur.app/screen.html`
   - 後台：`https://你的網址.zeabur.app/admin.html`

## 使用方式

1. 大螢幕開啟 `screen.html`
2. 手機開啟 `admin.html`，輸入四項競賽的項目名稱與冠軍姓名
3. 按下「開始抽獎」，大螢幕會自動播放老虎機抽獎動畫並停在隨機抽出的 MVP
