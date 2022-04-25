# Airline-Customer-Value-Analysis-Case-with-Clustering-K-Means

Airline-customer-value-analysis-case merupakan salah satu tugas kelompok metode Unsupervised learning yang diberikan pada saat mengikuti bootcamp Data Science Rakamin Academy.

## Content
Melakukan segmentasi pelanggan penerbangan, menganalisis karakteristik kategori pelanggan yang berbeda, membandingkan nilai pelanggan dari kategori pelanggan yang berbeda, memberikan layanan yang dipersonalisasi untuk kategori pelanggan dengan nilai yang berbeda, dan merumuskan strategi pemasaran yang sesuai.

### Exploratory Data Analysis dan Preprocessing
*	Berdasarkan missing values, dilakukan pengisian data pada feature AGE, SUM_YR_1, dan SUM_YR_2. Selain itu, dilakukan drop pada feature WORK_CITY, WORK_PROVINCE, WORK_COUNTRY dan GENDER
*	Dari hasil heatmap dan referensi ebook diketahui bahwa fitur penting berdasarkan sumber yang dibaca, dipilih menggunakan model LRFMC dimana fitur yang digunakan untuk model ini adalah: `load_time, ffp_date, last_to_end, flight_count, seg_km_sum, avg_discount`
*	Fitur yang nilai korelasinya rendah dan dianggap tidak berhubungan dalam penyelesaian masalah akan di drop dari dataset: MEMBER_NO, AGE, GENDER, EXCHANGE_COUNT, SUM_YR_1, SUM_YR_2, POINT_NOTFLIGHT, AVG_INTERVAL, MAX_INTERVAL 
*	Distribusi pelanggan banyak terpusat di umur produktif (27 – 55 tahun). Hal ini bisa menjadi insight bahwa pelanggan melakukan perjalanan bisnis
*	Pelanggan Loyal bisa dilihat dari pembagian flight count per tahun menjadi member
*	Pelanggan lama bisa dilihat dari tanggal data diambil dikurang FFP join date

**Feature yang tidak ada akan ditambahkan dalam feature engineering**
#### Feature Engineering
Dari feature `LAST_FLIGHT_DATE, FIRST_FLIGHT_DATE, dan FLIGHT COUNT, dilakukan perhitungan untuk menentukan rata-rata penerbangan per tahun dengan output pada feature Flight_Count/Year`
*	Dibuat feature Meeting_Time untuk menghitung jumlah bulan antara LOAD_TIME dan FPP_DATE
*	Setelah feature engineering, drop feature yang tidak digunakan kembali, dan handling outlier, dilakukan standarisasi pada dataset sehingga data dapat siap untuk modelling

### Modeling
Melakukan clustering menggunakan k-means dimana berdasarkan elbow method digunakan jumlah cluster yaitu sebanyak 4 cluster.

### Summary (Analysis Hasil Clustering) 
Simpulkan secara singkat hasil pengerjaan teman-teman. Analysis karakteristik setiap cluster dan berikan insight
Berdasarkan hasil pengerjaan, didapatkan beberapa kesimpulan sebagai berikut:
a.	Feature yang mempengaruhi dalam segmentasi pelanggan diantaranya yakni total jarak penerbangan, jarak waktu penerbangan terakhir ke pesanan penerbangan paling akhir, rata-rata diskon yang didapatkan pelanggan, durasi pelanggan menjadi member, dan rata-rata jumlah penerbangan per tahun.  
b.	Berdasarkan cluster yang telah diidentifikasi (dapat dilihat di file Homework Solution - Clustering)
Adapun penjelasan terhadap ke-4 cluster yang terbentuk adalah sebagai berikut:
1.	`Cluster 0` merupakan pelanggan yang telah mendaftar sebagai member cukup lama (rata-rata 81 bulan) dengan frekuensi terbang sedang (rata-rata 16.564 km) atau sering melakukan penerbangan jarak jauh mengingat jumlah penerbangan per tahunnya cenderung rendah (rata-rata 2 kali per tahun). 
2.	`Cluster 1` merupakan pelanggan baru (rata-rata 30 bulan) dengan frekuensi terbang tinggi (rata-rata 11 penerbangan per tahun), dengan penerbangan jarak jauh (rata-rata 22.258 km).
3.	`Cluster 2` merupakan pelanggan dengan durasi menjadi member, frekuensi terbang, dan jarak penerbangan sedang namun memiliki jarak waktu penerbangan terakhir ke pesanan penerbangan paling akhir rendah.
4.	`Cluster 3` merupakan pelanggan dengan durasi menjadi member, frekuensi terbang, dan jarak penerbangan sedang namun memiliki jarak waktu penerbangan terakhir ke pesanan penerbangan paling akhir tinggi.
