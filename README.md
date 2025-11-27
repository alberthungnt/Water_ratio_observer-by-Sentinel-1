# Water_ratio_observer by Sentinel-1
文本旨在使用Sentinel-1 衛星影像，應用於台灣本島範圍之監測範圍水域覆蓋率估算。

## 內容
### Part 1 - 下載衛星影像
* 衛星影像參數：
    * "type": "sentinel-1-grd",
    * "Operational mode": "IW",
    * "Resolution": "HIGH",
    * "Polarization": "DV",
    * "Orbit Direction": "DESCENDING",
    * "Polarisation channels"："VV","VH"
* 影像預處理：
    * "backCoeff": "GAMMA0_TERRAIN",
    * "orthorectify": "true",
    * "demInstance": "COPERNICUS",
    * "radiometricTerrainOversampling": 2

### Part 2 - 接合影像
* 如果監測範圍寬、高大於25公里，必須將影像切割後，方能下載。
* 若樣區可能遭裁切於多張影像中，將造成後續水域計算有誤，建議將影像接合後方能進行運算。

### Part 3 - 水域覆蓋率判釋
* 水域判釋極化：VV
* 水域判釋數位數值閾值：0.029

## 提醒
* 請將程式碼複製一份至新的colab頁面執行
* 若該段落程式碼執行時間過長，請嘗試將該段落切分成多段依序執行 ***
* 若無需將每個樣區之sar圖層分別存取，盡量將監測範圍涵蓋於單一polygon中下載衛星影像，避免各樣區影像重疊，影響覆蓋率計算 ***

## 範例
1. 臺南市七股區、將軍區鹽田  
我們使用2025年3月25日 Sentinel-1 及 Sentinel-2 影像檢視水域覆蓋範圍
![image](https://github.com/alberthungnt/Water_ratio_observer-by-Sentinel-1/blob/main/Image/20250325_%E9%B9%BD%E7%94%B0%E6%B0%B4%E5%9F%9F%E8%A6%86%E8%93%8B%E7%8E%87%E7%A4%BA%E6%84%8F%E5%9C%96.png)

2. 臺南市七股區魚塭  
我們使用2025年3月25日 Sentinel-1 影像建立魚塭水域覆蓋率
![image](https://github.com/alberthungnt/Water_ratio_observer-by-Sentinel-1/blob/main/Image/20250325_%E9%AD%9A%E5%A1%AD%E6%B0%B4%E5%9F%9F%E8%A6%86%E8%93%8B%E7%8E%87%E7%A4%BA%E6%84%8F%E5%9C%96.png)
![image](https://github.com/alberthungnt/Water_ratio_observer-by-Sentinel-1/blob/main/Image/20250325_%E9%AD%9A%E5%A1%AD%E6%B0%B4%E5%9F%9F%E8%A6%86%E8%93%8B%E7%8E%87%E7%94%A2%E5%87%BA%E7%A4%BA%E6%84%8F%E5%9C%96.png)
