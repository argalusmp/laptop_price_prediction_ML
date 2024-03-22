# Laporan Proyek Machine Learning - Vidi Septri Argalus Mp

## Domain Proyek

Proyek ini berfokus pada prediksi harga laptop menggunakan dataset yang tersedia di Kaggle. Prediksi harga laptop ini penting untuk membantu konsumen dalam membuat keputusan pembelian. Selain itu, ini juga dapat membantu penjual untuk menetapkan harga yang kompetitif.

### Latar Belakang

Laptop adalah salah satu barang elektronik yang paling sering diperdagangkan secara online. Harga laptop dapat bervariasi secara signifikan tergantung pada berbagai fitur dan spesifikasi, seperti merk, ukuran layar, jenis prosesor, kecepatan prosesor, memori, dan lainnya. Oleh karena itu, membangun model yang dapat memprediksi harga laptop berdasarkan fitur-fitur ini bisa sangat berguna.

Dalam proyek ini, kita akan mencoba membangun model prediktif untuk harga laptop menggunakan dataset dari Kaggle. Kami akan menggunakan beberapa algoritma machine learning, termasuk K-Nearest Neighbors, Random Forest, dan AdaBoosting, dan kami juga akan melakukan hyperparameter tuning untuk meningkatkan performa model. Kami berharap bahwa hasil dari proyek ini akan membantu penjual dan pembeli laptop dalam transaksi mereka.

## Business Understanding

### Problem Statements

Berdasarkan latar belakang masalah, rincian masalahnya adalah sebagai berikut:

- Bagaimana kita dapat memprediksi harga laptop berdasarkan fitur-fitur tertentu?
- Algoritma machine learning apa yang paling efektif untuk memprediksi harga laptop?

### Goals

Untuk tujuan penyelesaiannya, antara lain:

- Membuat model prediktif yang dapat memprediksi harga laptop dengan akurasi yang tinggi.
- Menentukan algoritma machine learning terbaik untuk memprediksi harga laptop.

### Solution statments

Solusi yang dapat dilakukan :

- Membangun beberapa model pembelajaran mesin dan memilih model yang terbaik, disini saya menggunakan algoritma K-Nearest Neighbors, Random Forest dan AdaBoosting untuk membangun model prediktif

- Melakukan hyperparameter tuning dengan RandomizedSearchCV, RandomForestRegressor, KNeighborsRegressor, dan GradientBoostingRegressor untuk meningkatkan performa model.

**Rubrik/Kriteria Tambahan (Opsional)**:

- Menambahkan bagian “Solution Statement” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut:

  ### Solution statements

  - Mengajukan 2 atau lebih solution statement. Misalnya, menggunakan dua atau lebih algoritma untuk mencapai solusi yang diinginkan atau melakukan improvement pada baseline model dengan hyperparameter tuning.
  - Solusi yang diberikan harus dapat terukur dengan metrik evaluasi.

## Data Understanding

Data yang digunakan dalam proyek ini adalah dataset harga laptop yang mencakup berbagai fitur, seperti ukuran layar, RAM, penyimpanan, merek, dan lainnya. Dataset ini dapat diunduh dari [https://www.kaggle.com/datasets/juanmerinobermejo/laptops-price-dataset].

### Variabel-variabel pada Laptop Price dataset adalah sebagai berikut:

- RAM: Ukuran RAM laptop .
- Storage: Kapasitas penyimpanan laptop .
- Screen: Ukuran layar laptop.
- Brand: Merek laptop.
- Model: Model laptop.
- CPU: Tipe prosesor laptop.
- Storage type: Jenis penyimpanan laptop.
- GPU: Jenis kartu grafis laptop (jika ada).
- Touch: Menunjukkan apakah layar laptop mendukung fitur layar sentuh atau tidak.

### Exploratory Data Analysis and Visualization dataset

![GitHub Image](https://github.com/argalusmp/laptop_price_prediction_ML/blob/main/images/correlation%20matrix.png)
![GitHub Image](https://github.com/argalusmp/laptop_price_prediction_ML/blob/main/images/Screenshot%202024-03-22%20180026.png)
Berdasarkan visualisasi diatas dapat diketahui bahwa:

- RAM dan Storage memiliki korelasi untuk harga yang cukup penting
- Kapasitas RAM paling banyak ada dibawah 20GB dan Storage dibawah 1000

![Github Image](https://github.com/argalusmp/laptop_price_prediction_ML/blob/main/images/brand_laptop.png)
Gambar diatas menunjukan bahwa brand memiliki kepercayaan sehingga memiliki pembelian product terbanyak.

## Data Preparation

Pada tahap ini, data dibersihkan dan diproses agar siap digunakan dalam pemodelan. Proses ini meliputi penanganan missing values, pengkodean variabel kategorikal, dan standarisasi beberapa kolom data numerik.

- Melakukan penanganan missing values dengan mengisinya sesuai dengan format data, misal pada GPU yang memiliki cukup banyak missing values, karena produk memang tidak memiliki GPU, sehingga saya mengisi nilai dengan teks 'None'

- Melakukan pengkodean dari kategorikal atau teks menjadi format numerik untuk model dengan LabelEncoder()

- Sebelum memasukkan ke model, saya melakukan standarisasi dengan StandardScaler() pada kolom yang memiliki range value cukup luas.

![Github Image](https://github.com/argalusmp/laptop_price_prediction_ML/blob/main/images/info_data.png)
Pada gambar info data sudah cukup bersih dan memiliki format numerik

## Modeling

Pada tahap ini, tiga algoritma machine learning digunakan: K-Nearest Neighbors, Random Forest, dan AdaBoosting. Hyperparameter tuning dilakukan dengan RandomizedSearchCV, RandomForestRegressor, KNeighborsRegressor, dan GradientBoostingRegressor untuk meningkatkan performa model.

- Membuat model dengan menggunakan algoritma K-Nearest Neighbors, alasan menggunakan algoritma ini karena ini merupakan algortima yang umum untuk menyelesaikan permasalahan regresi, kelebihan dari algoritma ini yaitu mudah dipahami dan cukup sederhana.
- Membuat model dengan menggunakan algoritma RandomForest, kelebihan dari menggunakan algoritma ini yaitu terdiri dari beberapa model dan bekerja secara bersama-sama untuk menyelesaikan masalah.
- Membuat model dengan algoritma AdaBoosting, dimana algoritma ini sangat powerfull dalam meningkatkan akurasi prediksi.

## Evaluation

Metrik evaluasi yang digunakan dalam proyek ini adalah Mean Squared Error (MSE). MSE adalah metrik yang umum digunakan dalam masalah regresi dan memberikan penilaian tentang seberapa dekat prediksi model dengan nilai sebenarnya.

Hasil evaluasi akan ditampilkan setelah proses pemodelan dan evaluasi selesai dilakukan. Hasil ini akan memberikan gambaran tentang performa model dan efektivitas algoritma yang digunakan.

![result](https://github.com/argalusmp/laptop_price_prediction_ML/blob/main/images/result1.png)
Terlihat pada gambar hasil dari ketiga algoritma yang dipakai ketika dihitung MSE model untuk training dan test dataset.

![result test](https://github.com/argalusmp/laptop_price_prediction_ML/blob/main/images/result2.png)
Hasil dari model ketika dicoba untuk memprediksi harga dari test dataset, dan menilai ketepatan dengan price aslinya.

Boosting dan RandomForest memiliki akurasi yang cukup tinggi.
