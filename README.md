# Project E.X.I.T. — Game Design Wiki

Project E.X.I.T. 是一個「AI 驅動 2D 撤離生存遊戲」的開發知識網站。

本網站以 `AGENTS.md` 作為開發規範，統一管理頁面結構、命名方式、視覺風格與內容格式，並支援後續新增遊戲系統、AI 模組、地圖、NPC 與開發紀錄。

## Live Site

https://s711433116-ui.github.io/project-exit-wiki_HW10/

## Repository

https://github.com/s711433116-ui/project-exit-wiki_HW10

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

以新增 `Combat System` 為例，`AGENTS.md` 已定義以下處理方式：

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
7. 部署完成後確認首頁與各內容頁皆可正常瀏覽。


## Extension Example

### Medical Center 頁面範例

`Medical Center` 屬於 World / Map Page，依規範建立：

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

透過固定的 Page Type 與內容模板，新頁面可沿用既有結構與樣式持續擴充。
