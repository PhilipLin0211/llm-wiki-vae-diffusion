# Source 04: Denoising Diffusion Probabilistic Models (DDPM)
- **作者**：Jonathan Ho, Ajay Jain, Pieter Abbeel (2020)
- **論文連結**：arXiv:2006.11239
- **核心摘要**：
  1. 簡化擴散模型訓練目標，提出「讓神經網路直接預測該步驟加入的雜訊 $\epsilon_\theta(x_t, t)$」，而非直接預測乾淨原圖 $x_0$，大幅提升生成畫質與穩定度。
  2. 推導出閉式解（Closed-form）前向跳步公式：令 $\alpha_t = 1 - \beta_t$ 且 $\bar{\alpha}_t = \prod_{i=1}^t \alpha_i$，可直接由原圖 $x_0$ 一步算出任意時刻 $t$ 的雜訊圖 $x_t = \sqrt{\bar{\alpha}_t}x_0 + \sqrt{1-\bar{\alpha}_t}\epsilon$，無需逐步迭代。
  3. 結合 U-Net 架構與時間步嵌入（Time Embedding），奠定現代擴散模型的標準訓練與採樣（Iterative Denoising）範式。
