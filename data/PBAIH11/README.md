# PBAIH11 練習資料

- `Dataset07__SFPM.xlsx`：MetaboLights MTBLS79 的直接注入質譜（DIMS）特徵表，172 樣本 × 2488 個 m/z 峰；38 個 QC、8 個批次（7 天）；20 個牛／羊心臟組織萃取物重複測量。用於實作二。MD5：`30413b355a2163effb221eca8857ec2c`。來源：`ftp.ebi.ac.uk/pub/databases/metabolights/studies/public/MTBLS79/FILES/`；EMBL-EBI 使用條款；引用 Kirwan et al., *Sci Data* 2014;1:140012（doi:10.1038/sdata.2014.12）。
- `sacurine_cropped/`：實作一的 12 個 centroid mzML（6 個尿液樣本、3 個 pooled QC、3 個 blank；LTQ-Orbitrap、ESI 負離子）與 `sampleMetadata_12samp_completed.tsv`。來源 Zenodo [10130758](https://zenodo.org/records/10130758)（原研究 MetaboLights MTBLS404），CC BY 4.0；已裁切為 m/z 70–600、RT 60–1000 s 並重新壓縮，未做其他修改。
- 同樣的 12 個 mzML 也打包成 `sacurine_cropped.zip`（46 MB），放在 [Releases `data-v1`](https://github.com/wang3yuan/PBAIH/releases/tag/data-v1)：notebook 下載一個檔案比下載 12 個快。MD5：`cea31df04b9d71b0038d11420837f9c9`。
