# Analisis Prediktif untuk Penjualan Supermarket - Lanyta Setyani Gunawan
![inventory](https://github.com/MeiLing19/Predictive-Analytics-for-Supermarket-Sales/blob/main/Pict/Inventory.jpg)

## Domain Proyek
Proyek ini berfokus pada analisis penjualan *supermarket*. Pemahaman yang mendalam tentang pola penjualan di *supermarket* sangat penting bagi manajemen untuk mengoptimalkan strategi pemasaran, manajemen inventaris, dan pengalaman pelanggan.
### Latar Belakang
Dalam industri ritel, terutama di supermarket, kemampuan untuk memprediksi penjualan secara akurat sangat penting untuk operasi bisnis yang efektif dan pengambilan keputusan strategis. 
Prediksi penjualan melibatkan perkiraan volume penjualan di masa depan berdasarkan data historis, tren pasar, dan berbagai faktor eksternal. 
Proses analisis prediktif ini memainkan peran penting dalam mengoptimalkan manajemen inventaris, tingkat staf, dan perkiraan pendapatan.

### Mengapa masalah ini perlu dipecahkan?
Prediksi penjualan di *supermarket* memiliki dampak yang signifikan dalam beberapa aspek bisnis. Salah satunya adalah dalam manajemen persediaan, di mana menjaga keseimbangan inventaris yang tepat sangat penting untuk memenuhi permintaan pelanggan sambil meminimalkan biaya penyimpanan dan risiko kehabisan stok. Dengan prediksi penjualan yang akurat, *supermarket* dapat mengantisipasi permintaan untuk berbagai produk dan menyesuaikan tingkat inventaris mereka secara efisien. Selain itu, prediksi penjualan yang akurat juga membantu dalam pengoptimalan jumlah staf, di mana *supermarket* dapat menjadwalkan staf mereka dengan tepat untuk memenuhi permintaan pelanggan selama jam sibuk dan menghindari kelebihan staf selama periode yang lebih lambat. Informasi mengenai perkiraan pendapatan di masa depan juga sangat penting untuk penganggaran, perencanaan keuangan, dan menetapkan tujuan bisnis yang realistis. Analisis prediktif dalam peramalan penjualan juga berkontribusi pada kepuasan pelanggan dengan memastikan ketersediaan produk yang tepat pada waktu yang tepat. Pelanggan yang puas lebih cenderung untuk kembali, yang pada gilirannya meningkatkan loyalitas dan tingkat retensi pelanggan. Pada akhirnya, prediksi penjualan yang akurat akan berdampak positif pada profitabilitas *supermarket* dengan mengoptimalkan tingkat persediaan, mengurangi biaya penyimpanan, dan memaksimalkan potensi pendapatan, sehingga menjadikan *supermarket* lebih kompetitif di pasar.

## Business Understanding
### Pernyataan Masalah
Perkiraan penjualan yang tidak akurat dapat mengakibatkan kelebihan atau kekurangan stok produk di *supermarket*, menyebabkan kerugian finansial dan penurunan kepuasan pelanggan. 
Metode prediksi yang manual yang saat ini umum digunakan cenderung memakan waktu dan rentan terhadap kesalahan, yang dapat mengakibatkan ketidakpastian dalam manajemen persediaan barang.
### Tujuan
Dengan masalah yang ada tersebut maka pihak *supermarket* akan membuat analisis prediktif dengan tujuan sebagai berikut. 
1. Mengembangkan model prediktif yang dapat memperkirakan penjualan *supermarket* secara akurat untuk mengatasi masalah ketidakpastian dalam manajemen persediaan.
2. Mengurangi biaya persediaan dengan mengoptimalkan tingkat stok barang berdasarkan prediksi permintaan, sehingga meminimalkan kerugian akibat kelebihan atau kekurangan persediaan.
### Solusi
Berdasarkan permasalahan dan tujuan yang ada, solusinya adalah sebagai berikut.
1. Menerapkan algoritma *Linear Regression* dan *Decision Trees Regression* untuk memprediksi penjualan.
2. Menyempurnakan parameter model menggunakan penyetelan hiperparameter untuk meningkatkan akurasi.

## Data Understanding
### Dataset
Dataset bersumber dari Kaggle, berikut merupakan tautannya [Source](https://www.kaggle.com/code/mhmdkardosha/market-analysis/input)

Supermarket_Sales.csv berisi data-data sebagai berikut.

|    | Invoice ID | Branch |   City   | Customer type | Gender |     Product line     | Unit price | Quantity | Tax 5% |   Total   |    Date    |  Time  |   Payment   |   cogs  | gross margin percentage | gross income | Rating |
|---:|-----------:|-------:|---------:|--------------:|-------:|---------------------:|-----------:|---------:|-------:|----------:|-----------:|-------:|------------:|--------:|------------------------:|-------------:|-------:|
| 0  | 750-67-8428|    A   |  Yangon  |     Member    | Female | Health and beauty    |   74.69    |     7    | 26.1415| 548.9715  |  1/5/2019  | 13:08  |  Ewallet    |  522.83 |        4.761905         |    26.1415   |   9.1  |
| 1  | 226-31-3081|    C   | Naypyitaw|     Normal    | Female |Electronic accessories|   15.28    |     5    |  3.8200|  80.2200  |  3/8/2019  | 10:29  |   Cash      |   76.40 |        4.761905         |     3.8200   |   9.6  |
| 2  | 631-41-3108|    A   |  Yangon  |     Normal    |  Male  | Home and lifestyle   |   46.33    |     7    | 16.2155| 340.5255  |  3/3/2019  | 13:23  | Credit card |  324.31 |        4.761905         |    16.2155   |   7.4  |
| 3  | 123-19-1176|    A   |  Yangon  |     Member    |  Male  | Health and beauty    |   58.22    |     8    | 23.2880| 489.0480  |  1/27/2019 | 20:33  |  Ewallet    |  465.76 |        4.761905         |    23.2880   |   8.4  |
| 4  | 373-73-7910|    A   |  Yangon  |     Normal    |  Male  | Sports and travel    |   86.31    |     7    | 30.2085| 634.3785  |  2/8/2019  | 10:37  |  Ewallet    |  604.17 |        4.761905         |    30.2085   |   5.3  |
| .. |    ...     |  ...   |   ...    |      ...      |  ...   |        ...           |    ...     |    ...   |   ...  |   ...     |    ...     |  ...   |   ...       |   ...   |           ...           |      ...     |  ...   |
| 995| 233-67-5758|    C   | Naypyitaw|     Normal    |  Male  | Health and beauty    |   40.35    |     1    |  2.0175|  42.3675  |  1/29/2019 | 13:46  |  Ewallet    |   40.35 |        4.761905         |     2.0175   |   6.2  |
| 996| 303-96-2227|    B   | Mandalay |     Normal    | Female | Home and lifestyle   |   97.38    |    10    | 48.6900| 1022.4900 |  3/2/2019  | 17:16  |  Ewallet    |  973.80 |        4.761905         |    48.6900   |   4.4  |
| 997| 727-02-1313|    A   |  Yangon  |     Member    |  Male  | Food and beverages   |   31.84    |     1    |  1.5920|  33.4320  |  2/9/2019  | 13:22  |   Cash      |  31.84  |        4.761905         |     1.5920   |   7.7  |
| 998| 347-56-2442|    A   |  Yangon  |     Normal    |  Male  | Home and lifestyle   |   65.82    |     1    |  3.2910|  69.1110  |  2/22/2019 | 15:33  |   Cash      |  65.82  |        4.761905         |     3.2910   |   4.1  |
| 999| 849-09-3807|    A   |  Yangon  |     Member    | Female | Fashion accessories  |   88.34    |     7    | 30.9190| 649.2990  |  2/18/2019 | 13:28  |   Cash      |  618.38 |	  4.761905         |    30.9190	  |   6.6  |

Data terdiri dari 1000 baris × 17 kolom
### Kondisi Data

Bersih, tidak ada nilai yang hilang. Hal ini dibuktikan dengan *output* dari pembahasan selanjutnya yaitu bagian persiapan data.
### Variabel

Variabel dalam set data Penjualan *Supermarket* adalah sebagai berikut:
- Unit price: harga satuan produk
- Quantity: jumlah produk yang dibeli
- Tax 5%: Pajak 5% dari total harga
- Total: total harga pembelian
- cogs: harga pokok penjualan
- gross margin percentage: persentase margin kotor
- gross income: pendapatan kotor
- Rating: penilaian produk oleh pelanggan
- Branch_A, Branch_B, Branch_C: cabang-cabang toko supermarket.
- City_Mandalay, City_Naypyitaw, City_Yangon: kota tempat toko supermarket berada.
- Customer type_Member, Customer type_Normal: jenis pelanggan (anggota atau bukan anggota)
- Gender_Female, Gender_Male: jenis kelamin pelanggan.
- Product line_Electronic accessories, Product line_Fashion accessories, Product line_Food and beverages, Product line_Health and beauty, Product line_Home and lifestyle, Product line_Sports and travel: jenis produk.
- Payment_Cash, Payment_Credit card, Payment_Ewallet: metode pembayaran

## Korelasi antar Variabel
Korelasi antar variabel digunakan untuk memahami seberapa kuat hubungan atau hubungan linier antara dua variabel dalam sebuah dataset. 

Dalam konteks analisis data, korelasi memberikan informasi tentang arah dan kekuatan hubungan antara variabel-variabel tersebut.
![korelasi](https://github.com/MeiLing19/Predictive-Analytics-for-Supermarket-Sales/blob/main/Pict/Korelasi%20antar%20Variabel.png)

Catatan :

Warna yang lebih gelap menunjukkan korelasi yang lebih tinggi, sementara warna yang lebih terang menunjukkan korelasi yang lebih rendah atau bahkan tidak ada korelasi.

### Jenis Data
Jenis data yang dimaksudkan disini adalah *numerical features* dan *categorical features*. Cara menentukannya dengan kode sebagai berikut.
numerical_data = data.select_dtypes(include=['int'])
numeric = data.select_dtypes(include=['float'])

categorical_data = data.select_dtypes(include=['object'])

**Numerical Features**
*Numerical Features* adalah fitur dalam dataset yang memiliki nilai berupa angka atau numerik. Fitur-fitur ini dapat diperlakukan sebagai variabel kontinu atau diskrit tergantung pada sifatnya.
Seperti kode diatas yang termasuk *numerical features* adalah data yang tipe datanya berupa angka(dalam dataset ini hanya ada integer dan float).
Berikut merupakan *numerical features*.
- Int(bilangan bulat)
  *Quantity, Month*
  
- Float (bilangan bernilai desimal)
  *Unit price, Tax 5%, Total, cogs, gross margin percentage, gross income, Rating*

**Categorical Features:**
Categorical features adalah fitur dalam dataset yang memiliki nilai berupa kategori atau label diskrit. Fitur-fitur ini tidak memiliki urutan atau hubungan ordinal di antara kategori-kategorinya.
Seperti kode diatas yang termasuk *categorical features* adalah data '*object*' yang tipe datanya berupa teks atau string.
Berikut merupakan *categorical features*.
- Object(teks atau string)
  *Invoice ID, Branch, City, Customer type, Gender, Product line, Time, Payment*

## Data Preparation

Pada tahap ini, data mentah yang diperoleh dari sumber akan diolah sehingga siap untuk digunakan dalam pemodelan.

### Mengidentifikasi dan Menampilkan Jumlah Nilai yang Hilang

missing_values = data.isnull().sum()

- Metode isnull() memeriksa nilai yang hilang dalam set data, dan fungsi sum() menghitung jumlah total nilai yang hilang untuk setiap kolom.
print(missing_values)
- Variabel missing_values berisi jumlah nilai yang hilang untuk setiap kolom. Mencetak missing_values memberikan ringkasan jumlah nilai yang hilang di setiap kolom dataset

**Output** :

Invoice ID                 0

Branch                     0

City                       0

Customer type              0

Gender                     0

Product line               0

Unit price                 0

Quantity                   0

Tax 5%                     0

Total                      0

Date                       0

Time                       0

Payment                    0

cogs                       0

gross margin percentage    0

gross income               0

Rating                     0

dtype: int64

- Berdasarkan *output*, tidak ada nilai *null* atau NaN dalam dataset karena jumlahnya nol untuk setiap kolom.
Oleh karena itu, tidak ada langkah tambahan yang diperlukan untuk menangani nilai yang hilang dalam tahap pembersihan data.
Data sudah bersih dan siap digunakan untuk analisis lebih lanjut.

## Pemodelan

### Regresi Linier
**Tahapan Pemodelan**
- Membagi data menjadi fitur (X) dan target (y).
- Membagi data menjadi data training dan data testing.
- Membuat model Regresi Linier.
- Melatih model menggunakan data latih.
- Menguji model menggunakan data uji.
  
**Parameter yang digunakan**
  fit_intercept (default=True)
  
- Menentukan apakah akan menghitung intersep (b) dalam model regresi linier. Jika disetel False, garis regresi akan melewati titik (0,0).
  normalize (default=False)

  Menentukan apakah fitur akan dinormalisasi sebelum regresi. Normalisasi dilakukan dengan mengurangi rata-rata dan membaginya dengan standar deviasi masing-masing fitur.
  
**Keuntungan**
- Sederhana dan mudah diinterpretasikan.
- Cocok untuk kasus-kasus di mana hubungan antara fitur dan target bersifat linier.
  
**Kekurangan**
- Rentan terhadap asumsi linearitas dan independensi.
- Tidak efektif dalam menangani hubungan non-linear antara fitur dan target.

## Decision Trees Regression
**Tahapan Pemodelan**
- Membagi data menjadi fitur (X) dan target (y).
- Membagi data menjadi data latih dan data uji.
- Membuat model Decision Trees Regression.
- Melatih model menggunakan data latih.
- Menguji model menggunakan data uji.
  
**Parameter yang digunakan**
  random_state = 42
  
- Parameter ini digunakan untuk menentukan seed yang digunakan dalam proses pengacakan pada algoritma.
Mengatur nilai random_state akan memastikan bahwa hasilnya konsisten setiap kali kode dijalankan.

**Keuntungan**
- Dapat menangani hubungan non-linear antara fitur dan target.
- Mudah dipahami dan diinterpretasikan.
  
**Kekurangan**
- Rentan terhadap overfitting terutama jika tidak diatur dengan baik.
- Tidak stabil, perubahan kecil pada data dapat menghasilkan tree yang sangat berbeda.

## Evaluasi
Dalam proyek ini, metrik evaluasi yang digunakan adalah Mean Squared Error (MSE), Mean Absolute Error (MAE), dan R-squared Score (R^2).
1. **Mean Squared Error (MSE)**
   
   MSE mengukur rata-rata kuadrat dari perbedaan antara nilai prediksi dan nilai aktual.
   
   MSE memberikan informasi tentang seberapa dekat prediksi rata-rata dengan nilai aktual. Nilai MSE yang lebih rendah menunjukkan kinerja model yang lebih baik.
2. **Rata-rata Kesalahan Mutlak (MAE)**
   
   MAE mengukur rata-rata nilai absolut dari perbedaan antara nilai prediksi dan nilai aktual.
   
   MAE juga memberikan informasi tentang seberapa dekat prediksi rata-rata dengan nilai aktual, tetapi tidak terpengaruh oleh kuadrat perbedaan, sehingga lebih toleran terhadap pencilan.
3. **R-squared Score (R^2)**
   
   R-squared mengukur seberapa baik variabilitas dalam data dijelaskan oleh model. Nilai R-squared berkisar antara 0 hingga 1, di mana 1 menunjukkan bahwa model sangat cocok dengan data.
   
   R-squared memberikan persentase variabilitas dalam variabel dependen yang dapat dijelaskan oleh model.
   
   Semakin dekat nilai R-squared ke 1, semakin baik modelnya.
   
Dalam mengevaluasi hasil proyek, kami akan meninjau nilai MSE, MAE, dan R^2 untuk memahami seberapa baik model kami memprediksi penjualan supermarket. Menginterpretasikan nilai-nilai ini akan memberikan wawasan tentang kinerja model dalam memperkirakan penjualan.

## Hasil
**Regresi Linier**
- Mean Squared Error (MSE): "2.56 × 10^-26"

  Sangat mendekati nol, mengindikasikan kemampuan prediksi model yang nyaris sempurna.
- Mean Absolute Error (MAE): "1.28×10^-13"

  Sangat kecil, menunjukkan ketepatan yang tinggi dalam memprediksi data
- R-squared Score (R^2): 1.0

  Menunjukkan kemampuan model untuk menjelaskan semua variabilitas dalam data

**Decision Trees Regressions**
- Mean Squared Error (MSE): 2.34

  Lebih besar dari Regresi Linier, menunjukkan lebih banyak variabilitas dalam data yang diprediksi
  
- Mean Absolute Error (MAE): 0.92

  Lebih besar dari Regresi Linier, menunjukkan akurasi yang sedikit lebih rendah dalam memprediksi data
  
- R-squared Score (R^2):  0.99996

  Sangat mendekati 1,0, menunjukkan kecocokan model yang sangat baik dengan data, meskipun sedikit lebih rendah dari Regresi Linier

## Kesimpulan
Berdasarkan evaluasi ini, model Regresi Linier tampaknya lebih cocok untuk memprediksi dataset Penjualan Supermarket karena kinerjanya yang sedikit lebih baik. 

Meskipun Decision Tree Regressor memberikan hasil yang sangat baik, Regresi Linier menunjukkan akurasi yang lebih tinggi dengan nilai error yang lebih rendah dan nilai R-squared yang sempurna.

Oleh karena itu, model Regresi Linier dapat dianggap sebagai pilihan utama untuk memprediksi penjualan supermarket.
