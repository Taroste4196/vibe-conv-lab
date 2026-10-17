# CONV LAB · 卷積神經網路視覺實驗室

互動式網頁作業：用單一 `index.html` 學習 CNN（卷積神經網路）的核心概念。純前端、無外部相依，開啟即可使用。

`claude.ai`

## 題目發想

參考 Vibe2026 範例（GenAI Odyssey、Ameba Robo Odyssey）的「全螢幕學習航線 → 互動實驗 → 任務」結構，但主題改為課程中的**電腦視覺基礎**，並讓每一關都能「動手玩」而不只是閱讀：

| 關卡 | 互動內容 |
|---|---|
| 01 PIXELS | 在 32×32 畫布上繪圖／換圖案／上傳照片，滑鼠移動即時顯示附近像素值 |
| 02 KERNEL | 3×3 視窗逐點滑動，顯示「區塊 × kernel = 乘積 → Σ」的完整計算，輸出圖逐點掃出 |
| 03 FILTER LAB | 自訂 3×3 kernel，調整 stride／padding／ReLU，即時看輸出尺寸公式與結果 |
| 04 POOLING | Max／Average、2/3/4 視窗，滑鼠懸停顯示對應區塊與運算 |
| 05 PIPELINE | Conv → ReLU → Pool，4 個特徵偵測器（垂直／水平／兩種斜線）的反應強度 |
| 06 TRAIN | 隨機初始化的 kernel 用梯度下降學會 Sobel／Blur 等目標，即時看 Loss 曲線與學習率影響 |

每關最後有一題測驗（Mission），答對後進度會儲存在瀏覽器（localStorage），可從 JOURNEY LOG 查看或重設。

## 提示詞紀錄（與 Claude 的產生過程）

1. 提供作業說明、範例網站與 Vibe2026 範本（`Prompt-AI_ROBOT_ODYSSEY.txt`）。
2. 提示詞：

```
參考 Vibe2026 範本與兩個範例網站（AI-course、EdgeAI-AmebaPro2），
自訂一個不同的題目，做成互動式網頁並存成單一 index.html，
風格延續「全螢幕學習航線 + 互動實驗 + 任務」，內容為繁體中文。
題目：CNN 卷積神經網路視覺實驗室，包含像素、卷積、濾鏡、池化、特徵管線、kernel 訓練六個關卡，
每關有互動實驗與一題測驗，進度存在 localStorage。
```

3. 以 Playwright 實測：無 console 錯誤；斜線偵測器方向正確；訓練關卡 Loss 可收斂至 < 1e-4；手機寬度版面正常。

## 部署到 GitHub Pages

1. 在 GitHub 建立新 repo（例如 `vibe-conv-lab`，設為 Public）。
2. 上傳 `index.html`（網頁 Add file → Upload files，或 `git add/commit/push`）。
3. Repo → **Settings → Pages** → Source 選 **Deploy from a branch**，Branch 選 `main`、資料夾 `/ (root)` → Save。
4. 約 1 分鐘後網址為 `https://<你的帳號>.github.io/<repo 名稱>/`。
