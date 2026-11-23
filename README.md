# LLM Wiki × 教學 HTML 簡報：從 VAE 到 Diffusion 的圖像生成冒險

> **115-1 TAICA《生成式 AI：文字與圖像生成的原理與實務》作業**  
> **繳交者**：台科大 人工智慧跨域科技研究所 碩一 M11552010 林宸平

## 專案簡介
本專案結合 **LLM Wiki（結構化知識庫）** 與 **Loop / Graph 驗證工作流**，先將 5 篇涵蓋「表徵學習（Embeddings）、自編碼器（Autoencoder）、變分自編碼器（VAE）、擴散模型（DDPM / Diffusion）與潛在擴散模型（Latent Diffusion / Stable Diffusion）」的核心講義與經典論文 Ingest 為結構化 Markdown Wiki，再讓 AI 依據 Wiki 條目產製零基礎友善的互動式 HTML 教學簡報。

## 目錄結構
```text
.
├── AGENTS.md                  # AI 協作憲法與 Ingest / 簡報生成檢查規則
├── README.md                  # 專案說明與部署指南
├── wiki/
│   ├── index.md               # LLM Wiki 總目錄與知識演進圖
│   ├── sources/               # 5 篇 Ingest 原始資料摘要卡
│   │   ├── src-01-taica-week11-slides.md
│   │   ├── src-02-kingma-2013-vae.md
│   │   ├── src-03-sohl-dickstein-2015-diffusion.md
│   │   ├── src-04-ho-2020-ddpm.md
│   │   └── src-05-rombach-2022-ldm.md
│   └── concepts/              # 結構化 Wiki 概念條目
│       ├── 01-embeddings-and-proxy-tasks.md
│       ├── 02-autoencoder.md
│       ├── 03-variational-autoencoder.md
│       ├── 04-diffusion-models.md
│       └── 05-latent-diffusion-models.md
└── slides/
    └── index.html             # 可直接瀏覽之互動式教學 HTML 簡報（10 頁）
```

## 如何預覽與部署至 GitHub Pages
1. **本地預覽**：直接雙擊開啟 `slides/index.html`，可使用鍵盤 `←` / `→` 或點擊畫面下方按鈕切換投影片。
2. **GitHub Pages 部署**：
   - 將本資料夾推送至公開 GitHub Repository（例如 `llm-wiki-image-gen-slides`）。
   - 前往 `Settings -> Pages -> Build and deployment`，選擇 `Deploy from a branch` -> `main` / `/ (root)`。
   - 即可透過 `https://<你的帳號>.github.io/<repo名稱>/slides/index.html` 線上瀏覽簡報（亦可將 `slides/index.html` 複製一份至根目錄或建立首頁連結）。
