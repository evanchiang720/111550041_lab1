# 服裝風格分類

## 研究問題
使用多種機器學習模型分類不同風格的服裝，並針對模型的不同參數與方法進行實驗。主要包括：
- **CNN 模型**：使用CNN訓練，測試不同圖片尺寸對準確率的影響。
- **SVM 模型**：利用SVM訓練，測試不同kernel函數對準確率的影響。
- **K-means 模型**：利用K-means分群，測試不同的特徵提取工具與維度降低工具對準確率的影響。

## 資料集說明

### 1. 資料來源與概述
- **資料來源**：所有圖片皆來自Google圖片，透過爬蟲下載。
- **搜尋方式**：根據不同服裝類型的名稱進行搜尋，為了增加同一類圖片的多樣性，每個類別採用兩個關鍵字搜尋，例如「運動服裝」與「體育服裝」的搜尋結果歸為「運動體育服裝」。

### 2. 資料格式與搜尋連結
- **圖片格式**：均為`.jpg`格式
- **搜尋連結**：使用以下連結進行圖片搜尋：https://www.google.com/search?q={query}&tbm=isch

### 3. 圖片類別
資料共分為六個服裝類別：
1. 前衛造型服裝
2. 商務工作服裝
3. 運動體育服裝
4. 居家休閒服裝
5. 宴會婚禮服裝
6. 傳統古典服裝

### 4. 爬蟲流程與資料處理
**爬蟲原理**：
- 構建搜尋連結
- 使用Selenium WebDriver抓圖片
- 下載圖片

**圖片抓取數量**：每個類別初步爬取3000張

**自動篩選**：
- 設定圖片大小至少為90x90
- 排除Base64編碼的圖片
- 篩選後每個類別約剩1000張圖片

**人工處理**：
- 對自動篩選後的圖片進行人工審核
- 刪除不符合類別標籤的圖片
