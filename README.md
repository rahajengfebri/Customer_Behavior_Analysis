# Customer Behavior Analysis: Purchase Patterns, Customer Segmentation, and Transaction Cancellations

## Overview Project
Proyek ini bertujuan untuk menganalisis perilaku pelanggan dalam transaksi e-commerce untuk memahami **pola pembelian pelanggan, segmentasi pelanggan, serta pembatalan transaksi**.

Analisis ini membantu bisnis untuk:
- Mengidentifikasi pelanggan yang paling berkontribusi terhadap revenue
- Memahami pola pembelian pelanggan
- Mengidentifikasi produk yang populer
- Menganalisis pola pembatalan transaksi

Pada proyek ini juga dilakukan **segmentasi pelanggan menggunakan metode RFM (Recency, Frequency, Monetary)** untuk mengelompokkan pelanggan berdasarkan perilaku transaksi mereka.

---

# Problem Statement
Perusahaan e-commerce memiliki banyak data transaksi pelanggan, namun data tersebut belum dimanfaatkan secara optimal untuk memahami **pola pembelian pelanggan, kontribusi pelanggan terhadap penjualan, serta perilaku pembatalan transaksi**.

Tanpa analisis yang tepat, perusahaan akan kesulitan untuk:
- Mengetahui pelanggan yang paling berkontribusi terhadap penjualan
- Memahami kebiasaan pembelian pelanggan
- Mengidentifikasi pola pembatalan pesanan

---

# Business Questions
Proyek ini bertujuan untuk menjawab beberapa pertanyaan bisnis berikut:

1. Produk apa saja yang paling sering dibeli oleh pelanggan?
2. Bagaimana pola aktivitas pembelian pelanggan dari waktu ke waktu?
3. Bagaimana distribusi pelanggan berdasarkan lokasi atau negara?
4. Bagaimana segmentasi pelanggan berdasarkan metode **RFM (Recency, Frequency, Monetary)**?
5. Segmen pelanggan mana yang memiliki aktivitas transaksi paling tinggi?
6. Produk apa yang paling sering mengalami pembatalan transaksi?
7. Bagaimana pola pembatalan transaksi pelanggan dari waktu ke waktu?

---

# Dataset
Dataset yang digunakan dalam proyek ini merupakan **data transaksi penjualan dari perusahaan e-commerce berbasis di United Kingdom (UK)** selama satu tahun.

Dataset diambil dari Kaggle dan berisi sekitar **536.350 baris data dengan 8 kolom**.

Sumber dataset:  
https://www.kaggle.com/datasets/gabrielramos87/an-online-shop-business/data

## Informasi Dataset
- Total pelanggan: **4.738**
- Total transaksi: **±19.79K**
- Total revenue: **£62.78M**

## Deskripsi Kolom

| Kolom | Deskripsi |
|------|------|
| TransactionNo | Nomor unik 6 digit untuk setiap transaksi. Jika diawali huruf **C**, berarti transaksi tersebut merupakan pembatalan |
| Date | Tanggal transaksi dilakukan |
| ProductNo | Kode unik untuk mengidentifikasi produk |
| ProductName | Nama produk |
| Price | Harga per unit produk dalam Poundsterling (£) |
| Quantity | Jumlah produk dalam transaksi (nilai negatif menunjukkan pembatalan atau refund) |
| CustomerNo | Nomor unik pelanggan |
| Country | Negara asal pelanggan |

---

# Data Preprocessing
Beberapa tahapan preprocessing dilakukan untuk memastikan data siap digunakan untuk analisis:

- Mengambil dataset dari Kaggle
- Memperbaiki tipe data
- Menangani missing values
- Menghapus data duplikat
- Memeriksa distribusi data
- Normalisasi data menggunakan **RobustScaler**
- Deteksi outlier
- Feature engineering:
  - Membuat kolom **Revenue**
  - Melakukan **analisis RFM**
  - Membuat kolom **Customer Segment**

Outlier tidak dihapus karena pada dataset transaksi e-commerce nilai ekstrem dapat terjadi akibat **pembelian dalam jumlah besar, transaksi bisnis, atau proses pengembalian barang**.

---

# RFM Customer Segmentation

Metode **RFM (Recency, Frequency, Monetary)** digunakan untuk mengelompokkan pelanggan berdasarkan perilaku transaksi mereka.

### Recency
Menunjukkan **kapan terakhir kali pelanggan melakukan pembelian**.

### Frequency
Menunjukkan **seberapa sering pelanggan melakukan pembelian**.

### Monetary
Menunjukkan **berapa banyak uang yang dibelanjakan pelanggan**.

Pelanggan kemudian diklasifikasikan ke dalam 4 segmen:

- **Royal Customer**
- **Potential Customer**
- **At Risk Customer**
- **Lost Customer**

---

# Hasil Analisis

## Customer Purchasing Behavior
Dataset mencatat:

- **4.738 pelanggan**
- **4.718 pelanggan menyelesaikan transaksi**
- **±19.79K transaksi**
- **Total revenue sebesar £62.78M**

Produk dengan jumlah pelanggan terbanyak yang menyelesaikan transaksi:

1. Regency Cakestand 3 Tier
2. Cream Hanging Heart T-Light Holder
3. Jumbo Bag Red Retrospot

Aktivitas pembelian pelanggan menunjukkan **tren meningkat sepanjang tahun dengan puncak transaksi pada bulan November**.

Sebagian besar pelanggan berasal dari **United Kingdom**, sementara **Germany dan France** menjadi pasar internasional terbesar setelah UK.

---

# Customer Segmentation (RFM)

Distribusi pelanggan berdasarkan segmentasi RFM:

- **Royal Customer:** 36.82%
- **Potential Customer:** 29.33%
- **At Risk Customer:** 18.65%
- **Lost Customer:** 15.2%

Segmen **Royal Customer** memiliki kontribusi terbesar terhadap bisnis dengan:

- **4.27K transaksi**
- **£43M revenue**

Kontribusi revenue berdasarkan segmen:

| Segment | Revenue |
|------|------|
| Royal Customer | £43M |
| Potential Customer | £13M |
| At Risk Customer | £5M |
| Lost Customer | £2M |

---

# Order Cancellation Analysis

Dataset mencatat **1.533 pelanggan yang melakukan pembatalan transaksi**.

Produk dengan jumlah pelanggan pembatalan terbanyak:

- Regency Cakestand 3 Tier
- Jam Making Set with Jars
- Set of 3 Cake Tins Pantry Design

Terdapat transaksi pembatalan dalam jumlah sangat besar:

- Customer **16446** membatalkan **80.995 unit** produk *Paper Craft Little Birdie*
- Customer **12346** membatalkan **74.215 unit** produk *Medium Ceramic Top Storage Jar*

Hal ini menunjukkan adanya **pembatalan transaksi dalam jumlah ekstrem** yang perlu ditinjau lebih lanjut.

Pola pembatalan transaksi:

- Tingkat pembatalan tertinggi terjadi pada **January (22.84%)** dan **November (22.65%)**
- **Hari Minggu** memiliki jumlah pelanggan pembatalan tertinggi

---

# Insight

- Produk paling populer adalah **Regency Cakestand 3 Tier**, **Cream Hanging Heart T-Light Holder**, dan **Jumbo Bag Red Retrospot**.
- Aktivitas pembelian pelanggan meningkat sepanjang tahun dengan **puncak transaksi pada bulan November**.
- Sebagian besar pelanggan berasal dari **United Kingdom**.
- Segmen **Royal Customer mendominasi dengan 36.82% pelanggan**.
- Segmen **Royal Customer memberikan kontribusi revenue terbesar (£43M)**.
- Beberapa produk memiliki tingkat pembatalan yang tinggi.
- Terdapat transaksi pembatalan dengan quantity sangat besar yang perlu dianalisis lebih lanjut.

---

# Recommendation

- Mempertahankan **Royal Customer** melalui program loyalitas dan promosi khusus.
- Mendorong **Potential Customer** menjadi Royal Customer melalui strategi pemasaran yang lebih personal.
- Mengoptimalkan strategi promosi pada periode **high season**, terutama menjelang akhir tahun.
- Mengembangkan pasar internasional, khususnya **Germany dan France**.
- Mengidentifikasi produk dengan tingkat pembatalan transaksi yang tinggi sebagai bahan evaluasi bisnis.
- Melakukan peninjauan terhadap transaksi dengan **quantity pembatalan yang sangat besar**.
- Mengidentifikasi pelanggan dengan pola pembelian dalam jumlah besar untuk mengetahui apakah pelanggan tersebut merupakan **reseller atau pelanggan bisnis**.
- Menerapkan monitoring terhadap transaksi dengan **quantity ekstrem** untuk mendeteksi potensi anomali lebih awal.


