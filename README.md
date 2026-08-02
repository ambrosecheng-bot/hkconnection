# Vibe Coding 工作坊 — Landing Page

單頁宣傳網頁，用嚟推廣「兩小時，建立屬於你的第一個網頁」Vibe Coding 工作坊（Southampton 本地舉行）。

**線上網址：** https://ambrosecheng-bot.github.io/hkconnection/

## 檔案結構

```
index.html   # 單一 HTML 檔案，包含所有 CSS 同內容（圖片以 base64 內嵌）
```

呢個係一個 self-contained 嘅靜態網頁，冇任何外部依賴（無 JS framework、無外部 CSS/字體檔案），可以直接用瀏覽器打開，或者上傳到任何靜態網站託管服務（例如 GitHub Pages）。

## 頁面結構

- **Hero** — 標題、副標題、CTA 按鈕、社會證明數字（50+ 學員 · 4 堂 · $0）、名額 + 倒數提示
- **Pain / 探索** — 引導訪客諗吓自己整到網頁可以用嚟做咩
- **Benefits** — 四個學員將帶走嘅好處 + CTA（呼應 16 個構思）
- **Ideas** — 16 個網站構思（4 大分類，`<details>` 摺疊式）
- **Speaker** — 導師介紹（Ambrose Cheng）
- **Testimonials** — 學員心聲
- **Lead Form** — 留位表格（前端 demo，未連接後端），表格上方有黃先生見證卡做最後推力
- **Footer** — 天際線 banner 圖 + 經文
- **Sticky CTA**（手機版）

## 設計系統

| 項目 | 數值 |
|---|---|
| 主色 Berry | `#1B2A4A` |
| 輔色 Rose/Teal | `#14a89f` |
| 背景 | `#ffffff` |
| 字體 | Noto Sans TC / PingFang TC / Microsoft JhengHei（中文），Cambria / Georgia（標題） |

## 響應式設計（Mobile-first）

CSS 採用 mobile-first 寫法：

- **Base styles**（無 media query）— 針對細螢幕（手機），單欄佈局
- **`min-width: 640px`** — 容器加闊，卡片內距增加
- **`min-width: 860px`** — Hero 留白增加、Benefits 變 2 欄 grid、Testimonials 變 3 欄 grid、Sticky CTA 隱藏（改用 inline CTA）
- **`min-width: 1200px`** — Benefits 變 4 欄，容器闊度上限 1180px

## 活動資訊（目前設定）

- 日期：2026年11月8日（星期日）
- 時間：上午10:30
- 地點：Chandler's Ford Library, Oakmount Road, Chandler's Ford, Eastleigh, SO53 2LH
- 費用：完全免費

如活動資訊有變，請搜尋並更新以下位置：
- 全站 CTA 按鈕文字（`免費攞《兩小時建站行動計劃》`，Hero / Benefits / Sticky CTA 三處已統一，改一處要三處都改）
- Lead Form 嘅 `<p class="info">` 同 `.info-pills`
- Hero 同 Lead Form 嘅名額/緊迫性文字（`Chandler's Ford Library 場地得 20 個位`）
- 倒數天數 `<script>` 入面嘅 `target = new Date('2026-11-08T00:00:00')`（同 Hero 顯示嘅日子要一致，否則倒數會計錯）

## 開發備註

- 天際線圖片已經 crop 走頂部空白，以 base64 內嵌喺 `.footer-banner` 嘅 `<img>` tag 入面
- 表格提交只係前端 demo（`onsubmit` 改變按鈕文字），未連接任何後端／API
- Lead Form 用 **電郵地址**（`type="email"`）收集聯絡方式，唔再用電話／WhatsApp
- 「你最想用網頁做咩？」改為非必填下拉選單（`<select>`），對應 16 個構思分類，降低填表門檻
- 頁面底部有一段 vanilla JS，用嚟計算並顯示距離活動日期仲有幾多日（`#days-left`）；除此之外全站冇任何 JS framework 或外部依賴
- 所有文案為繁體中文（粵語口語），如需英文版本須另行翻譯

## 如何本機預覽

直接用瀏覽器打開 `index.html` 即可，毋須安裝任何工具或執行 build 步驟。
