# pain_exam

台灣疼痛醫學會疼痛專科醫師考古題互動練習網站（繁體中文）。

## 立刻開始

- **線上**：在 GitHub 的 **Settings → Pages** 設定 `Deploy from a branch`，選擇 `main` 和 `/(root)`。啟用後可由 GitHub Pages 開啟網站。
- **離線**：請先 **Code → Download ZIP**，解壓縮後開啟 `index.html`。要保留 `data/` 資料夾與首頁的相對位置；只下載單獨的 `index.html` 無法載入題庫。

## 練習模式

1. **第一輪：整年度模擬考**。全部作答、交卷後才顯示官方答案與解析。
2. **第二輪：逐題即時複習**。完成該年度後解鎖，逐題作答後立即查看結果。
3. **錯題簿**。答錯自動加入，直到使用者手動標記為已熟悉。
4. **資料備份**。進度保存在瀏覽器本機儲存（localStorage），不會因為 GitHub Commit 而跨裝置同步。請定期匯出 JSON 備份。

## 題庫範圍

| 年份 | 題數 |
|---|---:|
| 民國 106～115 年 | 499 題（107 年取得的來源僅 49 題）|
| 民國 105 年（額外練習） | 50 題 |
| **合計** | **549 題** |

已匯入歷屆試卷提供的官方答案，但**尚未逐題完成醫學文獻獨立核對**。請以網站中的查證標記分辨已核對與仍待查證的內容，切勿把官方答案視為絕對正確。

## 專案結構

```text
pain_exam/
├── index.html          # 網站 UI 與功能邏輯
├── data/
│   ├── 106.js          # 106 年 50 題
│   ├── ...             # 107～115 年題庫，各自獨立
│   └── 105.js          # 額外練習 50 題
├── README.md
└── .gitignore
```

各年度 `data/年份.js` 會在頁面載入時把考題附加到 `window.PAIN_EXAM_SEEDS`，首頁再使用 `const SEEDS=window.PAIN_EXAM_SEEDS||[]`。這樣日後更新某個年度的題目或詳解，可以單獨修改對應檔案，再 Commit，不需要更新超過 1 MB 的單體 HTML。

### 日後如何修改

- 修改介面或作答流程：編輯 `index.html`。
- 修正題目、官方答案或詳解：編輯 `data/<年度>.js`。
- 可直接在 GitHub 編輯檔案、輸入 Commit message；也能使用本機 Git 或請 ChatGPT 連線後協助建立 Commit。

建議用簡潔的 Commit message：

- `fix: 修正 114 年第 6 題爭議註記`
- `feat: 新增跨年度錯題統計`
- `docs: 補充文獻查證說明`

## GitHub Pages

進入 **Settings → Pages**，在 **Build and deployment** 選擇 **Deploy from a branch**，設定 `main` 和 `/(root)`，按 **Save**。GitHub Pages 啟用後通常會提供 `https://tad820423ntu.github.io/pain_exam/` 作為網站網址，請以 Pages 設定頁顯示的正式網址為準。

## 著作權及醫學內容

原始考題和參考文獻之著作權仍屬各自權利人。本專案作為考前個人學習工具。資料中的舊版治療建議可能已過時，臨床應以現行正式指引為準。

目前 Repository 是 **Public**，GitHub 上的內容可以被公開瀏覽。
