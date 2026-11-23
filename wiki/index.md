# 圖像生成模型演進 LLM Wiki（總目錄）

本知識庫以「**從 VAE 開始的冒險旅程**」為核心脈絡，系統性收錄現代 AI 圖像生成背後的關鍵數學直覺與架構演進。

## 知識演進地圖（Concept Graph）
```text
[Proxy Tasks & Embeddings] ──▶ [Autoencoder (AE)] ──▶ [Variational Autoencoder (VAE)]
                                                                │
                                            (提供壓縮 Latent Space，解決高維運算瓶頸)
                                                                ▼
[Diffusion Models (DDPM)] ───────────────────────────▶ [Latent Diffusion Models (Stable Diffusion)]
```

## 核心概念條目（Concepts）
1. [[01-embeddings-and-proxy-tasks]] — 呆萌 AI 機器人如何透過「代理任務」學會把萬物變成特徵向量？
2. [[02-autoencoder]] — 輸入等於輸出的「自我複製」機器：Encoder 與 Decoder 的誕生與空間斷裂問題。
3. [[03-variational-autoencoder]] — 強制潛在空間服從常態分佈 $\mathcal{N}(\mu, \sigma^2)$，讓隨機採樣也能畫出合理圖像。
4. [[04-diffusion-models]] — Encoder 不用學、用算的！逐步加雜訊與 U-Net 逐步去雜訊的逆向工程。
5. [[05-latent-diffusion-models]] — 為什麼沒有 VAE 就沒有 Stable Diffusion？在 $64\times 64$ 壓縮空間中結合 CLIP 條件控制。

## 已收錄資料來源（Ingested Sources，共 5 篇）
- `src-01`: 蔡炎龍（2026）。《115-1 TAICA 生成式 AI：第 11 週 從 VAE 開始的冒險旅程》課程簡報。
- `src-02`: Kingma, D. P., & Welling, M. (2013). *Auto-Encoding Variational Bayes* (arXiv:1312.6114).
- `src-03`: Sohl-Dickstein, J., et al. (2015). *Deep Unsupervised Learning using Nonequilibrium Thermodynamics* (arXiv:1503.03585).
- `src-04`: Ho, J., Jain, A., & Abbeel, P. (2020). *Denoising Diffusion Probabilistic Models (DDPM)* (arXiv:2006.11239).
- `src-05`: Rombach, R., et al. (2022). *High-Resolution Image Synthesis with Latent Diffusion Models* (arXiv:2112.10752).
