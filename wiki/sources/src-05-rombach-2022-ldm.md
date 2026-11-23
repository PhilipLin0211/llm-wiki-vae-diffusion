# Source 05: High-Resolution Image Synthesis with Latent Diffusion Models (LDM)
- **作者**：Robin Rombach, Andreas Blattmann, Dominik Lorenz, Patrick Esser, Björn Ommer (2022)
- **論文連結**：arXiv:2112.10752（即 Stable Diffusion 核心論文）
- **核心摘要**：
  1. 指出傳統像素空間擴散模型（Pixel-space Diffusion）在 $512\times 512$ 以上高解析度下訓練與推論極度耗費算力。
  2. 提出兩階段架構：第一階段訓練感知壓縮模型（Perceptual Compression, 即 **VAE**），將 $512\times 512\times 3$ 圖像壓縮 8 倍至 $64\times 64\times 4$ 潛在張量（Latent Tensor）；第二階段在低維潛在空間中訓練 U-Net 擴散模型。
  3. 引入 **Cross-Attention（交叉注意力機制）**：將文字 Prompt 經由 CLIP / Transformer 編碼為條件向量 $y$（作為 Key 與 Value），與雜訊潛在張量 $z_T$（作為 Query）融合，實現精準的文字生圖（Text-to-Image）。
