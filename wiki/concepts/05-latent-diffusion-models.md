# 05. 潛在擴散模型（Latent Diffusion Models, LDM / Stable Diffusion）

## 一句話白話定義
**Stable Diffusion (LDM)** 就是「先用 VAE 把大圖縮小 8 倍成精華壓縮包，在壓縮包裡做 Diffusion 除噪畫圖，最後再用 VAE 放大回高清大圖」的天才架構。

## 核心直覺與運作機制
1. **VAE 空間壓縮（縮小 8 倍）**：先訓練好一組 VAE，把 $512\times 512$ 的圖片壓縮成 $64\times 64$ 的 Latent 張量，運算量瞬間減少數十倍 `[[src-01, src-05]]`。
2. **文字條件控制（CLIP + Cross-Attention）**：
   - 使用 CLIP 等 Transformer 模型把人類輸入的 Prompt（例如 `"a rabbit wearing a rabbit ear hat"`）轉成 $77\times 768$ 的文字特徵向量 $y$ `[[src-01]]`。
   - 透過 Transformer 的 **Cross-Attention** 機制（文字向量當作 $K, V$，雜訊潛在張量當作 $Q$），在每一步 U-Net 去雜訊時引導畫面長出符合文字描述的內容 `[[src-01, src-05]]`。
3. **VAE Decoder 還原**：經過 Scheduler 重複 $N$ 次去噪後，交給 VAE Decoder 把 $64\times 64$ 潛在張量還原為 $512\times 512$ 高清圖像 `[[src-01]]`。

## 解決了什麼痛點？（與前代模型對比）
- **打破算力高牆**：讓個人消費級 GPU 也能在幾秒內生成高解析度圖像，引爆開源 AI 繪圖革命 `[[src-05]]`。
- **破除常見迷思**：很多人以為 VAE 只是 Stable Diffusion 的外掛畫質濾鏡（如預設 / EMA / MSE 版本切換），但事實上 **沒有 VAE 提供壓縮的 Latent Space，Stable Diffusion 根本無法運作** `[[src-01]]`。

## 延伸閱讀與 Wiki 關聯
- 回顧起點：[[01-embeddings-and-proxy-tasks]] $\rightarrow$ [[03-variational-autoencoder]] $\rightarrow$ [[04-diffusion-models]]
