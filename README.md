# PBAIH｜智慧醫療大數據實作與分析

臺北醫學大學 智慧醫療學士學位學程　1151 學期（Practical Big data Analysis in Intelligent Healthcare）

本 repo 提供課程實作單元的 Colab notebook 與練習資料，可直接在 Google Colab 開啟，不需要安裝任何東西。

> 目前收錄 **PBAIH11（非靶向代謝體資料前處理）** 與 **PBAIH12（代謝物辨識）**，授課教師：王三源。課程其他單元的教材由各單元的負責教師提供，不在這個 repo。

## PBAIH11　非靶向代謝體資料前處理

從 LC-MS 原始檔，一路做到可以拿去做統計的分析矩陣。

| 實作 | 內容 | 開啟 |
|---|---|---|
| 實作一 | 從 mzML 原始檔到特徵表（pyopenms：特徵偵測、跨樣本對應、blank 過濾） | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/wang3yuan/PBAIH/blob/main/notebooks/PBAIH11A_raw_to_features.ipynb) |
| 實作二 | 從特徵表到分析矩陣（QC 過濾、缺值、漂移校正、PQN、轉換與縮放、PCA 前後比較） | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/wang3yuan/PBAIH/blob/main/notebooks/PBAIH11B_features_to_matrix.ipynb) |
| 作業 | 個人作業：前處理決策與敏感度分析（參數敏感度、流程比較、批判性解讀；最後附 GenAI 使用說明） | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/wang3yuan/PBAIH/blob/main/homework/PBAIH11_HW.ipynb) |

### 參考解答

實作一、實作二的練習題都有參考解答，放在 [`solutions/`](solutions/)。**請先在上面的 notebook 自己試**，卡住了再對照解答。解答與練習版的差別只在練習題的空格（`____`）已填好。作業沒有提供解答。

| 實作 | 開啟 |
|---|---|
| 實作一　參考解答 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/wang3yuan/PBAIH/blob/main/solutions/PBAIH11A_raw_to_features_solution.ipynb) |
| 實作二　參考解答 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/wang3yuan/PBAIH/blob/main/solutions/PBAIH11B_features_to_matrix_solution.ipynb) |

**上課一開始請先執行 notebook 的 Part 0**（安裝套件、下載資料），趁它在跑的時候聽老師開場。實作一的 Part 0.1 說明下載失敗時怎麼辦。

## PBAIH12　代謝物辨識

上一單元得到可做統計的特徵表之後，這一單元回答「這個 feature 是誰」：只有 m/z 和同位素能做到什麼，MS/MS 怎麼取得，怎麼和公開譜庫比對，為什麼高分不等於對。

| 實作 | 內容 | 開啟 |
|---|---|---|
| 實作一 | 認識 MS/MS 與 MS1 線索（一個 m/z 有幾個候選、理論同位素分布、手算 cosine、比較真實的譜） | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/wang3yuan/PBAIH/blob/main/notebooks/PBAIH12A_ms2_and_ms1_clues.ipynb) |
| 實作二 | 譜庫比對與假命中（leave-one-contributor-out、門檻與匹配峰數、加權比較、失敗案例） | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/wang3yuan/PBAIH/blob/main/notebooks/PBAIH12B_library_search_false_hits.ipynb) |
| 作業 | 個人作業：這個高分的命中可信嗎？（依學號抽 3 張未知譜，設門檻、判讀、對照答案；約 1 小時） | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/wang3yuan/PBAIH/blob/main/homework/PBAIH12_HW.ipynb) |

**每一份 notebook 都要各自執行一次 Part 0**（Colab 的每份 notebook 是獨立的執行環境）。Part 0 會安裝 `matchms==1.0.0`、下載 [Releases `data-v2`](https://github.com/wang3yuan/PBAIH/releases/tag/data-v2) 的 `PBAIH12_data.zip`（約 10 MB）；安裝後如果要你重新啟動工作階段，照做後直接執行 Part 0-b。

### 參考解答

實作一、實作二的練習題都有參考解答，放在 [`solutions/`](solutions/)。**請先在上面的 notebook 自己試**，卡住了再對照解答。解答與練習版的差別只在練習題的空格（`____`）已填好。

| 實作 | 開啟 |
|---|---|
| 實作一　參考解答 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/wang3yuan/PBAIH/blob/main/solutions/PBAIH12A_ms2_and_ms1_clues_solution.ipynb) |
| 實作二　參考解答 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/wang3yuan/PBAIH/blob/main/solutions/PBAIH12B_library_search_false_hits_solution.ipynb) |

## 執行環境

- Google Colab（建議）。PBAIH11 的 Part 0 會安裝 `pyopenms==3.6.0`，PBAIH12 的 Part 0 會安裝 `matchms==1.0.0`；其餘套件使用 Colab 內建版本：pandas 2.2.3、scipy 1.16.3、scikit-learn 1.6.1、statsmodels 0.15.0、matplotlib 3.10.0、seaborn 0.13.2。
- 在 Python 3.12（macOS）上以相同版本驗證過；Colab（Linux）請以實際執行為準。

## 資料

| 資料 | 用於 | 位置 | 來源與授權 |
|---|---|---|---|
| Sacurine toy set（裁切版：12 個 mzML＋樣本中繼資料） | 實作一 | [`data/PBAIH11/sacurine_cropped/`](data/PBAIH11/sacurine_cropped/)（12 個 mzML 與樣本中繼資料，約 115 MB）。notebook 為了下載快，改下載 [Releases `data-v1`](https://github.com/wang3yuan/PBAIH/releases/tag/data-v1) 的 `sacurine_cropped.zip`（約 46 MB，內容相同） | Zenodo [10130758](https://zenodo.org/records/10130758)（原研究 MetaboLights MTBLS404），**CC BY 4.0**。已裁切為 m/z 70–600、RT 60–1000 s 並重新壓縮；未做其他修改 |
| MTBLS79 直接注入質譜特徵表 | 實作二 | [`data/PBAIH11/Dataset07__SFPM.xlsx`](data/PBAIH11/Dataset07__SFPM.xlsx) | MetaboLights [MTBLS79](https://www.ebi.ac.uk/metabolights/MTBLS79)，EMBL-EBI 使用條款。未修改 |
| MassBank 2026.11 學生子集（只含 CC BY／CC0 的 MS/MS 紀錄） | PBAIH12 實作一、二 | [Releases `data-v2`](https://github.com/wang3yuan/PBAIH/releases/tag/data-v2) 的 `PBAIH12_data.zip`（內含 2 個 parquet 與 README） | MassBank/MassBank-data 2026.11，Zenodo [10.5281/zenodo.24082491](https://doi.org/10.5281/zenodo.24082491)。MassBank 的授權**逐筆標示**，本子集只收 **CC BY 4.0** 與 **CC0**，每筆保留作者、著作權與授權欄位，使用時請標示 MassBank 與各筆作者。已改寫成 parquet、強度以基峰正規化並去掉低於基峰 0.2% 的峰，並排除已棄用與非標準品確認的紀錄 |

引用 MTBLS79：Kirwan JA, Weber RJM, Broadhurst DI, Viant MR. Direct infusion mass spectrometry metabolomics dataset: a benchmark for data processing and quality control. *Sci Data* 2014;1:140012. doi:[10.1038/sdata.2014.12](https://doi.org/10.1038/sdata.2014.12)

兩份資料皆為公開資料，不含個人可識別資訊。

## 授權

- 程式碼：[MIT License](LICENSE)。
- notebook 的說明文字與教材內容：[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.zh-hant)，引用時請註明出處。
- 資料依上表各自的授權與使用條款。
