# Source 03: Deep Unsupervised Learning using Nonequilibrium Thermodynamics
- **作者**：Jascha Sohl-Dickstein, Eric A. Weiss, Niru Maheswaranathan, Surya Ganguli (2015)
- **論文連結**：arXiv:1503.03585
- **核心摘要**：
  1. 首次將非平衡態熱力學中的「擴散過程」引入深度學習生成模型。
  2. 定義前向擴散過程（Forward Diffusion Process）：透過馬可夫鏈逐步向資料注入微小的受控高斯雜訊，最終將複雜資料分佈摧毀為純粹的各向同性高斯雜訊。
  3. 證明當每步擴散幅度 $\beta_t$ 足夠小時，逆向去噪過程（Reverse Process）具有與前向過程相同的函數形式（高斯分佈），因此可用神經網路學習逆向轉移機率來生成新樣本。
