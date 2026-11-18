# 2026 日本夏日旅行互動地圖

免安裝、免框架的靜態網頁，可直接部署到 GitHub Pages。包含 **8 個可點選／滑鼠懸停發光的圓形地圖熱區**、城市行程摘要、**54 頁 PDF 的文字擷取與逐頁展開**、全文搜尋、原始 PDF（含截圖與圖片）和手機版抽屜面板。

## GitHub Pages 上架

1. 在 GitHub 新增公開或具備 Pages 權限的 repository，例如 `japan-trip-2026`。
2. **把本資料夾裡的所有檔案**（`index.html`、`itinerary.json`、`assets/`）上傳到 repository 根目錄。不要只上傳圖片。
3. 進入 **Settings → Pages**，於 **Build and deployment** 選 **Deploy from a branch**，選 `main` 和 `/ (root)`，儲存。
4. GitHub Pages 完成部署後，網站網址會類似 `https://你的帳號.github.io/japan-trip-2026/`。

本機測試：進入資料夾執行 `python3 -m http.server 8000`，瀏覽 `http://localhost:8000`。直接雙擊 index.html 可能因瀏覽器限制導致 JSON 無法載入。

## 改內容

- `assets/map-clean.jpg`：**已去除右下方木製鳥居的底圖**，保留城市插畫。可替換成相同內容的新版圖片。
- `itinerary.json`：`regions` 內每個城市的 `intro`、`days`、`chips`、`tip` 都能編輯；`pages` 對應原 PDF 頁次；`point` 是地圖上圓形位置的 **相對座標** `[x,y]`，例如 `[0.69,0.224]`。
- `assets/original-itinerary.pdf`：原始行程，保留圖片、畫面截圖與表格。
- `index.html`：介面、顏色、動態效果、點擊互動；完全不依賴 CDN。

## 注意

原始 PDF 中部分同一日期存在多種備選方案，且首頁寫「總共住15天」，但行程寫到 Day 16（7/29）。本站不自行判斷哪個方案為最終版本，並保留原始 PDF 供對照。PDF 文字版由文字擷取生成，因此雙欄區塊或折行可能不如 PDF 原版整齊。

發佈前注意：PDF 可能含預約截圖、預訂資訊及個人旅行資訊。若放在公開 GitHub repository，其他人可能讀到完整 PDF。建議先檢查並刪除不想公開的內容。
