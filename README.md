# 校園折射震測科學建模與第 4 炮實測分析平台

> **台北市立大學 地球物理通論課程 ‧ 北市大圖書館後方測線（202610_UTELS）**  
> 施測日期：2026-10-07 ｜ 分析對象：第 4 炮（104 炮點，SEG-2 / 104.dat）

本專案將野外折射震測之硬體系統、波動物理原理、實測 24 道數據以及 CER 科學論證整合成一個開箱即用、富互動性且支援深淺色主題切換的單頁 Web 應用程式。

---

## 🌟 核心互動功能

1. **第 4 炮互動式走時曲線圖（t–x Diagram）**
   - 繪製 24 道受波器初達時間，自動標註「高可靠 P 波初達」、「雷利表面波」、「近炮飽和削頂道」。
   - 包含最小平方擬合視速度線（近支距段 612 m/s）、理論折射層趨勢線（550 m/s）與表面波線（106 m/s）。
   - 支援「僅看右翼（17道，0~34m）」與「全測線雙翼（24道，-12~+34m）」即時切換。

2. **互動式兩層地下波傳與速度結構實驗室（Subsurface Raypath Simulator）**
   - HTML5 Canvas 動態模擬地層剖面、24 支受波器陣列與 12.0m 震源。
   - 動態調整上層速度 $V_1$、下層速度 $V_2$ 與截距時間 $t_i$。
   - 即時計算並可視化：
     - 風化層厚度 $h$（截距時間法公式）
     - 臨界入射角 $\theta_c = \arcsin(V_1 / V_2)$
     - 交叉距離 $x_{\text{cross}}$
     - 直達波與折射頭波之粒子傳播動畫。

3. **訊號品質與幾何擴散衰減分析**
   - 視覺化展示各道峰值振幅與雜訊 RMS（對數尺度）。
   - 深入剖析近炮道飽和（CH5～CH8）、遠支距表面波掩蓋 P 波、AIC 速度視窗陷阱等真實資料限制。

4. **CER 科學論證與 12 炮互換原理（Reciprocity）**
   - 主張（Claim）、證據（Evidence）、推理（Reasoning）結構化展現。
   - 35 組互換配對（中位時間差僅 1.5 ms）幾何一致性檢驗。

5. **24 道完整實測數據庫與 CSV 匯出**
   - 支援即時分類篩選（高可靠 / 表面波 / 飽和）及一鍵匯出 CSV 檔案。

---

## 🚀 GitHub Pages 一鍵部署步驟

本專案完全零配置（Zero Config），所有樣式、資料庫與邏輯均整合於 `index.html`，無需安裝 Node.js 或執行任何建置步驟：

### 方法 A：透過 GitHub 網頁直接上傳（最簡便）

1. 登入 [GitHub](https://github.com/) 並點選右上角 **New repository** 建立新儲存庫（設為 **Public**）。
2. 在儲存庫主頁點選 **Add file** -> **Upload files**。
3. 將本資料夾中的 `index.html`、`README.md`、`.nojekyll` 拖曳上傳，並點選 **Commit changes**。
4. 點選儲存庫頂部的 **Settings** 標籤頁。
5. 在左側側邊欄點選 **Pages**。
6. 在 **Build and deployment** 下方的 **Branch** 選擇 `main`（或 `master`），資料夾維持 `/ (root)`，點選 **Save**。
7. 約等待 30 ～ 60 秒重新整理頁面，即可看到綠色橫條提示您的專案已發布，網址為：  
   `https://<你的GitHub帳號>.github.io/<儲存庫名稱>/`

### 方法 B：透過 Git 命令列

```bash
git init
git add index.html README.md .nojekyll
git commit -m "feat: deploy campus seismic refraction web app"
git branch -M main
git remote add origin https://github.com/<你的GitHub帳號>/<儲存庫名稱>.git
git push -u origin main
```

隨後同樣至 GitHub 儲存庫的 **Settings** -> **Pages** 啟用發布即可。

---

## 📁 檔案清單說明

- `index.html`：主網頁檔案（包含完整互動介面、圖表、物理公式與動態模擬引擎）。
- `.nojekyll`：通知 GitHub Pages 略過 Jekyll 引擎，直接發布靜態檔案。
- `refraction_shot4_分析報告.txt`：第 4 炮原始分析報告與各道參數。
- `===================================.txt`：校園折射震測儀器與原理完整整理報告。
- `README.md`：專案說明與部署指南。
