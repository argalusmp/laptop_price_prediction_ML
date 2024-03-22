# Laporan Proyek Machine Learning - Vidi Septri Argalus Mp
## Laptop Price Prediction
### Domain Proyek
Proyek ini berfokus pada prediksi harga laptop berdasarkan berbagai fitur yang dimiliki oleh laptop tersebut. Tujuan dari proyek ini adalah untuk membantu konsumen dan penjual dalam menentukan harga yang tepat untuk laptop berdasarkan spesifikasi teknisnya.

### Business Understanding
- Menentukan faktor-faktor apa saja yang mempengaruhi harga sebuah laptop.
- Membangun model prediktif yang dapat memperkirakan harga laptop dengan akurasi tinggi berdasarkan fitur-fitur tertentu.

### Goals

- Mengidentifikasi variabel-variabel yang paling berpengaruh terhadap harga laptop.
- Membangun model prediktif yang dapat memprediksi harga laptop dengan MSE rata rata kurang dari   12% dari rentang harga laptop dalam dataset.


### Solution Statement
- Menerapkan teknik analisis regresi untuk mengidentifikasi variabel-variabel yang paling berpengaruh terhadap harga laptop.
- Menggunakan algoritma RandomForest dan K-Nearest Neighbors

### Data Understanding
Data yang digunakan dalam proyek ini adalah dataset harga laptop yang mencakup berbagai fitur, seperti ukuran layar, RAM, penyimpanan, merek, dan lainnya. Dataset ini dapat diunduh dari [https://www.kaggle.com/datasets/juanmerinobermejo/laptops-price-dataset].

Variabel-variabel dalam dataset ini mencakup:

- RAM: Ukuran RAM laptop .
- Storage: Kapasitas penyimpanan laptop .
- Screen: Ukuran layar laptop.
- Brand: Merek laptop.
- Model: Model laptop.
- CPU: Tipe prosesor laptop.
- Storage type: Jenis penyimpanan laptop.
- GPU: Jenis kartu grafis laptop (jika ada).
- Touch: Menunjukkan apakah layar laptop mendukung fitur layar sentuh atau tidak.

### Data Preparation
Proses persiapan data melibatkan langkah-langkah berikut:
- Memeriksa dan menghapus nilai-nilai yang hilang.
- Mengonversi variabel kategorikal atau object menjadi format yang sesuai untuk pemodelan.
- Penskalaan fitur-fitur numerik
![GitHub Image](/images/Screenshot%202024-03-22%20175945.png)
![GitHub Image](/images/Screenshot%202024-03-22%20180021.png)
![GitHub Image](/images/Screenshot%202024-03-22%20180026.png)
![GitHub Image](/images/correlation%20matrix.png)
![GitHub Image](/images/info_data.png)

### Modeling

Algoritma pada proyek ini melakukan pemodelan dengan 3 algoritma, yaitu:
- K-Nearest Neighbour  
- Random Forest
- Boosting

Disini juga melakukan hyperparameter tuning menggunakan RandomizedSearchCV, RandomForestRegressor , KNeighborsRegressor dan GradientBoostingRegressor



### Evaluation
Metrik evaluasi yang digunakan dalam proyek ini adalah MSE, yang mengukur seberapa baik model memprediksi harga laptop dibandingkan dengan nilai sebenarnya.

Hasil proyek ini menunjukkan bahwa model regresi linier memberikan MSE terendah, sehingga dipilih sebagai model terbaik untuk memprediksi harga laptop yaitu.
![GitHub Image](/images/result1.png)
![GitHub Image](/images/result2.png)
