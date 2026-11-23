# Source 01: TAICA《生成式 AI》第 11 週課程簡報
- **作者**：政治大學應用數學系 蔡炎龍 教授
- **類型**：課程講義（75 頁）
- **核心摘要**：
  1. 以「函數學習機 $f_\theta$（呆萌型 AI 機器人）」貫穿全篇，說明任何隱藏層輸出皆可視為輸入的特徵代表向量（Embedding / Latent Vector）。
  2. 透過「八哥鳥分類」與「Word2Vec (CBOW / Skip-Gram)」解釋如何用容易取得資料的**代理任務（Proxy Task）**訓練出 Encoder。
  3. 指出傳統 Autoencoder 的 Latent Space 缺乏連續結構（隨便取相近點解碼可能無意義），進而引出 VAE 學習平均值 $\mu$ 與標準差 $\sigma$ 的設計。
  4. 揭示 Diffusion Models 的核心洞見：**「Diffusion 基本上就是 Autoencoder，只是前面的 Encoder 是用數學公式算出來的（逐步加高斯雜訊），而 Decoder 是神經網路學出來的（逐步預測並減去雜訊）。」**
  5. 釐清常見誤區：Stable Diffusion（LDM）並非「用 VAE 提升畫質」，而是先用 VAE 將 $512\times 512$ 圖像壓縮 8 倍至 $64\times 64$ Latent Space，再於低維空間執行擴散去噪，否則計算量過大根本無法運作。
