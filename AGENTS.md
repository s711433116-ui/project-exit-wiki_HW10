# AGENTS.md

## 1. Project Overview

Project E.X.I.T. Game Design Wiki 是一個用來整理「AI 驅動 2D 撤離生存遊戲」之遊戲設計、AI 系統、世界觀與開發進度的靜態網站。

本專案的重點不只是完成目前頁面，而是建立一套可以長期延伸的網站規範。AI 在修改或新增內容前，必須先閱讀本文件，並依照既有結構、視覺與內容規則工作。

---

## 2. Project Goals

1. 清楚呈現 Project E.X.I.T. 的遊戲設計與 AI 架構。
2. 讓不同頁面保持一致的資訊結構與視覺風格。
3. 讓 AI 能依規則新增 Game System、AI System、World、NPC、Map 或 Development 頁面。
4. 保持網站為純靜態 GitHub Pages 可部署專案。
5. 避免為單一頁面加入不必要的新框架或破壞全站一致性。

---

## 3. Language Rules

- 主要內容使用台灣繁體中文。
- 技術名稱可保留英文，例如 AI Director、RAG、Tool Use、Planning、Reflection、Game State。
- 避免中國大陸慣用詞與簡體字。
- 標題要短且明確。
- 技術說明應具體，不使用空泛宣傳語。
- 未確定的期末功能必須標示為「規劃」、「預計」或「Planned」，不可寫成已完成。

---

## 4. Visual Style

網站定位為「遊戲開發 Wiki + 生存終端介面」，不得改成可愛、明亮或一般企業網站風格。

### Core visual rules

- 深灰藍背景。
- Cyan 為主要強調色。
- Amber 表示警告、風險或 Prototype。
- Green 表示完成、可用或 Game Layer。
- Purple 表示 AI / Agent / Planned 類功能。
- 卡片使用圓角、細邊框與低強度陰影。
- 使用大量留白，不塞滿資訊。
- 不使用花俏動畫。
- 不新增外部 UI framework。

### Existing color variables

必須優先使用 `/css/style.css` 中的 CSS variables：

- `--bg`
- `--panel`
- `--line`
- `--text`
- `--muted`
- `--cyan`
- `--amber`
- `--red`
- `--green`
- `--purple`

不得在單一頁面自行建立另一套配色。

---

## 5. Project Structure

```text
project-exit-wiki/
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

### Folder rules

- 首頁固定為 `/index.html`。
- 所有內容頁放在 `/pages/`。
- 全站共用樣式放在 `/css/style.css`。
- 全站共用 JavaScript 放在 `/js/main.js`。
- 圖片放在 `/assets/images/`。
- 不在根目錄任意新增內容頁。

---

## 6. File Naming Rules

HTML 內容頁檔名：

- 全小寫。
- 使用 kebab-case。
- 不使用空格。
- 不使用中文檔名。
- 名稱直接表達內容。

### Correct

- `combat-system.html`
- `medical-center.html`
- `doctor-npc.html`
- `rag-npc.html`

### Incorrect

- `CombatSystem.html`
- `combat_system.html`
- `戰鬥系統.html`
- `page1.html`

圖片同樣使用 lowercase kebab-case。

---

## 7. Page Types

新增頁面前，先判斷屬於哪一種 page type。

### 7.1 System Page

適用：
- Combat System
- Inventory System
- Extraction System
- AI Director
- RAG NPC
- Reflection Agent

固定內容：

1. Overview
2. Purpose
3. How It Works
4. Workflow / Diagram
5. Example
6. Related Systems

### 7.2 World / Map Page

適用：
- Research Lab
- Medical Center
- Industrial Zone

固定內容：

1. Overview
2. Background
3. Environment
4. Resources
5. Threats
6. Related Missions

### 7.3 NPC Page

固定內容：

1. Character Overview
2. Role
3. Personality
4. Gameplay Function
5. Known Information
6. AI Prompt Rules
7. Related Quests

### 7.4 Development Page

適用：
- Roadmap
- Dev Log
- Technical Notes

可依內容調整，但必須維持全站 Header、Breadcrumb、Hero、主要 Content Layout 與 Footer。

---

## 8. Page Template Rules

所有 `/pages/*.html` 頁面必須包含：

1. 共用 Site Header。
2. Breadcrumb。
3. Page Hero。
4. `content-layout`。
5. 左側 TOC（內容超過三個段落時）。
6. 主內容 article。
7. Related Systems 或 Related Content。
8. 共用 Footer。
9. `/js/main.js`。

頁面應優先沿用以下 class：

- `.container`
- `.page-hero`
- `.breadcrumb`
- `.kicker`
- `.lead`
- `.content-layout`
- `.toc`
- `.article`
- `.card`
- `.grid`
- `.diagram`
- `.notice`
- `.actions`
- `.btn`

禁止複製一份新的全站 CSS 到 HTML 內。

---

## 9. Navigation Rules

新增頁面後，AI 必須判斷頁面重要程度。

### Primary pages

如果屬於主要專案功能，可加入 Header navigation。

Header navigation 不應超過 6 個主要項目。

### Secondary pages

若為單一 NPC、單一地圖或細部系統：
- 不必加入全站 Header。
- 必須從相關頁面或首頁卡片可到達。

### Every new page must

- 至少有一個站內入口連到該頁。
- 至少有一個返回相關頁面的連結。
- 確認相對路徑正確。

---

## 10. Content Rules

### Game facts

目前網站主要是「設計規格」而非完成遊戲。

因此：
- 尚未完成的功能使用「預計」、「規劃」、「MVP」、「Planned」。
- 不得自行宣稱某功能已實作完成。
- 不自行增加未定案的武器、NPC、地圖數量或精確數值。

### AI explanations

AI 技術必須說明「為什麼需要」及「在遊戲中負責什麼」。

不要只列技術名稱。

例如：

不建議：
> 本專案使用 RAG、Planning、Reflection。

建議格式：
> RAG 用於讓 NPC 在回答世界觀問題前先檢索遊戲知識庫，降低憑空生成與角色資訊不一致。

---

## 11. Diagram Rules

流程圖優先使用 HTML + CSS 元件，不依賴外部圖片。

規則：
- 使用 `.diagram`、`.diagram-row`、`.diagram-box`。
- AI 元件使用 `.ai`。
- Game / State 元件使用 `.game`。
- 風險與條件使用 `.warn`。
- 流程由左至右。
- 單張圖避免超過 6 個主要節點。
- 如果流程太複雜，拆成兩張圖。

---

## 12. CSS Rules

- 優先重用既有 class。
- 共用樣式只能修改 `/css/style.css`。
- 不加入 Bootstrap、Tailwind 或其他 CSS framework。
- 不使用 `!important`，除非有明確理由。
- 新增 CSS variable 前先確認現有變數無法表達需求。
- 必須維持 mobile breakpoint 的可讀性。
- 不使用固定寬度造成手機水平溢出。

---

## 13. JavaScript Rules

目前 JavaScript 僅負責：
- Mobile navigation。
- Active navigation。
- Back-to-top。
- Scroll reveal。
- Footer year。

新增 JS 時：
- 優先放 `/js/main.js`。
- 不為純文字頁增加不必要 JS。
- 不加入大型 framework。
- 頁面在 JS 失效時仍應可閱讀。

---

## 14. Accessibility Rules

AI 修改頁面時必須：
- 保持正確 heading hierarchy。
- 導覽使用 `<nav>`。
- 主要內容使用 `<main>`。
- 圖片必須有 `alt`。
- Button 必須有可理解的文字或 `aria-label`。
- 不只依顏色傳達資訊。
- 文字與背景維持足夠對比。

---

## 15. Adding a New Page

新增頁面時，AI 必須依以下順序工作：

1. 閱讀本 `AGENTS.md`。
2. 判斷 Page Type。
3. 決定 kebab-case 檔名。
4. 建立於 `/pages/`。
5. 複用既有 Header / Footer / CSS / JS。
6. 依該 Page Type 填入固定內容結構。
7. 加入至少一個站內入口。
8. 加入 Related Systems / Related Content。
9. 檢查相對路徑。
10. 檢查桌面與手機版。
11. 檢查未完成項目是否被錯寫成已完成。
12. 不修改與任務無關的頁面。

---

## 16. Example Extension Task

範例任務：新增 Combat System 頁面。

執行規則：

1. 建立 `/pages/combat-system.html`。
2. 使用 System Page 模板。
3. 包含：
   - Overview
   - Purpose
   - How It Works
   - Workflow
   - Example
   - Related Systems
4. 沿用既有深色視覺與 CSS classes。
5. 不自行建立另一套 CSS。
6. 在 `gameplay.html` 的 Related Systems 或適當位置加入 Combat System 連結。
7. 如果它成為主要功能，再評估是否需要加入首頁卡片；不要直接塞進 Header。
8. 檢查所有路徑。

---

## 17. AI Modification Checklist

每次完成修改前，AI 必須自我檢查：

- [ ] 是否遵守繁體中文規則？
- [ ] 是否使用正確 Page Type？
- [ ] 檔名是否為 lowercase kebab-case？
- [ ] 是否沿用現有視覺風格？
- [ ] 是否重用既有 CSS？
- [ ] 是否保留 Header / Footer？
- [ ] 新頁面是否可由站內其他頁面到達？
- [ ] Related Systems 是否正確？
- [ ] 相對路徑是否正確？
- [ ] 是否將 Planned 功能誤寫為完成？
- [ ] 手機版是否仍可閱讀？
- [ ] 是否只修改任務需要的檔案？

---

## 18. Definition of Done

一個新增或修改任務只有在以下條件都滿足時才算完成：

1. 網頁可以正常開啟。
2. 所有站內連結可到達正確頁面。
3. 視覺與現有頁面一致。
4. 內容符合對應 Page Type。
5. 沒有明顯 broken layout。
6. 不需要另外安裝套件即可在 GitHub Pages 使用。
7. 修改內容符合本 AGENTS.md。
