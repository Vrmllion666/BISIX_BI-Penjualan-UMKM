# Sistem Analitik Penjualan UMKM Berbasis Business Intelligence

## Deskripsi
Sistem Business Intelligence untuk analisis dan forecasting penjualan 
UMKM percetakan kertas. Sistem ini mengintegrasikan data warehouse, 
pipeline ETL, analisis OLAP, forecasting machine learning, dan 
dashboard visualisasi interaktif dalam satu ekosistem yang terhubung.

## Teknologi yang Digunakan
- SQL Server 2022 — Data Warehouse dan penyimpanan data
- SSIS (SQL Server Integration Services) — ETL pipeline
- SSAS (SQL Server Analysis Services) — OLAP Cube multidimensi
- Python / Google Colab — Machine learning forecasting
- Microsoft Power BI — Dashboard visualisasi interaktif
- scikit-learn, pandas, numpy — Library machine learning

## Arsitektur Sistem
Data CSV
  -> SSIS (ETL)
  -> SQL Server / Data Warehouse
  -> SSAS (OLAP Cube)
  -> Python AdaBoost (Forecasting)
  -> Power BI (Dashboard)

## Struktur Data Warehouse
Star schema dengan 7 tabel:

Tabel Dimensi:
- DimTanggal     : 487 baris (Agustus 2022 - November 2023)
- DimProduk      : 88 produk unik
- DimKategori    : 9 kategori produk
- DimHarga       : 4 segmen harga

Tabel Fakta:
- FactPenjualan      : 1.072 baris detail transaksi
- FactRekapBulanan   : 625 baris rekap per produk per bulan
- FactAnalisisHarga  : 801 baris analisis harga per produk

## Evaluasi Model (10 Algoritma)
Model terpilih: AdaBoost Regressor berdasarkan nilai MAPE terkecil.

| No | Model              | MAPE (%) | MAE (Rp Jt) |
|----|--------------------|----------|-------------|
| 1  | AdaBoost           | 71,27    | 8,61        |
| 2  | Random Forest      | 75,19    | 8,26        |
| 3  | ElasticNet         | 75,61    | 9,06        |
| 4  | XGBoost            | 78,66    | 8,96        |
| 5  | SVR                | 82,69    | 8,51        |
| 6  | Gradient Boosting  | 83,08    | 8,96        |
| 7  | LightGBM           | 83,24    | 8,48        |
| 8  | Hybrid KNN-SES     | 91,62    | 8,98        |
| 9  | Decision Tree      | 105,94   | 10,13       |
| 10 | Linear Regression  | 189,47   | 16,64       |

## Hasil Forecasting (Desember 2023 - Februari 2024)
Total proyeksi 3 bulan: Rp 310,33 juta

| Produk            | Avg Historis    | Avg Proyeksi    | Growth  |
|-------------------|-----------------|-----------------|---------|
| Dupleks310        | Rp 27.036.875   | Rp 36.011.111   | +33,19% |
| FoodpakMatte245   | Rp 12.007.692   | Rp 18.691.667   | +55,66% |
| Ivory230          | Rp 14.706.725   | Rp 18.430.000   | +25,32% |
| CraftLaminasi290  | Rp 20.496.094   | Rp 17.197.917   | -16,09% |
| Dupleks350        | Rp 14.210.938   | Rp 13.111.111   | -7,74%  |


## Anggota Tim
- [Weka Surajati Sudanta] / [24051214079]
- [MuhammadMirza Shahbaz Zaydan] / [24051214086]
- [Eno Tri Febriani] / [24051214087]
- [Rabbani Nabil Musyaffa] / [24051214097]
- [Muhammad Nashrul Aziz] / [24051214159]
