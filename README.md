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
| 類別 | 範例圖片 |
|------|---------|
| **前衛造型服裝** | <img src="https://image1.gamme.com.tw/news2/2017/49/34/pJyRo6ael6OZrqQ.jpg" width="150"> |
| **商務工作服裝** | <img src="https://www.gentlemansgazette.com/wp-content/uploads/2016/09/Business-Casual-Mens-by-hogtownrake-Cardigan-Madder-inspired-tie-that-extends-beyond-the-waistband-with-suspenders-and-vintage-watch-768x1147.jpg" width="150"> |
| **運動體育服裝** | <img src="https://cdna.lystit.com/520/650/n/photos/underarmour/77c7016a/under-armour-black-Debardeur-En-Mesh-Imprime-Zone-Pro-Pour-Homme-Anthracite-Stream.jpeg" width="150"> |
| **居家休閒服裝** | <img src="https://s.yimg.com/ob/image/624d3be2-6e45-4d36-b4a8-5dff9d72e939.jpg" width="150"> |
| **宴會婚禮服裝** | <img src="https://g-search1.alicdn.com/img/bao/uploaded/i4/i1/2678078532/O1CN0154Bp2X2CtiE5ZV0wa_!!0-item_pic.jpg_360x360q90.jpg_.webp" width="150"> |
| **傳統古典服裝** | <img src="https://m1.aboluowang.com/uploadfile/2019/0222/20190222045852245.webp" width="150"> |

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
