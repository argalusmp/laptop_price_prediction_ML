
# Laptop Price Prediction

## Domain Proyek

Proyek ini berfokus pada prediksi harga laptop menggunakan dataset yang tersedia di Kaggle. Prediksi harga laptop ini penting untuk membantu konsumen dalam membuat keputusan pembelian. Selain itu, ini juga dapat membantu penjual untuk menetapkan harga yang kompetitif.

### Latar Belakang

Laptop adalah salah satu barang elektronik yang paling sering diperdagangkan secara online. Harga laptop dapat bervariasi secara signifikan tergantung pada berbagai fitur dan spesifikasi, seperti merk, ukuran layar, jenis prosesor, kecepatan prosesor, memori, dan lainnya. Oleh karena itu, membangun model yang dapat memprediksi harga laptop berdasarkan fitur-fitur ini bisa sangat berguna.

Dalam proyek ini, akan mencoba membangun model prediktif untuk harga laptop menggunakan dataset dari Kaggle. Proyek ini akan menggunakan beberapa algoritma machine learning, termasuk *K-Nearest Neighbors, Random Forest,* dan *AdaBoosting*, serta  juga akan melakukan *hyperparameter tuning* untuk meningkatkan performa model. Capaian proyek ini akan membantu penjual dan pembeli laptop dalam bertransaksi.

## Business Understanding

### Problem Statements

Berdasarkan latar belakang masalah, rincian masalahnya adalah sebagai berikut:

- Bagaimana ini  dapat memprediksi harga laptop berdasarkan fitur-fitur tertentu?

- Algoritma *machine learning* apa yang paling efektif untuk memprediksi harga laptop?

### Goals

Untuk tujuan penyelesaiannya, antara lain:

- Membuat model prediktif yang dapat memprediksi harga laptop dengan akurasi yang tinggi.

- Menentukan algoritma machine learning terbaik untuk memprediksi harga laptop.

### Solution statments

Solusi yang dapat dilakukan :

- Membangun beberapa model pembelajaran mesin dan memilih model yang terbaik, disini  menggunakan algoritma *K-Nearest Neighbors, Random Forest* dan *AdaBoosting* untuk membangun model prediktif

- Melakukan *hyperparameter* *tuning* dengan *RandomizedSearchCV, RandomForestRegressor, KNeighborsRegressor*, dan *GradientBoostingRegressor* untuk meningkatkan performa model.

## Data Understanding

Data yang digunakan dalam proyek ini adalah dataset harga laptop yang mencakup berbagai fitur, seperti ukuran layar, RAM, penyimpanan, merek, dan lainnya. Dataset ini dapat diunduh dari [https://www.kaggle.com/datasets/juanmerinobermejo/laptops-price-dataset].

### Variabel-variabel pada Laptop Price dataset adalah sebagai berikut:

- *RAM*: Ukuran RAM laptop .

- *Storage*: Kapasitas penyimpanan laptop .

- *Screen*: Ukuran layar laptop.

- Brand: Merek laptop.

- Model: Model laptop.

- *CPU*: Tipe prosesor laptop.

- *Storage type*: Jenis penyimpanan laptop.

- *GPU*: Jenis kartu grafis laptop (jika ada).

- *Touch*: Menunjukkan apakah layar laptop mendukung fitur layar sentuh atau tidak.

### Exploratory Data Analysis and Visualization dataset

 Gambar 1. *Corellation Matrix* ![GitHub Image](https://github.com/argalusmp/laptop_price_prediction_ML/blob/main/images/correlation%20matrix.png?raw=true) 

 Pada Gambar 1, terlihat jelas bahwa antara *RAM*, *SSD* dan *GPU* memiliki korelasi yang paling tinggi terhadap *Final Price* .

Gambar 2. Sebaran nilai *RAM* dan *Storage*![GitHub Image](https://github.com/argalusmp/laptop_price_prediction_ML/blob/main/images/Screenshot%202024-03-22%20180026.png?raw=true)

Pada Gambar 2, menunjukkan bahwa kapasitas *RAM* dan *Storage* paling banyak pada sebaran data *RAM* dibawah 20GB dan *Storage* dibawah 1000.

Gambar 3. Sebaran data laptop berdasarkan kuantitas dari setiap *brand*.![Github Image](https://github.com/argalusmp/laptop_price_prediction_ML/blob/main/images/brand_laptop.png?raw=true)

Gambar diatas menunjukan bahwa brand memiliki kepercayaan sehingga memiliki pembelian product terbanyak.

Gambar 4. Sebaran data tiap nilai dari kolom *RAM, Storage, Screen* dan *Final Price* ![Github Image](https://github.com/argalusmp/laptop_price_prediction_ML/blob/main/images/distributionofquantity.png?raw=true)

Gambar 4 diatas menunjukkan kuantitas dari laptop dataset terhadap setiap *value* pada ke-empat kolom.

![Github Image](https://github.com/argalusmp/laptop_price_prediction_ML/blob/main/images/distributionofstatus.png?raw=true)Gambar 5. Sebaran data dari kolom status

Pada Gambar 5, menunjukkan bahwa laptop yang baru lebih banyak peminat daripada *Refurbished*.



## Data Preparation

Pada tahap ini, data dibersihkan dan diproses agar siap digunakan dalam pemodelan. Proses ini meliputi penanganan *missing values*, pengkodean variabel kategorikal, dan standarisasi beberapa kolom data numerik.

- Melakukan penanganan *missing values* dengan mengisinya sesuai dengan format data, misal pada GPU yang memiliki cukup banyak missing values, karena produk memang tidak memiliki GPU, sehingga  mengisi nilai dengan teks '*None*'. Hal ini menggunakan fungsi ```fillna()``` dari *pandas dataframe*

- Melakukan pengkodean dari kategorikal atau teks menjadi format numerik untuk model dengan *LabelEncoder()* pada setiap kolom yang ingin diubah menjadi berisi *value* numerik


- Sebelum memasukkan ke model,  melakukan standarisasi dengan *StandardScaler()* pada kolom yang memiliki range value cukup luas, pada kasus ini pada kolom *Storage* dan *Laptop*.

Setelah proses penyesuaian data maka akan didapatkan data dengan informasi seperti tabel dibawah ini:

| Colums        		| Non-Null  | Count | Dtype  |
| ---------------------:|:---------:| -----:| ------:|
| Ram      				| non-null 	| 2160 	| int64	 |
| Storage				| non-null	| 2160	| int64	 |
| Screen				| non-null	| 2160	| float64|
| Final Price			| non-null	| 2160	| float64|
| Laptop_Encoded		| non-null	| 2160	| int64	 |
| Status_Encoded		| non-null	| 2160	| int64	 |
| Brand_Encoded			| non-null	| 2160	| int64	 |
| Model_Encoded			| non-null	| 2160	| int64	 |
| CPU_Encoded		  	| non-null	| 2160	| int64	 |
| Storage type_Encoded	| non-null	| 2160	| int64	 |
| GPU_Encoded			| non-null	| 2160	| int64	 |
| Touch_Encoded			| non-null	| 2160	| int64	 |

Tabel 1. Clean Data
Pada data tabel 1 diatas  info data sudah cukup bersih dan memiliki format numerik.

 Selanjutnya tahapan membagi dataset kedalam data *train* dan juga data *test*, menggunakan package dari sklearn dengan pembagian 90% *train* dan 10% *test*.



## Modeling

Pada tahap ini, tiga algoritma machine learning digunakan: *K-Nearest Neighbors, Random Forest,* dan *AdaBoosting*. *Hyperparameter tuning* dilakukan dengan *RandomizedSearchCV, RandomForestRegressor, KNeighborsRegressor,* dan *GradientBoostingRegressor* untuk meningkatkan performa model.

 1.  Membuat model dengan menggunakan algoritma *K-Nearest Neighbors*, alasan menggunakan algoritma ini karena ini merupakan algortima yang umum untuk menyelesaikan permasalahan regresi, kelebihan dari algoritma ini yaitu mudah dipahami dan cukup sederhana.
		-   Ketika mendapatkan data baru yang akan diklasifikasikan, algoritma mengukur jarak antara data baru tersebut dengan setiap data latih yang telah ada.
		-   Kemudian, algoritma memilih k data latih terdekat (diukur dengan jarak) dengan data baru tersebut. "K" dalam KNN merupakan jumlah tetangga terdekat yang akan dipertimbangkan.
		-   Setelah itu, algoritma melakukan mayoritas voting untuk menentukan kelas dari data baru berdasarkan kelas mayoritas dari tetangga terdekatnya.
		-  Parameter yang digunakan untuk proyek ini untuk KNN hanyalah ```n_neighbors = 10``` , yang mana adalah jumlah tetangga terdekat yang diinginkan.

2.  Membuat model dengan menggunakan algoritma *RandomForest*, kelebihan dari menggunakan algoritma ini yaitu terdiri dari beberapa model dan bekerja secara bersama-sama untuk menyelesaikan masalah.
	-   Random Forest bekerja dengan menggunakan banyak pohon keputusan (decision trees).
	-   Setiap pohon dalam Random Forest dibangun secara acak dari subset data latih, dan pada setiap simpul dalam pohon, hanya sebagian kecil dari fitur yang dipertimbangkan untuk membagi data.
	-   Ketika akan mengklasifikasikan data baru, Random Forest meminta setiap pohon memberikan prediksi kelasnya.
	-   Hasil prediksi dari setiap pohon digunakan untuk melakukan voting, dan kelas dengan mayoritas voting akan menjadi prediksi akhir dari Random Forest.
	-  Parameter yang digunakan untuk model ini dalam kasus proyek adalah ```n_estimators=75, max_depth=32, random_state=33, n_jobs=-1 ```-   dimana n_estimator adalah  jumlah *trees* (pohon) di forest, max_depth: kedalaman *trees* dalam membelah (*splitting*) untuk membagi setiap node ke dalam jumlah pengamatan yang diinginkan, random_state digunakan untuk mengontrol  *random number generator* yang digunakan dan n_jobs adalah apakah pekerjaan dilakukan secara paralel atau tidak dengan -1 yaitu paralel.

3.  Membuat model dengan algoritma *AdaBoosting*, dimana algoritma ini sangat powerfull dalam meningkatkan akurasi prediksi.
	-    AdaBoosting bekerja dengan menggunakan beberapa model klasifikasi lemah (weak learner) secara berurutan.
	-   Pada setiap iterasi, AdaBoost memberi bobot yang lebih tinggi pada data yang salah diklasifikasikan oleh model sebelumnya, sehingga model berikutnya akan lebih fokus pada data yang sulit untuk diklasifikasikan.
	-   Prediksi akhir dibuat dengan menggabungkan prediksi dari setiap model dengan bobotnya masing-masing.
	-  Parameter yang digunakan dalam kasus ini adalah ``` learning_rate=0.1, random_state=77, n_estimators=100```dimana learning_rate adalah bobot yang diterapkan pada setiap regressor di masing-masing proses iterasi boosting, n_estimator adalah jumlah maksimum untuk dugaan di mana *Boosting* dihentikan dan random_state digunakan untuk mengontrol  *random number generator* yang digunakan.

## Evaluation

Metrik evaluasi yang digunakan dalam proyek ini adalah *Root Mean Squared Error* (RMSE). RMSE adalah metrik yang umum digunakan dalam masalah regresi dan memberikan penilaian tentang seberapa dekat prediksi model dengan nilai sebenarnya.

Rumus RMSE digunakan untuk mengukur seberapa akurat sebuah model dalam memprediksi nilai yang sebenarnya. RMSE menghitung rata-rata dari kuadrat selisih antara nilai prediksi dengan nilai yang sebenarnya, kemudian hasilnya diambil akar kuadrat.

Rumus RMSE dapat dituliskan sebagai berikut:
$$
RMSE = \sqrt{\frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2}
$$

di mana:
- \( n \) adalah jumlah sampel,
- \( y_i \) adalah nilai sebenarnya,
- \( ŷi \) adalah nilai prediksi.

RMSE memberikan informasi tentang seberapa baik model mampu memperkirakan nilai yang sebenarnya. 

Dengan menggunakan RMSE, dapat mengevaluasi kinerja model dalam memprediksi data dengan cara yang konsisten dan terukur.


Hasil evaluasi akan ditampilkan setelah proses pemodelan dan evaluasi selesai dilakukan. Hasil ini akan memberikan gambaran tentang performa model dan efektivitas algoritma yang digunakan.

![result](https://github.com/argalusmp/laptop_price_prediction_ML/blob/main/images/graph_error.png?raw=true)Gambar 6. Nilai error pada ketiga algoritma

Terlihat pada Gambar 6, hasil dari ketiga algoritma yang dipakai ketika dihitung MSE model untuk training dan test dataset.

Berikut adalah hasil test prediksi dari data test pada index 10:

| y_true | prediksi_KNN | prediksi_RF | prediksi_Boosting |
| ------:| ------------:| -----------:| -----------------:|
| 1045.94| 1206.0	    | 1059.5	  | 1250.3   		  |

Prediksi dari *RandomForest* memiliki nilai yang paling dekat dengan *y_true* data. Hasil ini cukup memuaskan dengan *gap* dari nilai sebenarnya tidak lebih dari 10% sehingga metode yang cocok digunakan dalam membangun model ini adalah algoritma *RandomForest* dari ketiga algoritma tersebut.

Model yang dibangun menggunakan *RandomForest*  ini dapat menyelesaikan masalah dan memenuhi *goals* atau tujuan dari proyek dalam menentukan harga dari laptop.



