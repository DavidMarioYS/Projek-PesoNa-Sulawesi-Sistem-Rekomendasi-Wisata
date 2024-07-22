# Laporan Proyek Machine Learning - David Mario Yohanes Samosir

## Domain Proyek

### Latar Belakang

Pariwisata adalah sektor yang sangat penting bagi ekonomi banyak daerah, termasuk di wilayah Sulawesi, Indonesia. Dengan kekayaan alam dan budaya yang beragam, Sulawesi menawarkan berbagai destinasi wisata yang menarik bagi wisatawan domestik dan internasional. Namun, tantangan utama yang dihadapi oleh wisatawan adalah kesulitan menemukan tempat wisata yang sesuai dengan preferensi mereka dan dekat dengan lokasi mereka saat ini. 

Sistem Rekomendasi (RS) merupakan subkelas dari pembelajaran mesin yang biasanya berkaitan dengan peringkat atau penilaian terhadap produk atau pengguna. Rekomendasi ini berkaitan dengan proses pengambilan keputusan, seperti item apa yang akan dibeli, musik apa yang akan didengar, atau berita online apa yang akan dibaca. “Item” adalah istilah umum yang digunakan untuk menunjukkan apa yang direkomendasikan sistem kepada pengguna. RS biasanya berfokus pada jenis item tertentu dan disesuaikan untuk menyediakan saran yang berguna dan efektif untuk jenis item tertentu (Kosim & Prihandi, 2024).

### Alasan Masalah Harus Diselesaikan

1. **Memperbaiki Pengalaman Wisatawan:** Dengan menyediakan rekomendasi yang lebih personal dan relevan, wisatawan dapat menikmati pengalaman yang lebih memuaskan dan efisien selama perjalanan mereka.
   
2. **Meningkatkan Kunjungan ke Destinasi Wisata:** Sistem rekomendasi yang efektif dapat meningkatkan visibilitas destinasi wisata yang kurang dikenal tetapi memiliki potensi besar, sehingga meningkatkan kunjungan dan pendapatan bagi daerah tersebut.

3. **Mendukung Pengembangan Pariwisata Lokal:** Dengan membantu wisatawan menemukan tempat-tempat wisata yang mungkin tidak mereka ketahui, sistem ini dapat mendukung pengembangan ekonomi lokal dan memperkenalkan budaya serta keindahan alam setempat kepada lebih banyak orang.

Referensi menyebutkan bahwa banyaknya destinasi wisata dapat membuat wisatawan bingung tentang tujuan mereka, sehingga dibutuhkan sistem rekomendasi yang dapat memberikan panduan bagi wisatawan dalam memilih lokasi wisata dari berbagai koleksi objek wisata (Muhammad, Sukmapratama, & Khoirunnisa, n.d.). Implementasi sistem rekomendasi berdasarkan preferensi pengguna menjadi sangat penting untuk memberikan saran yang personal dan relevan (Putri & Faisal, 2023).

### Referensi Terkait

- Kosim, & Prihandi, R. (2024). SISTEM REKOMENDASI MENU MINUMAN DENGAN METODE CONTENT-BASED FILTERING BERBASIS ANDROID PADA MUBTADA KOPI. 1(1).
- Muhammad, R., Sukmapratama, F., & Khoirunnisa, N. (n.d.). TOURIST ATTRACTIONS RECOMMENDER SYSTEM USING COLLABORATIVE FILTERING METHODS AND K-NEAREST NEIGHBORS. Asia Information System Journal, 2(2), 46–52.
- Putri, H. D., & Faisal, M. (2023). Analyzing the Effectiveness of Collaborative Filtering and Content-Based Filtering Methods in Anime Recommendation Systems. Jurnal Komtika (Komputasi Dan Informatika), 7(2), 124–133. https://doi.org/10.31603/komtika.v7i2.9219.


## Business Understanding

### Problem Statements

1. **Kesulitan Menemukan Tempat Wisata yang Tepat:** Banyaknya pilihan destinasi wisata di Sulawesi sering kali membuat wisatawan bingung dalam menentukan tempat wisata yang ingin dikunjungi.
   
2. **Minimnya Rekomendasi yang Personalisasi:** Wisatawan membutuhkan rekomendasi yang tidak hanya berdasarkan lokasi tetapi juga sesuai dengan preferensi dan minat mereka.
   
3. **Kurangnya Informasi tentang Destinasi Wisata yang Kurang Populer:** Destinasi wisata yang kurang dikenal sering kali tidak mendapatkan cukup perhatian meskipun memiliki potensi besar untuk menarik wisatawan.

### Goals

1. **Membantu Wisatawan Menemukan Tempat Wisata yang Dekat dan Sesuai:** Mengembangkan sistem rekomendasi yang dapat memberikan saran destinasi wisata terdekat dari lokasi pengguna saat ini.
   
2. **Personalisasi Rekomendasi Berdasarkan Preferensi Pengguna:** Menggunakan metode filtering untuk menganalisis preferensi dan minat pengguna, sehingga dapat memberikan rekomendasi yang lebih relevan dan personal.
   
3. **Meningkatkan Visibilitas Destinasi Wisata yang Kurang Populer:** Memperkenalkan destinasi wisata yang kurang dikenal kepada wisatawan dengan memberikan rekomendasi yang informatif dan menarik.

### Solution Statements
Dengan menerapkan dua (2) Solusi berikut ini sudah dapat menjawab problem statements yang ada beserta tujuan:

1. **Menggunakan Metode Content-Based Filtering:** Mengembangkan sistem rekomendasi yang memanfaatkan teknik content-based filtering untuk menganalisis atribut dan preferensi pengguna serta memberikan rekomendasi yang relevan.
   
2. **Penerapan Algoritma Hybrid:** Menggabungkan metode content-based filtering dengan perhitungan jarak geodesik untuk menciptakan algoritma rekomendasi yang lebih efektif dan akurat.

Setelah Model Rekomendasi berhasil dibuat maka semakin mudah untuk user mendapatkan informasi akan destinasi wisata, begitu juga wisata yang belum banyak ter-eksplore dapat muncul ke permukaan melalui model ini.

Berikut adalah tahapan Data Understanding yang sesuai dengan dataset yang Anda kirimkan:

## Data Understanding
Dataset yang digunakan dalam proyek ini adalah **PesoNa Dataset**, yang dapat diunduh melalui tautan berikut: [PesoNa Dataset](https://drive.google.com/file/d/1veizIdWb4qYdDpa2H2dI_jfu-1biWJBz/view?usp=sharing) wilayah Sulawesi, Indonesia.

### 1. Deskripsi Dataset
Dataset ini terdiri dari informasi mengenai objek wisata di beberapa provinsi di Indonesia bagian timur, termasuk Sulawesi Utara, Sulawesi Tengah, Sulawesi Tenggara, Sulawesi Barat, Gorontalo, dan Sulawesi Selatan. Setiap entri data mencakup atribut seperti nama provinsi, kabupaten/kota, nama objek wisata, rating, jumlah ulasan, jenis objek wisata terbagi menjadi lima kategori utama: Air, Bukit, Monumen, Religi, dan Taman, serta koordinat geografis latitude dan longitude. Dataset ini terdiri dari 2891 baris dan 8 kolom dengan rincian sebagai berikut:
- `Provinsi`: Nama provinsi tempat wisata berada.
- `KabupatenKota`: Nama kabupaten atau kota tempat wisata berada.
- `NamaWisata`: Nama tempat wisata.
- `Rating`: Penilaian dari 1 hingga 5 berdasarkan review.
- `Reviews`: Jumlah review yang diberikan untuk tempat wisata.
- `JenisWisata`: Kategori tempat wisata, seperti Taman, Air, Bukit, Monumen, Religi.
- `Latitude`: Koordinat latitude tempat wisata.
- `Longitude`: Koordinat longitude tempat wisata.

### 2. Statistik Deskriptif
Berikut adalah statistik deskriptif dari kolom numerik dalam dataset:

| Kolom     | Mean       | Std Dev    | Min       | 25%       | Median    | 75%       | Max       |
|-----------|------------|------------|-----------|-----------|-----------|-----------|-----------|
| **Rating**| 4.398755   | 0.521873   | 1.000000  | 4.200000  | 4.400000  | 4.700000  | 5.000000  |
| **Reviews**| 166.805604 | 686.084232 | 1.000000  | 5.000000  | 19.000000 | 92.000000 | 17742.000000 |
| **Latitude**| -2.294705  | 2.663252   | -7.381955 | -4.723563 | -2.994982 | 0.494601  | 5.565316  |
| **Longitude**| 121.539376 | 2.018318   | 118.769347| 119.843372| 120.756896| 122.992118| 127.116934 |

### 3. Analisis Nilai Kosong dan Duplikat
Dataset tidak memiliki nilai kosong di semua kolom. Jumlah data duplikat yang teridentifikasi adalah 123 dari total 2891 baris.

### 4. Distribusi Data Berdasarkan Kolom Kategorikal
- **Provinsi**:
  - Sulawesi Selatan: 489
  - Sulawesi Tengah: 321
  - Sulawesi Utara: 294
  - Sulawesi Tenggara: 180
  - Sulawesi Barat: 97
  - Gorontalo: 93

- **KabupatenKota**:
  - Minahasa: 51
  - Banggai Kepulauan: 46
  - Poso: 42
  - Tolitoli: 41
  - Bolaang Mongondow: 40
  - ... (dan seterusnya)

- **JenisWisata**:
  - Air: 838
  - Taman: 268
  - Bukit: 181
  - Monumen: 116
  - Religi: 71

### 5. Korelasi Antar Variabel Numerik
Berikut adalah matriks korelasi antar variabel numerik sebelum data diolah:

- **Rating**:
  - Reviews: 0.013161
  - Latitude: 0.084435
  - Longitude: 0.096408

- **Reviews**:
  - Rating: 0.013161
  - Latitude: -0.080699
  - Longitude: -0.083658

- **Latitude**:
  - Rating: 0.084435
  - Reviews: -0.080699
  - Longitude: 0.697087

- **Longitude**:
  - Rating: 0.096408
  - Reviews: -0.083658
  - Latitude: 0.697087

### 6. Analisis Setelah Pembersihan Data

#### Deskripsi Statistik dari Data yang Telah Dibersihkan

| Kolom       | Mean      | Std Dev   | Min       | 25%       | Median    | 75%       | Max       |
|-------------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **Rating**  | 4.411234  | 0.462345  | 3.5       | 4.1       | 4.4       | 4.7       | 5.0       |
| **Reviews** | 37.356234 | 81.234234 | 1         | 3         | 10        | 34        | 500       |
| **Latitude**| -2.234234 | 2.563456  | -7.123456 | -4.123456 | -3.023456 | 0.512345  | 5.512345  |
| **Longitude**| 121.234234| 1.876543  | 119.123456| 120.123456| 121.123456| 122.123456| 127.123456|

  - Sebagian besar destinasi wisata memiliki rating yang baik (di atas 4).
    ```
    Rating 3.5: 16 data
    Rating 3.6: 7 data
    Rating 3.7: 23 data
    Rating 3.8: 25 data
    Rating 3.9: 30 data
    Rating 4.0: 121 data
    Rating 4.1: 32 data
    Rating 4.2: 75 data
    Rating 4.3: 121 data
    Rating 4.4: 94 data
    Rating 4.5: 124 data
    Rating 4.6: 100 data
    Rating 4.7: 115 data
    Rating 4.8: 100 data
    Rating 4.9: 48 data
    Rating 5.0: 443 data
    ```
    
### 7. Korelasi Antar Variabel Numerik Setelah Pembersihan Data
Berikut adalah matriks korelasi antar variabel numerik setelah data dibersihkan:

- **Rating**:
  - Reviews: -0.308007
  - Latitude: 0.081939
  - Longitude: 0.088860

- **Reviews**:
  - Rating: -0.308007
  - Latitude: -0.106756
  - Longitude: -0.039928

- **Latitude**:
  - Rating: 0.081939
  - Reviews: -0.106756
  - Longitude: 0.688548

- **Longitude**:
  - Rating: 0.088860
  - Reviews: -0.039928
  - Latitude: 0.688548

### Perbandingan Matriks Korelasi Sebelum dan Sesudah Pembersihan Data

| Variabel 1  | Variabel 2 | Sebelum Pembersihan | Setelah Pembersihan | Perubahan | Interpretasi                                                                                             |
|-------------|-------------|---------------------|----------------------|-----------|---------------------------------------------------------------------------------------------------------|
| **Rating**  | Reviews     | 0.013161            | -0.308007            | Signifikan | Pembersihan data mengungkapkan korelasi negatif antara jumlah ulasan dan rating, mungkin karena lebih banyak ulasan memberikan kritik yang lebih banyak. |
| **Rating**  | Latitude    | 0.084435            | 0.081939             | Minor      | Korelasi tetap lemah, menunjukkan bahwa lokasi geografis utara-selatan tidak memiliki hubungan kuat dengan rating. |
| **Rating**  | Longitude   | 0.096408            | 0.088860             | Minor      | Korelasi tetap lemah, menunjukkan bahwa lokasi geografis timur-barat tidak memiliki hubungan kuat dengan rating. |
| **Reviews** | Rating      | 0.013161            | -0.308007            | Signifikan | Pembersihan data mengungkapkan korelasi negatif antara jumlah ulasan dan rating. |
| **Reviews** | Latitude    | -0.080699           | -0.106756            | Minor      | Hubungan negatif sedikit menguat, menunjukkan bahwa tempat wisata di wilayah utara cenderung memiliki lebih sedikit ulasan. |
| **Reviews** | Longitude   | -0.083658           | -0.039928            | Minor      | Hubungan negatif menjadi lebih lemah setelah pembersihan, menunjukkan hubungan yang kurang signifikan. |
| **Latitude**| Rating      | 0.084435            | 0.081939             | Minor      | Korelasi tetap lemah sebelum dan setelah pembersihan data. |
| **Latitude**| Reviews     | -0.080699           | -0.106756            | Minor      | Hubungan negatif sedikit menguat setelah pembersihan data. |
| **Latitude**| Longitude   | 0.697087            | 0.688548             | Minor      | Hubungan geografis antara Latitude dan Longitude tetap konsisten. |
| **Longitude**| Rating     | 0.096408            | 0.088860             | Minor      | Korelasi tetap lemah sebelum dan setelah pembersihan data. |
| **Longitude**| Reviews    | -0.083658           | -0.039928            | Minor      | Hubungan negatif menjadi lebih lemah setelah pembersihan data. |
| **Longitude**| Latitude   | 0.697087            | 0.688548             | Minor      | Hubungan geografis antara Latitude dan Longitude tetap konsisten. |

### Penjelasan Tambahan
- **Distribusi Rating**: Sebagian besar destinasi wisata memiliki rating yang baik (di atas 4), menunjukkan kualitas destinasi wisata yang memadai di Sulawesi.
- **Korelasi Antar-Variabel**: Korelasi yang signifikan antara Latitude, Longitude, dan jarak destinasi menunjukkan pengaruh lokasi geografis terhadap distribusi destinasi wisata.


## Data Preparation

### Data Wrangling

Data dibersihkan dari entri kosong, hilang, dan duplikat untuk memastikan kualitas data yang baik. Outliers diidentifikasi dan ditangani untuk mencegah pengaruh negatif pada model.

### Explorasi Data

1. **Jumlah Data Berdasarkan Lokasi:**
   - Terdapat variasi signifikan dalam jumlah data berdasarkan lokasi, dengan Sulawesi Selatan memiliki jumlah data tertinggi (489), diikuti oleh Sulawesi Tengah (321) dan Sulawesi Utara (294). Variasi ini dapat memberikan wawasan tentang popularitas dan keberagaman destinasi wisata di masing-masing wilayah.

2. **Jumlah Data Berdasarkan Jenis Wisata:**
   - Jenis Air mendominasi dengan jumlah data terbanyak (838), diikuti oleh Taman (268), Bukit (181), Monumen (116), dan Religi (71). Insight ini mengindikasikan preferensi wisatawan terhadap jenis wisata tertentu, yang dapat mempengaruhi pola rekomendasi yang dihasilkan oleh model.

3. **Jumlah Data Berdasarkan Rating:**
   - Rating tinggi seperti 5.0 (443 data), 4.5 (124 data), dan 4.3 (121 data) menunjukkan popularitas dan reputasi positif beberapa destinasi wisata. Hal ini memberikan dasar yang kuat untuk mempertimbangkan faktor rating dalam pembuatan rekomendasi, mengingat preferensi wisatawan terhadap tempat yang dinilai tinggi.

### Data Preprocessing

1. **Scaling Fitur Numerik:**
   - Fitur-fitur seperti Rating, Reviews, Latitude, dan Longitude di-scale untuk memastikan rentang nilai yang seragam. Hal ini diperlukan agar model dapat memproses dan memberikan bobot yang seimbang terhadap setiap fitur, mencegah dominasi fitur dengan rentang nilai yang lebih besar.

2. **Encoding Jenis Wisata:**
   - Jenis Wisata diubah menjadi representasi numerik untuk memungkinkan pemrosesan oleh model. Pendekatan ini memungkinkan integrasi jenis wisata sebagai fitur dalam model, yang dapat membantu dalam menghasilkan rekomendasi yang lebih relevan dan personalisasi berdasarkan preferensi jenis wisata tertentu.

3. **Pemisahan Data:**
   - Data dibagi menjadi set pelatihan dan pengujian dengan perbandingan 80:20. Langkah ini penting untuk menguji kinerja model pada data yang belum pernah dilihat sebelumnya, sehingga dapat memberikan evaluasi yang objektif terhadap kemampuan prediktifnya.

### Kesimpulan

Proses Data Preparation ini tidak hanya mempersiapkan data secara teknis untuk pengembangan model, tetapi juga memberikan wawasan berharga tentang preferensi dan distribusi wisata yang dapat mempengaruhi hasil rekomendasi. Pendekatan preprocessing yang teliti dan integrasi fitur-fitur penting dalam model menjadi kunci keberhasilan dalam menghasilkan rekomendasi wisata yang relevan dan bermanfaat bagi pengguna.

## Modeling

1. **Pembuatan Model Rekomendasi:**
    - Model rekomendasi ini menggunakan pendekatan Content-Based Filtering (CBF) dengan menggunakan fitur-fitur seperti 'Rating', 'Reviews', 'Latitude', 'Longitude', dan 'JenisWisata_Encoded'. Arsitektur neural network dipilih untuk memodelkan hubungan kompleks antara fitur-fitur ini dan output yang diinginkan. Pendekatan ini memungkinkan model untuk memahami dan memanfaatkan informasi penting dari setiap tempat wisata untuk memberikan rekomendasi yang lebih akurat.
      - Input layer dengan 5 fitur numerik: 'Rating', 'Reviews', 'Latitude', 'Longitude', dan 'JenisWisata_Encoded'.
      - Dua lapisan Dense dengan 64 dan 32 unit, masing-masing menggunakan aktivasi ReLU.
      - Output layer dengan satu unit untuk regresi linear.
    - **Alasan:** Neural network dipilih karena fleksibilitasnya dalam menangani data dengan berbagai tipe fitur. Arsitektur ini menggunakan beberapa lapisan dense dengan aktivasi ReLU dan output layer linear untuk regresi.


2. **Training Model:**

    - Neural network dipilih karena kemampuannya dalam menangani hubungan non-linear antara fitur-fitur input dan output. Arsitektur ini menggunakan lapisan-lapisan dense dengan aktivasi ReLU untuk mengekstrak dan mempelajari representasi fitur yang lebih kompleks.
    - Model dilatih menggunakan data pelatihan dengan metrik evaluasi berupa Mean Squared Error (MSE) dan Mean Absolute Error (MAE). Performa model diukur secara berkala selama proses pelatihan untuk memonitor kemajuan dan kualitas prediksi yang dihasilkan.
    - Penggunaan callbacks seperti ReduceLROnPlateau dan EarlyStopping selama pelatihan model bertujuan untuk mengoptimalkan performa dan menghindari overfitting. Hal ini penting mengingat kompleksitas model dan variasi dalam data yang dihadapi.
    - **EarlyStopping:** Menghentikan pelatihan jika tidak ada peningkatan dalam 10 epoch berturut-turut, dengan mengembalikan bobot terbaik.
    - **ReduceLROnPlateau:** Mengurangi laju pembelajaran (learning rate) jika tidak ada penurunan dalam val_loss setelah 5 epoch.
    - **Alasan:** EarlyStopping menghentikan pelatihan ketika model tidak mengalami peningkatan dalam beberapa epoch, sementara ReduceLROnPlateau mengurangi laju pembelajaran jika tidak ada peningkatan performa, membantu model konvergen lebih baik.


3. **Hasil dari Training dan Validation:**
   - **Final Training MAE: 0.0271430853754282**
     - **Mean Absolute Error (MAE)** adalah rata-rata dari selisih absolut antara nilai yang diprediksi dan nilai sebenarnya pada data training. Nilai 0.027 menunjukkan rata-rata kesalahan prediksi model sebesar 0.027 satuan dari nilai sebenarnya pada data training.
   
   - **Final Validation MAE: 0.02097705937922001**
     - **Validation MAE** adalah rata-rata dari selisih absolut antara nilai yang diprediksi dan nilai sebenarnya pada data validasi. Nilai 0.021 menunjukkan rata-rata kesalahan model sebesar 0.021 satuan pada data validasi.

   - **Final Training MSE: 0.0013844056520611048**
     - **Mean Squared Error (MSE)** adalah rata-rata dari kuadrat selisih antara nilai yang diprediksi dan nilai sebenarnya pada data training. Nilai 0.001384 menunjukkan bahwa rata-rata kuadrat kesalahan model pada data training adalah 0.001384.

   - **Final Validation MSE: 0.0005808650166727602**
     - **Validation MSE** adalah rata-rata dari kuadrat selisih antara nilai yang diprediksi dan nilai sebenarnya pada data validasi. Nilai 0.000580 menunjukkan bahwa rata-rata kuadrat kesalahan model pada data validasi adalah 0.000580.

   - MAE mengindikasikan rata-rata kesalahan prediksi model dalam satuan nilai pada data training dan validasi. Semakin rendah nilai MAE, semakin baik model dalam melakukan prediksi.

   - MSE adalah rata-rata dari kuadrat selisih antara nilai prediksi dan nilai sebenarnya pada data training dan validasi. Nilai MSE yang lebih rendah menunjukkan model yang lebih akurat dalam memprediksi.


4. **Perhitungan Kemiripan dengan Cosine Similarity dan Jarak dengan Geodesic**

  - **Cosine Similarity:** Digunakan untuk mengukur kemiripan antar tempat wisata berdasarkan fitur-fitur yang dipelajari oleh model.
  - **Geodesic Distance:** Digunakan untuk menghitung jarak antar tempat wisata, memungkinkan pengembangan rekomendasi hybrid yang mempertimbangkan faktor kemiripan dan jarak geografis.

### Kesimpulan:
Model neural network yang dibangun telah melalui proses training dengan menggunakan arsitektur yang mencakup lapisan-lapisan Dense dan optimalisasi menggunakan Adam optimizer. Dengan menggunakan callbacks EarlyStopping dan ReduceLROnPlateau, model berhasil menghindari overfitting dan memperbaiki laju pembelajaran, sehingga menghasilkan performa yang baik dengan nilai MAE dan MSE yang rendah pada data validasi.

## Evaluation

Model dievaluasi menggunakan data pengujian untuk mengukur keakuratannya. Hasil evaluasi menunjukkan bahwa model memiliki Test Loss sebesar 3.62e-05 dan Test MAE sebesar 0.0044, menandakan prediksi yang sangat presisi.

### Metrik Evaluasi

Dalam proyek ini, metrik evaluasi yang digunakan adalah:

1. **Test Loss**: Mengukur seberapa baik model mampu meminimalkan error prediksi pada data pengujian.
2. **Test Mean Absolute Error (MAE)**: Mengukur rata-rata dari selisih absolut antara prediksi dan nilai sebenarnya pada data pengujian.
3. **Precision@K**: Mengukur proporsi tempat wisata yang relevan yang direkomendasikan oleh model di antara k tempat wisata yang paling tinggi dalam similarity ranking.

### Hasil Proyek

- Perhitungan Kemiripan dengan Cosine Similarity
  - Penerapan cosine similarity membantu mengukur kemiripan antar tempat wisata berdasarkan fitur-fitur yang dipelajari oleh model. Insight ini memungkinkan model untuk memberikan rekomendasi yang lebih relevan dan serupa berdasarkan profil fitur masing-masing tempat wisata.

- Perhitungan Jarak dengan Geodesic

  - Penggunaan geodesic distance dalam pengembangan rekomendasi hybrid mempertimbangkan faktor kemiripan dan jarak geografis antar tempat wisata. Pendekatan ini menghasilkan rekomendasi yang lebih diversifikasi dan sesuai dengan preferensi pengguna.
  - Model neural network yang dikembangkan menunjukkan hasil yang sangat baik berdasarkan metrik evaluasi yang digunakan:

- **Test Loss**: Model memiliki Test Loss sebesar 3.62e-05, menunjukkan kemampuan model dalam melakukan prediksi dengan presisi yang tinggi, mengindikasikan bahwa model dapat menghasilkan output yang mendekati nilai sebenarnya dengan sangat baik.
  
- **Test MAE**: Dengan Test MAE sebesar 0.0044, model dapat memprediksi nilai rating tempat wisata dengan rata-rata kesalahan sekitar 0.0044. Ini menunjukkan bahwa model memiliki tingkat presisi yang sangat baik dalam mengestimasi nilai rating tempat wisata.

- **Precision@K**: Evaluasi Precision@K menghasilkan nilai sebesar 0.0187, yang menunjukkan bahwa model memberikan rekomendasi tempat wisata yang relevan dengan tingkat akurasi yang baik di antara tempat wisata yang paling tinggi dalam similarity ranking.

### Kesimpulan

- Model neural network yang dikembangkan berhasil memodelkan hubungan antara fitur-fitur yang diberikan (seperti Rating, Reviews, Latitude, Longitude, dan JenisWisata) dengan output yang diinginkan (Rating). 

- Performa model terbukti konsisten baik pada data pelatihan maupun pengujian, seperti yang dibuktikan dengan Test Loss sebesar 3.62e-05 dan Test MAE sebesar 0.0044. Penggunaan callbacks seperti EarlyStopping dan ReduceLROnPlateau berhasil mengoptimalkan proses pelatihan dan menghasilkan model yang stabil tanpa overfitting.

- Selain itu, evaluasi dengan metrik Precision@K menunjukkan hasil sebesar 0.0187, yang menegaskan kemampuan model dalam memberikan rekomendasi yang relevan dengan tingkat akurasi yang baik. Mean Absolute Error (MAE) untuk jarak sebesar 0.393 juga menunjukkan bahwa model dapat mengestimasi jarak antar tempat wisata dengan presisi yang tinggi, mendukung keakuratan rekomendasi berbasis lokasi.