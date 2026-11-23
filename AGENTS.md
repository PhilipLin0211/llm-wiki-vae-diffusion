# AGENTS.md — 圖像生成模型演進知識庫與教學簡報生產線

## 專案目的
本專案為「圖像生成模型演進（從 Embedding、AE、VAE 到 Diffusion / LDM）」的結構化 LLM Wiki 知識庫，並以此為單一事實來源（SSOT），透過驗證迴圈（Verification Loop）自動產製「讓初學者也能聽懂的互動式 HTML 教學簡報」。

## 資料夾與命名規則
- `AGENTS.md`: AI 協作規範、Ingest SOP 與簡報生成檢查清單（根目錄）。
- `README.md`: 專案總覽、GitHub Pages 部署說明與變更紀錄。
- `wiki/index.md`: 知識庫總目錄與概念關聯圖。
- `wiki/sources/src-0X-<slug>.md`: 原始資料摘要卡（至少 5 篇）。
- `wiki/concepts/<slug>.md`: 結構化概念條目（支援雙向連結與漸進式擴充）。
- `slides/index.html`: 獨立可瀏覽的教學型 HTML 簡報（支援鍵盤左右鍵與按鈕切換投影片）。

## Step 1: Wiki Ingest 規範（先討論、後生成）
1. **來源隔離**：所有概念推導必須標註 `[[src-0X]]` 來源編號，嚴禁憑空捏造未收錄的公式或論文年份。
2. **概念條目固定四段式結構**：
   - `## 一句話白話定義`（給零基礎讀者看）
   - `## 核心直覺與運作機制`
   - `## 解決了什麼痛點？（與前代模型對比）`
   - `## 延伸閱讀與 Wiki 關聯`（雙向連結至其他概念頁）
3. **增量更新檢查**：每次新增來源後，必須同步更新 `wiki/index.md` 與相關 `concepts/*.md`，不可覆蓋既有正確內容。

## Step 2: 教學 HTML 簡報生成與檢查 SOP
1. **知識溯源**：每張投影片內容皆須對應 `wiki/concepts/` 中的條目，禁止脫離 Wiki 自由發揮。
2. **初學者友善檢核（Beginner Readability Check）**：
   - 出現專有名詞（如 Latent Vector、KL 散度、U-Net）時，必須附上「生活化比喻」或白話解釋。
   - 每頁投影片文字控制在 120 字以內，搭配 SVG 架構圖或互動視覺化元件。
3. **前端單檔獨立性**：`slides/index.html` 不可依賴外部需編譯框架（如 React/Vue CLI），必須能直接雙擊開啟或部署於 GitHub Pages。
