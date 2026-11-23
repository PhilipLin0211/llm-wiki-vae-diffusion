# Source 02: Auto-Encoding Variational Bayes (VAE)
- **作者**：Diederik P. Kingma, Max Welling (2013)
- **論文連結**：arXiv:1312.6114
- **核心摘要**：
  1. 提出變分自編碼器（VAE），將原本確定性的單點編碼改為機率分佈編碼（輸出高斯分佈的均值 $\mu$ 與變異數 $\sigma^2$）。
  2. 透過 **Reparameterization Trick（重參數化技巧）** $z = \mu + \sigma \odot \epsilon$（其中 $\epsilon \sim \mathcal{N}(0, I)$），使隨機採樣過程可微分並能進行反向傳播訓練。
  3. 目標函數（ELBO）包含兩項：**重建誤差（Reconstruction Loss）**確保解碼圖片像原圖，以及 **KL 散度（KL Divergence）**將潛在分佈拉向標準常態分佈，消除潛在空間中的「空洞」。
