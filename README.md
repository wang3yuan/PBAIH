# PBAIH｜智慧醫療大數據實作與分析

臺北醫學大學 智慧醫療學士學位學程　1151 學期（Practical Big data Analysis in Intelligent Healthcare）

本 repo 提供課程實作單元的 Colab notebook 與練習資料，可直接在 Google Colab 開啟，不需要安裝任何東西。

> 目前只收錄 **PBAIH11（非靶向代謝體資料前處理，授課教師：王三源）**。課程其他單元的教材由各單元的負責教師提供，不在這個 repo。

## PBAIH11　非靶向代謝體資料前處理

從 LC-MS 原始檔，一路做到可以拿去做統計的分析矩陣。

| 實作 | 內容 | 開啟 |
|---|---|---|
| 實作一 | 從 mzML 原始檔到特徵表（pyopenms：特徵偵測、跨樣本對應、blank 過濾） | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/wang3yuan/PBAIH/blob/main/notebooks/PBAIH11A_raw_to_features.ipynb) |
| 實作二 | 從特徵表到分析矩陣（QC 過濾、缺值、漂移校正、PQN、轉換與縮放、PCA 前後比較） | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/wang3yuan/PBAIH/blob/main/notebooks/PBAIH11B_features_to_matrix.ipynb) |

**上課一開始請先執行 notebook 的第 0 節**（安裝套件、下載資料），趁它在跑的時候聽老師開場。每個 notebook 的第 0.1 節說明下載失敗時怎麼辦。

## 執行環境

- Google Colab（建議）。第 0 節會安裝 `pyopenms==3.6.0`；其餘套件使用 Colab 內建版本：pandas 2.2.3、scipy 1.16.3、scikit-learn 1.6.1、statsmodels 0.15.0、matplotlib 3.10.0、seaborn 0.13.2。
- 在 Python 3.12（macOS）上以相同版本驗證過；Colab（Linux）請以實際執行為準。

## 資料

| 資料 | 用於 | 位置 | 來源與授權 |
|---|---|---|---|
| Sacurine toy set（裁切版：12 個 mzML＋樣本中繼資料） | 實作一 | [`data/PBAIH11/sacurine_cropped/`](data/PBAIH11/sacurine_cropped/)（12 個 mzML 與樣本中繼資料，約 115 MB）。notebook 為了下載快，改下載 [Releases `data-v1`](https://github.com/wang3yuan/PBAIH/releases/tag/data-v1) 的 `sacurine_cropped.zip`（約 46 MB，內容相同） | Zenodo [10130758](https://zenodo.org/records/10130758)（原研究 MetaboLights MTBLS404），**CC BY 4.0**。已裁切為 m/z 70–600、RT 60–1000 s 並重新壓縮；未做其他修改 |
| MTBLS79 直接注入質譜特徵表 | 實作二 | [`data/PBAIH11/Dataset07__SFPM.xlsx`](data/PBAIH11/Dataset07__SFPM.xlsx) | MetaboLights [MTBLS79](https://www.ebi.ac.uk/metabolights/MTBLS79)，EMBL-EBI 使用條款。未修改 |

引用 MTBLS79：Kirwan JA, Weber RJM, Broadhurst DI, Viant MR. Direct infusion mass spectrometry metabolomics dataset: a benchmark for data processing and quality control. *Sci Data* 2014;1:140012. doi:[10.1038/sdata.2014.12](https://doi.org/10.1038/sdata.2014.12)

兩份資料皆為公開資料，不含個人可識別資訊。

## 授權

- 程式碼：[MIT License](LICENSE)。
- notebook 的說明文字與教材內容：[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.zh-hant)，引用時請註明出處。
- 資料依上表各自的授權與使用條款。
