# 04. 擴散模型（Diffusion Models / DDPM）

## 一句話白話定義
**Diffusion Model** 其實就是一種特殊的 Autoencoder——只不過它的「壓縮（Encoder）」是靠數學公式一步步撒雜訊，而「解壓縮（Decoder）」是讓 AI 學會一步步把雜訊擦乾淨！

## 核心直覺與運作機制
- **Encoder 不用學，用算的！**：
  - 從原圖 $x_0$ 開始，每次加一點點高斯雜訊：$\alpha_t = 1 - \beta_t$，$x_t = \sqrt{\alpha_t}x_{t-1} + \sqrt{1-\alpha_t}\epsilon_{t-1}$ `[[src-01, src-03]]`。
  - 利用連乘技巧 $\bar{\alpha}_t = \prod_{i=1}^t \alpha_i$，甚至能一秒算出任意第 $t$ 步的雜訊圖：$x_t = \sqrt{\bar{\alpha}_t}x_0 + \sqrt{1-\bar{\alpha}_t}\epsilon$，加到最後 $x_T$ 就是純粹的常態分佈亂碼 `[[src-01, src-04]]`。
- **Decoder 是 U-Net 除噪專家**：
  - 直接從純雜訊一步還原成原圖太難了，因此我們訓練一個 U-Net 模型 $\epsilon_\theta$，專心預測「這張圖裡摻了多少雜訊 $\epsilon$」`[[src-01, src-04]]`。
  - 生成時，只要從隨機雜訊 $z$ 出發，重複 $N$ 次「預測雜訊 $\rightarrow$ 減掉一點雜訊（Scheduler 控制步幅）」，清晰圖像就會慢慢浮現 `[[src-01]]`。

## 解決了什麼痛點？（與前代模型對比）
- **畫質與多樣性雙贏**：透過「多步漸進式去噪（Iterative Denoising）」拆解高難度生成任務，細節遠勝 VAE，訓練穩定度也遠勝容易崩潰的 GAN `[[src-01, src-04]]`。
- **遺留的新痛點**：如果直接在 $512\times 512$ 的高解析度像素上反覆跑幾十次 U-Net，運算量會大到一般電腦根本跑不動 `[[src-05]]`。

## 延伸閱讀與 Wiki 關聯
- 下一站：如何把 VAE 和 Diffusion 合體解決算力瓶頸？請見 [[05-latent-diffusion-models]]。
