# Analisis Ketersediaan dan Kebutuhan Komoditas Pangan Provinsi Jawa Tengah (2019–2023)

##  Deskripsi Project
Project ini bertujuan untuk menganalisis kondisi **ketersediaan, kebutuhan, dan potensi surplus/defisit** komoditas pangan strategis di Provinsi Jawa Tengah selama periode 2019–2023.

Analisis dilakukan menggunakan pendekatan **Exploratory Data Analysis (EDA)**, **Clustering K-Means**, **Analisis Musiman**, dan **Prediksi Time Series** untuk menghasilkan insight yang dapat mendukung pengambilan keputusan kebijakan pangan.

---

##  Dataset
- **Sumber**: Pemerintah Provinsi Jawa Tengah
- **URL**: https://data.jatengprov.go.id/dataset/325-sdjt-ketersediaan-dan-kebutuhan-komoditas-pangan
- **Periode**: 2019 – 2023
- **Granularitas**: Bulanan
- **Kolom Utama**:
  - `tahun` & `bulan`
  - `komoditas`
  - `ketersediaan` (Ton)
  - `kebutuhan` (Ton)
  - `deviasi` (Surplus/Defisit)

---

##  Struktur Repository
Project ini dibagi menjadi tiga tahapan analisis utama dalam bentuk Jupyter Notebook:

1.  **`01_eda.ipynb` (Data Preparation & EDA)**
    * Pembersihan data, penyatuan dataset tahunan, dan standardisasi nama komoditas.
    * Perhitungan awal surplus/defisit dan rasio pangan.
2.  **`02_clustering.ipynb` (Clustering K-Means)**
    * Mengelompokkan komoditas berdasarkan karakteristik ketahanan pangan (Aman vs Rawan).
3.  **`03_forecasting.ipynb` (Seasonality & Forecasting)**
    * Analisis pola musiman dan prediksi ketersediaan pangan menggunakan regresi linear/time series sederhana.

---

##  Tujuan Analisis
1.  **Tren**: Mengidentifikasi tren ketersediaan dan kebutuhan pangan tahunan.
2.  **Status Pangan**: Mengetahui komoditas dengan potensi **surplus** (Aman) dan **defisit** (Rawan).
3.  **Pengelompokan**: Mengelompokkan komoditas berdasarkan karakteristik pasokan dan permintaan menggunakan *Unsupervised Learning*.
4.  **Pola Musiman**: Mengidentifikasi siklus **panen raya & paceklik** untuk manajemen stok.
5.  **Forecasting**: Memprediksi kondisi ketersediaan pangan ke depan sebagai *early warning system*.

---

##  Hasil & Insight Utama

Berdasarkan eksekusi kode dan analisis data, berikut adalah temuan kuncinya:

### 1. Status Komoditas (EDA & Clustering)
Analisis K-Means dan perhitungan rasio pangan menghasilkan pengelompokan yang jelas:
* **Cluster Mandiri (Surplus Konsisten)**:
    * Komoditas: **Padi (Beras)** dan **Jagung**.
    * *Insight*: Produksi lokal sangat kuat dan mampu memenuhi kebutuhan konsumsi internal Jawa Tengah (Rasio > 1).
* **Cluster Rentan (Defisit/Rawan)**:
    * Komoditas: **Bawang Putih** dan **Kedelai**.
    * *Insight*: Menunjukkan ketersediaan negatif atau *gap* yang besar antara kebutuhan dan produksi, mengindikasikan ketergantungan tinggi pada pasokan luar daerah/impor.

### 2. Analisis Pola Musiman
* Teridentifikasi bulan-bulan **panen raya** di mana ketersediaan melonjak drastis.
* Teridentifikasi periode **paceklik** dengan penurunan pasokan signifikan.
* *Penting*: Pola ini sangat terlihat pada komoditas tanaman pangan (Padi/Jagung), sedangkan komoditas hortikultura memiliki fluktuasi yang lebih dinamis.

### 3. Prediksi vs Kebutuhan
* Model prediksi linear memberikan gambaran tren umum, namun deviasi antara prediksi dan kebutuhan aktual menjadi sinyal risiko yang harus dipantau, terutama menjelang hari besar keagamaan atau akhir tahun.

---

##  Kesimpulan & Rekomendasi

### Kesimpulan
1.  **Disparitas Ketahanan**: Tidak semua komoditas mengalami masalah yang sama. Jawa Tengah sangat kuat di sektor serealia (Padi/Jagung) namun rentan di sektor hortikultura spesifik (Bawang Putih) dan kacang-kacangan (Kedelai).
2.  **Faktor Musiman**: Analisis musiman terbukti krusial. Ketersediaan pangan tidak rata sepanjang tahun, menuntut manajemen logistik yang adaptif.

### Rekomendasi Kebijakan
1.  **Manajemen Buffer Stock**: Pemerintah perlu memaksimalkan penyerapan gabah/beras saat panen raya untuk mengisi cadangan pangan menghadapi bulan paceklik.
2.  **Intervensi Komoditas Defisit**: Diperlukan strategi khusus untuk **Kedelai dan Bawang Putih**, baik melalui diversifikasi impor, kerjasama antar-daerah, atau program intensifikasi pertanian lokal.
3.  **Sistem Monitoring**: Menggunakan hasil prediksi ini sebagai dasar intervensi distribusi sebelum puncak kebutuhan terjadi.

---

##  Tools & Library
Project ini dikembangkan menggunakan Python dengan library berikut:
* **Data Processing**: Pandas, NumPy, OpenPyXL
* **Visualization**: Matplotlib, Seaborn
* **Machine Learning**: Scikit-learn (StandardScaler, KMeans, LinearRegression)

---
##  Visualisasi Utama

![Ketersediaan vs Kebutuhan](assets/images/ketersediaan_vs_kebutuhan.png)

### Prediksi Ketersediaan Pangan (Beras)
![Prediksi Ketersediaan Beras](assets/images/prediksi_ketersediaan_beras.png)

**Author**: [mohfirdaus22]

