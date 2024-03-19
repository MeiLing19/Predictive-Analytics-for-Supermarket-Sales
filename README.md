# Analisis Prediktif untuk Penjualan Supermarket - Lanyta Setyani Gunawan
![inventory](https://github.com/MeiLing19/Predictive-Analytics-for-Supermarket-Sales/blob/main/Pict/Inventory.jpg)

## Domain Proyek
Proyek ini berfokus pada analisis penjualan supermarket. Pemahaman yang mendalam tentang pola penjualan di supermarket sangat penting bagi manajemen untuk mengoptimalkan strategi pemasaran, manajemen inventaris, dan pengalaman pelanggan.
### Latar Belakang
Dalam industri ritel, terutama di supermarket, kemampuan untuk memprediksi penjualan secara akurat sangat penting untuk operasi bisnis yang efektif dan pengambilan keputusan strategis. 
Prediksi penjualan melibatkan perkiraan volume penjualan di masa depan berdasarkan data historis, tren pasar, dan berbagai faktor eksternal. 
Proses analisis prediktif ini memainkan peran penting dalam mengoptimalkan manajemen inventaris, tingkat staf, dan perkiraan pendapatan.

### Mengapa masalah ini perlu dipecahkan?
Prediksi penjualan di --supermarket-- memiliki dampak yang signifikan dalam beberapa aspek bisnis. Salah satunya adalah dalam manajemen persediaan, di mana menjaga keseimbangan inventaris yang tepat sangat penting untuk memenuhi permintaan pelanggan sambil meminimalkan biaya penyimpanan dan risiko kehabisan stok. Dengan prediksi penjualan yang akurat, --supermarket-- dapat mengantisipasi permintaan untuk berbagai produk dan menyesuaikan tingkat inventaris mereka secara efisien. Selain itu, prediksi penjualan yang akurat juga membantu dalam pengoptimalan jumlah staf, di mana --supermarket-- dapat menjadwalkan staf mereka dengan tepat untuk memenuhi permintaan pelanggan selama jam sibuk dan menghindari kelebihan staf selama periode yang lebih lambat. Informasi mengenai perkiraan pendapatan di masa depan juga sangat penting untuk penganggaran, perencanaan keuangan, dan menetapkan tujuan bisnis yang realistis. Analisis prediktif dalam peramalan penjualan juga berkontribusi pada kepuasan pelanggan dengan memastikan ketersediaan produk yang tepat pada waktu yang tepat. Pelanggan yang puas lebih cenderung untuk kembali, yang pada gilirannya meningkatkan loyalitas dan tingkat retensi pelanggan. Pada akhirnya, prediksi penjualan yang akurat akan berdampak positif pada profitabilitas --supermarket-- dengan mengoptimalkan tingkat persediaan, mengurangi biaya penyimpanan, dan memaksimalkan potensi pendapatan, sehingga menjadikan --supermarket-- lebih kompetitif di pasar.

## Business Understanding
### Pernyataan Masalah
Perkiraan penjualan yang tidak akurat dapat mengakibatkan kelebihan atau kekurangan stok produk di --supermarket--, menyebabkan kerugian finansial dan penurunan kepuasan pelanggan. 
Metode prediksi yang manual yang saat ini umum digunakan cenderung memakan waktu dan rentan terhadap kesalahan, yang dapat mengakibatkan ketidakpastian dalam manajemen persediaan barang.
### Tujuan
Dengan masalah yang ada tersebut maka pihak --supermarket-- akan membuat analisis prediktif dengan tujuan sebagai berikut. 
1. Mengembangkan model prediktif yang dapat memperkirakan penjualan supermarket secara akurat untuk mengatasi masalah ketidakpastian dalam manajemen persediaan.
2. Mengurangi biaya persediaan dengan mengoptimalkan tingkat stok barang berdasarkan prediksi permintaan, sehingga meminimalkan kerugian akibat kelebihan atau kekurangan persediaan.
### Solusi
Berdasarkan permasalahan dan tujuan yang ada, solusinya adalah sebagai berikut.
1. Menerapkan algoritma --Linear Regression-- dan --Decision Trees Regression-- untuk memprediksi penjualan.
2. Menyempurnakan parameter model menggunakan penyetelan hiperparameter untuk meningkatkan akurasi.

## Data Understanding
### Dataset
Saya mendapatkan dataset dari Kaggle, ini tautannya [Source](https://www.kaggle.com/code/mhmdkardosha/market-analysis/input)

Supermarket_Sales.csv termasuk fitur-fitur seperti harga satuan, jumlah, pajak, cabang, kota, jenis pelanggan, dll.
### Jumlah catatan

1000 baris × 17 kolom
### Kondisi Data

Bersih, tidak ada nilai yang hilang.
### Variabel

Variabel dalam set data Penjualan Supermarket adalah sebagai berikut:
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

## Persiapan Data

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

- Berdasarkan output, tidak ada nilai null atau NaN dalam dataset karena jumlahnya nol untuk setiap kolom.
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
   Rumus untuk MSE adalah :
   
   ![mse](https://github.com/MeiLing19/Predictive-Analytics-for-Supermarket-Sales/blob/main/Pict/MSE.png)
   
   MSE memberikan informasi tentang seberapa dekat prediksi rata-rata dengan nilai aktual. Nilai MSE yang lebih rendah menunjukkan kinerja model yang lebih baik.
2. **Rata-rata Kesalahan Mutlak (MAE)**
   
   MAE mengukur rata-rata nilai absolut dari perbedaan antara nilai prediksi dan nilai aktual.
   
   Rumus untuk MAE adalah:
   
   ![mae](https://github.com/MeiLing19/Predictive-Analytics-for-Supermarket-Sales/blob/main/Pict/MAE.png)
   
   MAE juga memberikan informasi tentang seberapa dekat prediksi rata-rata dengan nilai aktual, tetapi tidak terpengaruh oleh kuadrat perbedaan, sehingga lebih toleran terhadap pencilan.
3. **R-squared Score (R^2)**
   
   R-squared mengukur seberapa baik variabilitas dalam data dijelaskan oleh model. Nilai R-squared berkisar antara 0 hingga 1, di mana 1 menunjukkan bahwa model sangat cocok dengan data.
   
   Rumus untuk R-kuadrat adalah:
   
   ![r^2](https://github.com/MeiLing19/Predictive-Analytics-for-Supermarket-Sales/blob/main/Pict/R2Formulas.png)
   
   R-squared memberikan persentase variabilitas dalam variabel dependen yang dapat dijelaskan oleh model.
   
   Semakin dekat nilai R-squared ke 1, semakin baik modelnya.
   
Dalam mengevaluasi hasil proyek, kami akan meninjau nilai MSE, MAE, dan R^2 untuk memahami seberapa baik model kami memprediksi penjualan supermarket. Menginterpretasikan nilai-nilai ini akan memberikan wawasan tentang kinerja model dalam memperkirakan penjualan.

## Hasil
**Regresi Linier**
- Mean Squared Error (MSE): 2.56 × 10^-26

  Sangat mendekati nol, mengindikasikan kemampuan prediksi model yang nyaris sempurna.
- Mean Absolute Error (MAE): 1.28×10^-13

  Sangat kecil, menunjukkan ketepatan yang tinggi dalam memprediksi data
- R-squared Score (R^2): 1.0
  1.0

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
