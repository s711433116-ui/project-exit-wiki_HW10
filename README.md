# Project E.X.I.T. — Game Design Wiki

Project E.X.I.T. 是一個「AI 驅動 2D 撤離生存遊戲」的開發知識網站。

本專案不是單純完成一個網頁，而是透過 `AGENTS.md` 建立一套可重複使用的專案規範，讓 AI 未來可以依相同方式持續新增遊戲系統、AI 模組、地圖、NPC 與開發紀錄。

## Live Site

GitHub Pages 啟用後，請將網址填在這裡：

`https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/`

## Repository Structure

```text
.
├── index.html
├── pages/
│   ├── gameplay.html
│   ├── ai-director.html
│   ├── architecture.html
│   └── roadmap.html
├── css/
│   └── style.css
├── js/
│   └── main.js
├── assets/
│   └── images/
├── AGENTS.md
└── README.md
```

## Current Pages

- Home
- Core Gameplay Loop
- AI Director
- AI Architecture
- Development Roadmap

## Why AGENTS.md?

`AGENTS.md` 規範：

- 專案目的
- 網站語言
- 視覺風格
- 資料夾結構
- 檔案命名
- Page Type
- 固定頁面模板
- Navigation 規則
- CSS / JavaScript 規則
- AI 修改流程
- Definition of Done

例如未來要新增 `Combat System`，AI 讀取 `AGENTS.md` 後即可知道：

1. 建立 `/pages/combat-system.html`
2. 使用 System Page 固定模板
3. 沿用既有 CSS
4. 不建立新的視覺系統
5. 更新相關站內連結
6. 檢查 GitHub Pages 相對路徑

## Run Locally

本網站為純靜態網站，可直接開啟 `index.html`。

也可使用 Python：

```bash
python -m http.server 8000
```

然後開啟：

```text
http://localhost:8000
```

## Deploy to GitHub Pages

1. 在 GitHub 建立新的 repository。
2. 將本專案所有檔案上傳至 repository root。
3. 進入 `Settings` → `Pages`。
4. Source 選擇 `Deploy from a branch`。
5. Branch 選擇 `main`，folder 選 `/ (root)`。
6. 儲存後等待 GitHub Pages 建立公開網址。
7. 將公開網址填回本 README 與作業繳交內容。

## Assignment Submission Checklist

- [ ] 專案簡介
- [ ] GitHub Repository 連結
- [ ] GitHub Pages 網頁連結
- [ ] `AGENTS.md`
- [ ] 延伸性說明
- [ ] 網站可正常瀏覽
- [ ] 至少一個內容頁
- [ ] Repository 為公開可讀

## Extension Example

如果未來要增加 `Medical Center`：

AI 應先讀取 `AGENTS.md`，判斷它屬於 World / Map Page，建立：

```text
pages/medical-center.html
```

並依序加入：

- Overview
- Background
- Environment
- Resources
- Threats
- Related Missions

因此，新內容不需要每次重新設計網站結構，可以持續沿用既有規則擴充。
