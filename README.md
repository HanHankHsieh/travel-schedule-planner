# 🌸 旅遊助手 - 智能旅遊規劃平台 🌸

一個功能完整的 **旅遊規劃應用程式**，整合行程管理、機票飯店資訊、願望清單、分帳記帳系統，並支援 Firebase 雲端同步與多人協作。

---

## ✨ 核心功能

### 📅 多日行程規劃
- 自由新增/刪除/編輯每日行程
- 自訂日期標題（例如：Day 1 東京、Day 2 京都）
- 每個景點可設定：
  - ⏰ 時間安排
  - 📍 Google Maps 地圖連結
  - 🔗 官方網站連結
  - 📝 備註說明
  - 💰 支出明細（含分帳功能）
  - ✅ 待買/待辦清單（可勾選完成）

### ✈️ 機票管理
- 登機證風格的精美卡片介面
- 記錄航班資訊：
  - 航空公司、航班號碼
  - 出發地 ✈️ 目的地
  - 起飛時間
  - 航廈/登機門、座位號碼

### 🏨 飯店住宿管理
- 飯店名稱、入住日期
- Google Maps 地圖導航
- 訂房確認碼/連結
- 飯店備註說明

### ✨ 願望清單
- 收藏想去但尚未排入行程的景點/餐廳
- 可直接「📅 匯入」到指定日期的行程中
- 支援與行程相同的完整功能（地圖、連結、待買清單、支出記錄）

### 💰 記帳與分帳系統
- **旅伴管理**：新增/移除同行旅伴
- **智能分帳**：
  - 每筆支出可指定付款人
  - 自由選擇分攤對象（支援部分分攤）
  - 自動計算每位旅伴的應收/應付金額
- **多幣別支援**：TWD、JPY 等
- **即時結算統計**：視覺化顯示每個人的收支狀況

### ⚙️ 管理介面
- **備份與還原**：
  - 複製完整 JSON 資料進行備份
  - 從 JSON 還原所有行程與設定
- **危險區域**：清空所有本地資料（需輸入 PIN 碼：8888）

### ☁️ Firebase 雲端同步
- 資料自動同步至 Firebase Realtime Database
- 支援多裝置存取
- 透過 URL 參數 `?id=xxx` 建立專屬行程空間
  - 例如：`index.html?id=tokyo2024` 
  - 不同 ID = 不同獨立行程
  - 分享連結給朋友即可共同編輯

---

## 🎨 設計特色

- **淡藍色調美學**：天空藍漸層配色，清新舒適
- **卡片式設計**：每個項目以獨立卡片呈現，資訊分層清晰
- **登機證風格機票**：深藍色漸層設計，專業質感
- **底部導航列**：快速切換行程/機票/飯店/願望/記帳/管理六大功能
- **浮動新增按鈕（FAB）**：快速新增項目
- **響應式介面**：支援手機、平板、電腦瀏覽

---

## 🚀 使用方式

### 1. 本地使用
直接開啟 `index.html` 即可使用！無需安裝任何套件。

### 2. 建立專屬行程空間
在網址後加上 `?id=你的行程名稱`，例如：
```
index.html?id=japan2025
index.html?id=europe_trip
```

### 3. 分享給旅伴
將完整網址（含 `?id=xxx`）分享給同行友人，即可共同編輯行程！

### 4. 備份資料
1. 點擊底部導航的「⚙️ 管理」
2. 點擊「📋 複製備份」
3. 將 JSON 資料儲存至安全位置

### 5. 還原資料
1. 點擊底部導航的「⚙️ 管理」
2. 將備份的 JSON 貼上文字框
3. 點擊「💾 寫入資料」

---

## 📦 技術架構

- **前端框架**：純 HTML + CSS + JavaScript（Vanilla JS）
- **資料庫**：Firebase Realtime Database
- **本地儲存**：LocalStorage（作為備份）
- **設計模式**：Single Page Application (SPA)
- **資料格式**：JSON

---

## 🔧 Firebase 設定

本專案已預設連接 Firebase 專案，如需使用自己的 Firebase：

1. 前往 [Firebase Console](https://console.firebase.google.com/)
2. 建立新專案並啟用 Realtime Database
3. 將 `index.html` 中的 `firebaseConfig` 替換為您的設定：

```javascript
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  databaseURL: "https://YOUR_PROJECT.firebaseio.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

---

## 📖 操作指南

### 新增行程景點
1. 確保在「📅 行程」頁面
2. 點擊右下角藍色「+」按鈕
3. 填寫景點資訊
4. 可新增多筆支出與待買清單
5. 點擊「儲存資料」

### 編輯/刪除項目
- 點擊卡片右上角的「✏️」編輯
- 點擊「🗑️」刪除

### 願望清單匯入行程
1. 在願望清單項目點擊「📅 匯入」
2. 選擇要加入的日期
3. 確認匯入

### 記帳分帳
1. 先在「💰 記帳」頁面新增所有旅伴
2. 在新增景點時，點擊「💰 記帳明細」
3. 填寫支出項目、金額、幣別
4. 選擇付款人
5. 勾選要分攤此筆的旅伴
6. 系統會自動計算每個人的應收/應付

---

## 🌐 線上體驗

<p>
  <a href="https://hanhankhsieh.github.io/travel-schedule-planner/" 
     target="_blank" 
     style="display:inline-block; padding:10px 20px; background:#4facfe; color:white; border-radius:8px; text-decoration:none; font-weight:bold;">
     🔗 立即體驗
  </a>
</p>

---

## 📝 授權

本專案僅供個人學習與使用。

---

## 💡 提示與建議

- 💾 **定期備份**：建議每次旅行前先備份一次 JSON 資料
- 🔗 **分享連結**：使用 `?id=` 參數可建立多個獨立行程空間
- 👥 **旅伴管理**：記得先新增所有旅伴再開始記帳，避免後續修改
- 📱 **手機使用**：本應用完全支援手機瀏覽器，建議加入主畫面快速存取

---

## 🎯 適用場景

✅ 多人出國旅遊規劃  
✅ 商務出差行程管理  
✅ 自助旅行攻略整理  
✅ 團體旅遊分帳記錄  
✅ 蜜月旅行規劃  

---

**祝您旅途愉快！🌸✈️🗺️**
