# Laporan Proyek Machine Learning - Muhammad Haifan Ghani (MC012D5Y1825)

## Domain Proyek : Sosial

Living longer has been one of humanity’s greatest ambitions, and currently living more than 80 years is a realistic expectation in many countries, Life expectancy captures mortality along the entire life course and its improvement is positively associated with welfare and health [_(Martinez et al., 2021)_](https://pmc.ncbi.nlm.nih.gov/articles/PMC8489742/). Kutipan tersebut merupakan hal yang menjadi latar belakang bagi saya dalam menjalankan proyek Predictive Analytics ini, karena saya ingin mengetahui mengenai perbedaan Harapan Hidup (life expectancy) dari berbagai negara serta faktor-faktor yang mempengaruhinya, selain dari amerika yang merupakan ruang lingkup penelitian dari jurnal tentang "Life expectancy, healthy life expectancy, and burden of disease in older people in the Americas, 1990–2019: a population-based study."

Melalui Analisis yang dilakukan ini, diharapkan dapat ditemukan model yang tidak hanya akurat tetapi juga mudah diimplementasikan di berbagai konteks, membantu dalam upaya global dan utamanya indonesia dalam mengingkatkan Harapan Hidup (Life Expectancy) pada setiap warganya. Analisis ini juga akan menyoroti pentingnya pemahaman mendalam tentang faktor-faktor yang mempengaruhi Harapan Hidup (Life Expectancy), Memberikan wawasan yang signifikan dalam merumuskan kebijakan publik yang bertujuan meningkatkan angka harapan hidup secara lebih efektif.

## Business Understanding

### Problem Statements

Rumusan masalah dari topik yang diangkat adalah :
- Dari berbagai fitur yang ada, fitur manakah yang paling berpengaruh terhadap Angka Harapan Hidup (Life Expectancy) seseorang?
- Bagaimana mengetahui pengaruh dari riwayat dari fitur-fitur yang ada terhadap Angka Harapan Hidup (Life Expctancy) Seseorang?

### Goals

Tujuan dari menyelesaikan permasalahan diatas adalah :
- Mengetahui fitur apa sajakah yang memiliki korelasi paling tinggi terhadap Angka Harapan Hidup (Life Expectancy) seseorang
- Membuat model machine learning yang dapat memprediksi pengaruh dari riwayat fitur-fitur yang ada terhadap besar Angka Harapan Hidup (Life Expectancy) seseorang

### Solution Statement

- Melakukan analisa pada data untuk memahami fitur-fitur yang mempengaruhi Angka Harapan Hidup (Life Expectancy) seseorang, dengan menerapkan visualisasi pada data untuk mengetahui korelasi antar fitur
- Menggunakan beberapa algoritma machine learning berbeda untuk membandingkan performa tiap modelnya, hal ini bertujuan untuk mendapatkan algoritma yang memiliki akurasi paling tinggi dalam memperkirakan pengaruh dari fitur-fitur yang ada terhadap Angka Harapan Hidup (Life Expectancy) Seseorang.

## Data Understanding

di website kaggle diketahui bahwa Dataset ini menangkap detail tentang Angka Harapan Hidup (Life Expectancy) di suatu negara dan faktor-faktor yang mempengaruhinya. Dataset ini diambil dari hasil penelitian seseorang. Terdapat total 1649 baris dan 22 kolom. saya mencantumkan detail mengenai fitur-fitur yang ada dari dataset yang digunakan pada tabel dibawah.

**Informasi Dataset**

| **Jenis**        | **Keterangan**                                                                         |
|------------------|----------------------------------------------------------------------------------------|
| **Title**        | Health and Demographics Dataset                                                        |
| **Source**       | [Kaggle](https://www.kaggle.com/datasets/uom190346a/health-and-demographics-dataset)   |                                               
| **Owner**        | [Laksika Tharmalingam](https://www.kaggle.com/uom190346a)                              |
| **License**      | Database: Open Database, Contents                                                      |
| **Visibility**   | Publik                                                                                 |
| **Tags**         | Social Science                                                                         |
| **Usability**    | 10.00                                                                                  |

### Berikut adalah informasi mengenai variabel-variabel pada dataset yang didapat dari kaggle :

- Country: Negara dimana data diambil.
- Year: Tahun dimana data diambil.
- Status: Penjelasan mengenai negara tersebut Developing (berkembang) atau Developed (maju).
- Life Expectancy: Angka Harapan Hidup.
- Adult Mortality: Mengukur probabilitas kelangsungan hidup antara usia 15 hingga 60 per 1.000 penduduk..
- Infant Deaths: kesehatan bayi dengan melihat jumlah kematian bayi per 1.000 kelahiran hidup.
- Alcohol: rata-rata konsumsi alkohol dalam liter per kapita.
- Percentage Expenditure: pengeluaran kesehatan sebagai persentase dari GDP suatu negara.
- Hepatitis B:  cakupan imunisasi untuk Hepatitis B.
- Measles: dampak penyakit yang dapat dicegah melalui jumlah kasus yang dilaporkan per 1.000 penduduk.
- BMI:  rata-rata Indeks Massa Tubuh.
- Under-Five Deaths:  angka kematian anak dengan jumlah kematian di bawah usia lima tahun per 1.000 kelahiran hidup.
- Polio: cakupan imunisasi untuk Polio.
- Total Expenditure:  total pengeluaran kesehatan sebagai persentase GDP.
- Diphtheria: cakupan imunisasi untuk Diphteria.
- HIV/AIDS: prevalensi HIV/AIDS sebagai persentase populasi.
- GDP: data Produk Domestik Bruto.
- Population: populasi suatu negara.
- Thinness 1-19 Years: prevalensi anak-anak dan remaja berusia 1-19 tahun yang kurus.
- Thinness 5-9 Years: prevalensi anak-anak dan remaja berusia 5-9 tahun yang kurus.
- Income Composition of Resources: indeks komposit yang mencerminkan distribusi pendapatan dan akses sumber daya.
- Schooling: data rata-rata tahun sekolah.

### Exploratory Data Analysis - Deskripsi Variabel 

| #  | Column                           | Non-Null Count | Dtype    |
|----|----------------------------------|----------------|----------|
| 0  | Country                          | 1649 non-null  | object   |
| 1  | Year                             | 1649 non-null  | int64    |
| 2  | Status                           | 1649 non-null  | object   |
| 3  | Life expectancy                  | 1649 non-null  | float64  |
| 4  | Adult Mortality                  | 1649 non-null  | int64    |
| 5  | infant deaths                    | 1649 non-null  | int64    |
| 6  | Alcohol                          | 1649 non-null  | float64  |
| 7  | percentage expenditure           | 1649 non-null  | float64  |
| 8  | Hepatitis B                      | 1649 non-null  | int64    |
| 9  | Measles                          | 1649 non-null  | int64    |
| 10 | BMI                              | 1649 non-null  | float64  |
| 11 | under-five deaths                | 1649 non-null  | int64    |
| 12 | Polio                            | 1649 non-null  | int64    |
| 13 | Total expenditure                | 1649 non-null  | float64  |
| 14 | Diphtheria                       | 1649 non-null  | int64    |
| 15 | HIV/AIDS                         | 1649 non-null  | float64  |
| 16 | GDP                              | 1649 non-null  | float64  |
| 17 | Population                       | 1649 non-null  | float64  |
| 18 | thinness 1–19 years              | 1649 non-null  | float64  |
| 19 | thinness 5–9 years               | 1649 non-null  | float64  |
| 20 | Income composition of resources  | 1649 non-null  | float64  |
| 21 | Schooling                        | 1649 non-null  | float64  |

Dari output tersebut dikethaui bahwa :
- terdapat 2 kolom dengan data bertipe string
- terdapat 8 kolom dengan data bertipe integer
- terdapat 12 kolom dengan data bertipe float

| Statistic      | Year   | Life expectancy  | Adult Mortality  | infant deaths  | Alcohol | percentage expenditure   | Hepatitis B  | Measles  | BMI    | under-five deaths   | Polio  | Total expenditure  | Diphtheria  | HIV/AIDS  | GDP       | Population   | thinness 1–19 years  | thinness 5–9 years | Income composition of resources | Schooling |
|----------------|--------|------------------|------------------|----------------|---------|--------------------------|--------------|----------|--------|---------------------|--------|--------------------|-------------|-----------|-----------|--------------|----------------------|--------------------|---------------------------------|-----------|
| count          | 1649   | 1649             | 1649             | 1649           | 1649    | 1649                     | 1649         | 1649     | 1649   | 1649                | 1649   | 1649               | 1649        | 1649      | 1649      | 1649         | 1649                 | 1649               | 1649                            | 1649      |
| mean           | 2007.84| 69.30            | 168.22           | 32.55          | 4.53    | 689.97                   | 79.22        | 2224.49  | 38.13  | 44.22               | 82.53  | 5.96               | 84.16       | 1.94      | 5566.02   | 1.47e+07     | 4.85                 | 4.91               | 0.63                            | 12.12     |
| std            | 4.09   | 8.80             | 125.31           | 120.85         | 4.03    | 1759.23                  | 25.60        | 10085.80 | 19.75  | 162.90              | 33.45  | 2.30               | 21.58       | 6.03      | 11475.90  | 7.05e+07     | 4.60                 | 4.65               | 0.18                            | 2.80      |
| min            | 2000   | 44.00            | 1.00             | 0.00           | 0.01    | 0.00                     | 2.00         | 0.00     | 2.00   | 0.00                | 3.00   | 0.00               | 2.00        | 0.10      | 1.68      | 3.40e+01     | 0.10                 | 0.01               | 0.04                            | 4.20      |
| 25%            | 2005   | 64.40            | 77.00            | 1.00           | 0.81    | 37.44                    | 74.00        | 0.00     | 19.50  | 1.00                | 60.00  | 3.31               | 82.00       | 0.10      | 462.15    | 1.92e+05     | 1.60                 | 1.70               | 0.51                            | 10.30     |
| 50% (median)   | 2008   | 71.70            | 148.00           | 3.00           | 3.79    | 146.10                   | 89.00        | 15.00    | 43.70  | 4.00                | 90.00  | 5.84               | 92.00       | 0.60      | 1592.57   | 1.42e+06     | 3.00                 | 3.20               | 0.67                            | 12.30     |
| 75%            | 2011   | 75.00            | 227.00           | 22.00          | 7.34    | 509.39                   | 96.00        | 373.00   | 55.80  | 29.00               | 97.00  | 7.47               | 97.00       | 0.70      | 4718.51   | 7.66e+07     | 7.10                 | 7.10               | 0.75                            | 14.00     |
| max            | 2015   | 89.00            | 723.00           | 1600.00        | 17.87   | 18961.35                 | 99.00        | 131441.00| 77.10  | 2100.00             | 99.00  | 14.39              | 99.00       | 50.60     | 119172.74 | 1.29e+09     | 27.20                | 28.20              | 0.94                            | 20.70     |

Fungsi diatas menjelaskan informasi statistik dengan penjelasan sebagai berikut :

- Count adalah jumlah sampel pada data.
- Mean adalah nilai rata-rata.
- Std adalah standar deviasi.
- Min yaitu nilai minimum setiap kolom.
- 25% adalah kuartil pertama. Kuartil adalah nilai yang menandai batas interval dalam empat bagian sebaran yang sama.
- 50% adalah kuartil kedua, atau biasa juga disebut median (nilai tengah). - 75% adalah kuartil ketiga.
- Max adalah nilai maksimum.

| Jumah Baris                           | Jumlah Kolom |
|---------------------------------------|--------------|
| 1649                                  | 22           |


### Exploratory Data Analysis - Missing Value & Outlier

**Mengecek Missing Value dan Anomali pada Data**

| Data Dupliat                        |
|-------------------------------------|
| 0                                   |

Setelah dilakukan pengecekan untuk data duplikat, saya mendapati bahwa dataset tidak memiliki data duplikat, selanjutnya kita akan mengecek ada atau tidaknya missing value pada data.

| Column                           | Missing Values |
|----------------------------------|----------------|
| Country                          | 0              |
| Year                             | 0              |
| Status                           | 0              |
| Life expectancy                  | 0              |
| Adult Mortality                  | 0              |
| infant deaths                    | 0              |
| Alcohol                          | 0              |
| percentage expenditure           | 0              |
| Hepatitis B                      | 0              |
| Measles                          | 0              |
| BMI                              | 0              |
| under-five deaths                | 0              |
| Polio                            | 0              |
| Total expenditure                | 0              |
| Diphtheria                       | 0              |
| HIV/AIDS                         | 0              |
| GDP                              | 0              |
| Population                       | 0              |
| thinness 1–19 years              | 0              |
| thinness 5–9 years               | 0              |
| Income composition of resources  | 0              |
| Schooling                        | 0              |

Setelah dilakukan pengecekan missing value, terlihat juga bahwa tidak terdapat missing value pada dataset, berikutnya kita akan mengecek, apakah terdapat data yang berisi nilai 0

| Column                           | Zero Values |
|----------------------------------|--------------|
| Country                          | 0            |
| Year                             | 0            |
| Status                           | 0            |
| Life expectancy                  | 0            |
| Adult Mortality                  | 0            |
| infant deaths                    | 395          |
| Alcohol                          | 0            |
| percentage expenditure           | 5            |
| Hepatitis B                      | 0            |
| Measles                          | 554          |
| BMI                              | 0            |
| under-five deaths                | 353          |
| Polio                            | 0            |
| Total expenditure                | 0            |
| Diphtheria                       | 0            |
| HIV/AIDS                         | 0            |
| GDP                              | 0            |
| Population                       | 0            |
| thinness 1–19 years              | 0            |
| thinness 5–9 years               | 0            |
| Income composition of resources  | 48           |
| Schooling                        | 0            |

Dapat dilihat bahwa terdapat nilai 0 pada kolom :
- Infant deaths
- Percentage expenditure
- Measles
- under-five deaths
- Income composition of resources

Namun disini saya tidak bisa menghapus nilai 0 tersebut, karena kolom yang berisi nilai 0 paling banyak adalah 554 kolom, yang artinya saya akan menhaous hampir 50% dari keseluruhan dataset, oleh karena itu saya hanya akan mengisi nilai 0 tersebut dengan mean, pada data yang tidak masuk akal jika berisi nilai 0 seperi :
- Percentage expenditure
- Income composition of resources

sedangkan pada fitur lainnya akan saya biarkan bernilai 0, karena jika saya isi dengan median, hal tersebut akan mengacaukan informasi pada fitur tersebut, contohnya seperti, jika saya mengisi mean pada data infant deaths, maka hal tersebut akan mengacaukan informasi pada data, karena memang mungkin saja terjadi tidak adanya kematian pada bayi ketika data tersebut diambil.

**Melakukan visualisasi data dengan boxplot pada tipa numerik** 

- Kita bisa mengunakan Box Plot untuk mengetahui, apakah suatu data dikatan Outlier
- Berikut merupakan penjelasan nilai statistik pada box plot
![Box Plot Illustration](https://github.com/Ganskuy/Submission_PredictiveAnalytics/blob/a908ebec48b594de06188ef5ebd6136b5730553c/resources/ilustrasi_outlier.jpg)
dari ilustrasi diatas dapat disimpulkan bahwa, data yang melebihi nilai minimum atau maksimum dikatakan sebagai outlier
- Outlier merupakan sesuatu yang harus kita tangani dalam membangun model machine learning, karena outlier ini bisa dianggap sebagai noise oleh model dan akan mengurangi performa model.
- Kemudian, dibawah ini adalah box plot dari dataset yang saya gunakan :
![Box Plot Illustration](https://github.com/Ganskuy/Submission_PredictiveAnalytics/blob/a1f6569fcc7dd83ab646ba11bf93757471c8f31d/resources/boxplot.png)
- Kita dapat melihat bahwa semua fitur numerik kecuali BMI, Income composition of resources, dan Year, memiliki outlier, kemudian kita akan menghilangkan outlier tersebut menggunakan IQR Method
- IQR (Interquartile) Methods merupakan salah satu metode yang umum digunakan dalam menangani outlier, metode ini menggunakan jarak antar kuartil sebagai nilai tengah, dan data yang berada diluar itu akan dianggap sebagai outlier
![Box Plot Illustration](https://github.com/Ganskuy/Submission_PredictiveAnalytics/blob/5bf98dcd691f49a1425776db0e7306bfc725409b/resources/Screenshot%202025-05-25%20at%2017.55.42.png)
- Q1 adalah Nilai dibawah 25% data
- Q3 adalah nilai diatas 75% data
- Pada metode IQR, data akan dikatakan sebagai Outlier jika:
![Box Plot Illustration](https://github.com/Ganskuy/Submission_PredictiveAnalytics/blob/fd821df3fe2b84ac9516cff0f350beefb7839ec3/resources/Screenshot%202025-05-25%20at%2018.01.06.png)

### Exploratory Data Analysis - Univariate Analysis
Tujuan utama dari univariate analysis adalah untuk memahami karakteristik dasar dari satu variabel secara individual.

**Univariate Analysis - Fitur Kategori**

![Box Plot Illustration](https://github.com/Ganskuy/Submission_PredictiveAnalytics/blob/ce66893e8ce796a5047f9c512906c9c36ce2b903/resources/univariate_country.png)
dari visualisasi tersebut, kita dapat menyimpulkan bahwa:
- sebagian besar sampel berasal dari negara Albania dengan persentase tertinggi, yaitu sebesar 2.4%
- sampel paling sedikit berasa dari negara Sri Lanka, Haiti, Guinea, Turkey, dan Croatia dengan masing-masingnya memiliki persentase sebesar 0.1%

![Box Plot Illustration](https://github.com/Ganskuy/Submission_PredictiveAnalytics/blob/ce66893e8ce796a5047f9c512906c9c36ce2b903/resources/univariate_status.png)
dari visualisasi tersebut, kita dapat menyimpulkan bahwa, sebagian besar negara dari sampe yang diambil merupakan negara berkembang (developing), dan sebagian kecilnya berasal dari negara maju (developed)

**Univariate Analysis - Fitur Numerik**

![Box Plot Illustration](https://github.com/Ganskuy/Submission_PredictiveAnalytics/blob/ce66893e8ce796a5047f9c512906c9c36ce2b903/resources/univariate_numerik.png)
dari visualisasi diatas, kita akan berfokus pada fitur target dari proyek ini, yaitu life expectancy, dan kita bisa menyimpulkan beberapa hal :
- Angka Life Expectancy meningkat seiring dengan bertambahnya jumlah sampel
- hanya sedikit sampel yang memiliki life expectancy diatas 65 tahun
- dapat dilihat dari sampel tersebut bahwa, rata-rata life expectancy berada di sekitar 25-55 tahun
- Distribusi Life Expectancy cenderung miring ke kanan (left-skewed), yang menunjukkan bahwa nilai median (nilai tengah) berada di kuartil ketiga dan lebih tinggi daripada nilai rata-rata.

### Exploratory Data Analysis - Multivariate Analysis
Multivariate Analysis dilakukan untuk melakukan visualisasi data dengan tujuan memahami keterkaitan antara dua atau lebih fitur dalam suatu dataset. Metode ini berguna untuk menemukan pola, hubungan, atau interaksi antar fitur yang dapat memberikan pemahaman yang lebih mendalam terhadap struktur data secara keseluruhan.

**Multivariate Analysis - Fitur Kategori**

![Box Plot Illustration](https://github.com/Ganskuy/Submission_PredictiveAnalytics/blob/ce66893e8ce796a5047f9c512906c9c36ce2b903/resources/multivariate_country-life.png)
![Box Plot Illustration](https://github.com/Ganskuy/Submission_PredictiveAnalytics/blob/ce66893e8ce796a5047f9c512906c9c36ce2b903/resources/multivariate_status-life.png)
Dari visualisasi diatas, kita mendapati bahwa :
- Pada visualisasi Rata-rata life expectany terhadap country, terlihat bahwa life expectancy pada negara-negara yang terdapat pada dataset, cukup tinggi yaitu diatas 65 tahun
- Pada visualisasi Rata-rata life expectany terhadap status, terlihat bahwa life expectancy pada negara-negara maju (developed) cenderung lebih tinggi ketimbang life expectancy pada negara berkembang (developing)

**Multivariate Analysis - Fitur Numerik**

![Box Plot Illustration](https://github.com/Ganskuy/Submission_PredictiveAnalytics/blob/ce66893e8ce796a5047f9c512906c9c36ce2b903/resources/multivariate_numerik-life.png)
disini kita menggunakan scatter plot dan rig plot untuk melihat hubungan antara fitur numerik terhadap fitur target, karena jika menggunakan pairplot, hasil visualisasi akan terlalu banyak sehingga menyulitkan kita dalam melihat insight dari visualisasi yang dilakukan, kemudian dari visualisasi diatas, dapat dilihat bahwa :
- Income Composition of Resources vs Life Expectancy : Terlihat adanya korelasi positif yang cukup kuat disini, bahwa semakin tinggi distribusi pendapatan dan fasilitas, semakin tinggi juga life expectancy
- Schooling vs Life Expectancy : Terlihat juga adanya korelasi positif yang kuat disini, bahwa semakin tinggi pendidikan yang ditempuh, semakin tinggi juga life expectancy

Untuk dapat melihat lebih jelas korelasi antar fitur, kita akan menggunakan Correlation Matrix

![Box Plot Illustration](https://github.com/Ganskuy/Submission_PredictiveAnalytics/blob/ce66893e8ce796a5047f9c512906c9c36ce2b903/resources/correlation_matrix.png)
dari correlation matrix diatas, kita dapat mengetahui bahwa :
- Income Composition of Resources memiliki korelasi yang kuat terhadap Life Expectancy, Fitur ini juga memiliki korelas yang kuat terhadap Schooling, hal ini cukup relevan mengingat orang yang mendapatkan fasilitas yang mendukung pasti akan menempuh pendidikan setinggi mungkin.
- Schooling terlihat memiliki korelasi yang kuat dengan Life Expectancy, fitur ini juga memiliki korelasi yang cukup kuat terhadap schooling, hal ini cukup relevan mengingat kesimpulan yang kita dapat sebelumnya, orang yang mendapatkan fasilitas yang mendukung pasti akan menempuh pendidikan setinggi mungkin.

Kesimpulan diatas juga menjawab pertanyaan kita diatas mengenai "fitur apa sajakah yang memiliki korelasi paling kuat dengan life expectancy" bahwa, Fasilitas yang didapat seseorang serta tingkat pendidikan seseorang memiliki korelasi yang kuat terhadap Life Expectancy, hal ini terbilang cukup relevan mengingat, seseorang yang menempuh pendidikan tinggi cenderung memiliki life expectancy yang tinggi pula karena tingginya mimpi yang biasanya dimiliki oleh seorang pelajar, dan seseorang yang mendapatkan fasilitas yang mendukung juga memiliki life expectancy yang tinggi

**Drop Fitur Berkorelasi Rendah**
Kemudian pada fitur-fitur yang memiliki korelasi rendah terhadap fitur target, yaitu Life Expectancyakan, kita drop, adapun fitur-fitur tersebut adalah :
- Year
- Adult Mortality
- infant deaths
- Measles
- under-five deaths
- HIV/AIDS
- Population
- thinness  1-19 years
- thinness 5-9 years

| Jumah Baris                           | Jumlah Kolom |
|---------------------------------------|--------------|
| 669                                   | 13           |

terlihat bahwa dimensi tereduksi menjadi 669 baris dan 13 kolom

## Data Preparation

Pada bagian ini ada empat tahap yang dapat dilakukan untuk mempersiapkan data yang, yaitu:

- Encoding fitur kategori.
- Reduksi dimensi dengan Principal Component Analysis (PCA).
- Pembagian dataset dengan fungsi train_test_split dari library sklearn.
- Standarisasi.

namun kali ini, saya hanya akan menggunakan 3 dari 4 proses diatas, karena proses reduksi dimensi disini tidak bisa saya lakukan, karena reduksi dimensi hanya bisa dilakukan jika terdapat fitur yang memiliki korelasi sangat kuat dan sama-sama menyimpan informasi yang serupa, contohnya fitur x,y, dan z yang sama-sama menyimpan informasi mengenai berat sebuah berlian, dan saya tidak mendapati adanya fitur seperti itu pada dataset yang digunakan. Sehingga, jika saya memaksakan untuk mereduksi dimensi dari dataset ini, hal tersebut akan mengacaukan informasi yang ada, dan membuat performa model menjadi buruk.

**Encoding fitur kategori**

pada dataset kita terdapat 2 fitur categorical yang akan diubah menjadi data numerik yaitu: 
- Fitur Country akan kita encode menggunakan Label Encoder karenaberisi banyak nama negara, dan akan menambahkan dimensi dataset secara signifikan jika menggunakan One-Hot Encoder
- Fitur Status akan kita encode menggunakan One-Hot Encoder karena hanya berisi 2 kemungkinan, yaitu Developing dan Developed, hal tersebut cocok dilakukan encoding menggunakan One-Hot Encoder karena data akan di-encode kedalam binary

Encoding perlu dilakukan terhadap Fitur kategori, karena sebagian besar algoritma machine learning tidak dapat bekerja secara langsung dengan data non-numerik, sehingga fitur yang memiliki tipe data non-numerik harus diubah terlebih dahulu menjadi numerik sebelum diproses oleh algoritma machine learning.

**Train-Test-Split**

Sebelum melakukan train-test-split, langkah awalnya adalah memisahkan antara fitur dan label. Variabel x digunakan untuk menyimpan fitur yang terdiri dari:

- Alcohol
- percentage expenditure
- Hepatitis B
- BMI
- Polio
- total expenditure
- Diphteria
- GDP
- Income composition of resources
- Schooling
- Country
- Status

Sedangkan variabel y digunakan untuk menyimpan label yaitu Life expectancy.

Selanjutnya, dilakukan train-test-split dengan pembagian data sebesar 90:10 antara data latih (train) dan data uji (test). data terbagi menjadi 602 untuk data latih dan 67 untuk data uji, dari total sebanyak 669 data.

**Standarisasi**

Algoritma machine learning akan menghasilkan performa yang lebih baik jika data yang digunakan memiliki skala yang relatif sama atau terdistribusi normal. Standarisasi mengubah skala fitur numerik agar memiliki distribusi standar, dengan standar deviasi 1 dan mean 0

Sehingga dilakukan standarisasi dengan StandardScaler pada 10 fitur yaitu:

- Alcohol
- percentage expenditure
- Hepatitis B
- BMI
- Polio
- total expenditure
- Diphteria
- GDP
- Income composition of resources
- Schooling

**Data prepration perlu dilakukan karena**

- Proses encoding diperlukan untuk mengubah data kategorikal menjadi format numerik karena sebagian besar algoritma machine learning tidak dapat memproses data non-angka secara langsung.
- Reduksi dimensi berguna untuk menyederhanakan kompleksitas data, mempercepat proses pelatihan model, serta membantu mengurangi kemungkinan terjadinya overfitting dan multikolinearitas.
- Pemisahan data ke dalam data latih dan data uji bertujuan untuk menilai performa model terhadap data yang belum pernah dilihat sebelumnya, sehingga dapat memberikan gambaran akurat mengenai kemampuan model dalam menggeneralisasi ke data baru.
- Standarisasi dilakukan agar fitur-fitur dalam dataset berada dalam skala yang seragam, karena banyak algoritma machine learning bekerja lebih optimal dan konvergen lebih cepat jika data berada dalam skala serupa atau mengikuti distribusi normal.

## Model Development

Pada kasus ini, kita menggunakan 4 model yaitu :

1. K-Nearest Neighbor
- **Proses Pembangunan Model**:

  1.   ```from sklearn.neighbors import KNeighborsRegressor```

       - Mengimpor class `KNeighborsRegressor` dari pustaka scikit-learn.

  2.   ```from sklearn.metrics import mean_squared_error```

       - Mengimpor class `mean_squared_error` dari pustaka scikit-learn, mean squared error (MSE) merupakan metrik evaluasi yang kita gunakan pada proyek ini

  3.   ```knn = KNeighborsRegressor(n_neighbors=10)```

       - Membuat objek dari class `KNeighborsRegressor` dengan parameter yang ditentukan.

          - **Penjelasan Parameter**:

            - `n_neighbors=10`: model akan mencari 10 tetangga terdekat dari titik data baru dan mengambil rata-rata dari target mereka untuk menghasilkan prediksi.

  4.   ```knn.fit(X_train, y_train)```

       - Memanggil metode fit untuk melatih model `KNeighborsRegressor` menggunakan data pelatihan `X_train` dan `y_train`.

       - `X_train`: Matriks fitur untuk melatih model.

       - `y_train`: Nilai target yang sesuai dengan data fitur dalam `X_train`.
         
- **Cara Kerja Model**:
  - K-Nearest Neighbors bekerja dengan mencari sejumlah tetangga terdekat dalam ruang fitur yang memiliki nilai target serupa. Setelah tetangga ditemukan, model akan menggunakan nilai rata-rata dari tetangga tersebut untuk membuat prediksi nilai target untuk data baru.

---

2. Random Forest
- **Proses Pembangunan Model**:

  1.   ```from sklearn.ensemble import RandomForestRegressor```

       - Mengimpor class `RandomForestRegressor` dari pustaka scikit-learn.

  2.   ```RF = RandomForestRegressor(n_estimators=50, max_depth=16, random_state=55, n_jobs=-1)```

       - Membuat objek dari class `RandomForestRegressor` dengan parameter yang ditentukan.

          - **Penjelasan Parameter**:

            - `n_estimators=50`: jumlah pohon yang dibangun sebanyak 50
            - `max_depth=16`: batas kedalam maksimum tiap pohon adalah 16 level, hal ini dilakukan untuk mencegah overfitting
            - `n_jobs=-1`: Menggunakan seluruh core CPU yang tersedia untuk mempercepat training

  3.   ```RF.fit(X_train, y_train)```

       - Memanggil metode fit untuk melatih model `RandomForestRegressor` menggunakan data pelatihan `X_train` dan `y_train`.

       - `X_train`: Matriks fitur untuk melatih model.

       - `y_train`: Nilai target yang sesuai dengan data fitur dalam `X_train`.
         
- **Cara Kerja Model**:
  - Random Forest bekerja dengan membuat banyak decision tree dari data yang diacak. Hasil prediksi dari semua pohon tersebut kemudian digabungkan — dengan cara voting (untuk klasifikasi) atau rata-rata (untuk regresi).

---

3. Ada Boost
- **Proses Pembangunan Model**:

  1.   ```from sklearn.ensemble import AdaBoostRegressor```

       - Mengimpor class `AdaBoostRegressor` dari pustaka scikit-learn.

  2.   ```boosting = AdaBoostRegressor(learning_rate=0.05, random_state=55)```

       - Membuat objek dari class `AdaBoostRegressor` dengan parameter yang ditentukan.

          - **Penjelasan Parameter**:

            - `learning_rate=0.05`: learning_rate=0.05 berarti, Mengontrol kontribusi masing-masing model lemah. Nilai yang kecil berarti model belajar lebih lambat tapi lebih stabil.
            - `random_state=55`: 55 “seed” digunakan untuk mengatur generator angka acak.

  3.   ```boosting.fit(X_train, y_train)```

       - Memanggil metode fit untuk melatih model `AdaBoostRegressor` menggunakan data pelatihan `X_train` dan `y_train`.

       - `X_train`: Matriks fitur untuk melatih model.

       - `y_train`: Nilai target yang sesuai dengan data fitur dalam `X_train`.
         
- **Cara Kerja Model**:
  - AdaBoost (Adaptive Boosting) bekerja dengan menggabungkan beberapa model lemah secara berurutan. Setiap model fokus pada kesalahan dari model sebelumnya dengan memberi bobot lebih besar pada data yang salah diprediksi. Model akhir adalah gabungan dari semua model lemah dengan bobot sesuai akurasinya.

---

**Kelebihan dan Kekurangan Dari Setiap Model**
| **Model**             | **Kelebihan**                                                                                                                                     | **Kekurangan**                                                                                                                              |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| **K-Nearest Neighbor**| - Mudah diimplementasikan  <br> - Cocok untuk data kecil dan non-linear                                                                           | - Lambat saat prediksi pada data besar  <br> - Sensitif terhadap data noisy & skala fitur  <br> - Tidak efektif pada data berdimensi tinggi |
| **Random Forest**     | - Akurasi tinggi & tahan overfitting  <br> - Bisa handle data numerik & kategorikal  <br> - Memberikan informasi feature importance               | - Kompleks & sulit diinterpretasikan  <br> - Butuh memori & waktu lebih banyak  <br> - Kurang cocok untuk prediksi real-time                |
| **Adaptive Boosting** | - Tingkatkan akurasi model sederhana  <br> - Fokus pada data yang sulit diklasifikasi  <br> - Risiko overfitting rendah jika dituning dengan baik | - Sensitif terhadap outlier  <br> - Performa buruk jika base model terlalu kompleks  <br> - Membutuhkan tuning parameter yang tepat         |

**Ketiga Model tersebut Cocok Karena**.

- K-Nearest Neighbor (KNN) model non-parametrik yang sederhana dan efektif. Ia mengklasifikasikan atau melakukan regresi berdasarkan kedekatan ke tetangga terdekat, sehingga sangat intuitif. KNN juga cocok digunakan karena dataset yang kita gunakan ini terbilang memiliki dimensi yang cukup kecil, sehingga cocok dengan algoritma KNN yang sederhana

- Random Forest Regressor menggabungkan hasil dari banyak pohon keputusan untuk menghasilkan prediksi yang lebih akurat dan robust. Ia juga memiliki mekanisme built-in untuk menangani overfitting dan dapat menangani data yang hilang dengan baik.

- AdaBoostRegressor Cocok digunakan karena dataset ini bersih, dan boosting bisa memperbaiki kesalahan iteratif, meningkatkan akurasi secara progresif.

## Evaluation

Dalam analisis ini digunakan metrik Mean Squared Error (MSE) untuk mengevaluasi kinerja model. MSE mengukur seberapa jauh prediksi model menyimpang dari nilai sebenarnya, dengan cara menghitung selisih antara nilai prediksi dan nilai aktual, mengkuadratkannya, lalu mengambil rata-rata dari seluruh selisih kuadrat tersebut. Nilai MSE yang lebih kecil menunjukkan bahwa prediksi model lebih mendekati nilai sebenarnya.

**Formula Mean Squared Error :**

![Box Plot Illustration](https://github.com/Ganskuy/Submission_PredictiveAnalytics/blob/d0024cc99a92ec93a55c9d711b48c81b2790df1b/resources/mse.jpg)

**Cara Kerja MSE**
---

1. **Hitung Error**
   - Untuk setiap data, hitung selisih antara nilai aktual dan nilai prediksi:
     
     Errorᵢ = Yᵢ -  Ŷᵢ

2. **Kuadratkan Error**
   - Agar semua error bernilai positif dan memberi penalti lebih besar pada error yang besar:
     
     (Errorᵢ)²

3. **Hitung Rata-rata**
   - Jumlahkan semua error yang telah dikuadratkan dan bagi dengan jumlah data:
     
     MSE = (1/n) × ∑(i=1 to n) (Errorᵢ)²

---

**Evaluasi Model Machine Learning**

| Model     | Train MSE | Test MSE |
|-----------|-----------|----------|
| KNN       | 0.008466  | 0.011335 |
| RF        | 0.000731  | 0.004887 |
| Boosting  | 0.007777  | 0.009028 |

![Box Plot Illustration](https://github.com/Ganskuy/Submission_PredictiveAnalytics/blob/ce66893e8ce796a5047f9c512906c9c36ce2b903/resources/train-test.png)

| Index | y_true | prediksi_KNN  | prediksi_RF | prediksi_Boosting  |
|-------|--------|---------------|-------------|--------------------|
| 720   | 78.9   | 79.7          | 81.3        | 80.7               |

Dari tabel di atas, dapat dilihat bahwa setiap model menghasilkan prediksi yang bervariasi untuk setiap nilai aktual (y_true). Model K-Nearest Neighbor (KNN) menunjukan hasil yang paling mendekati nilai aktual, sementara Random Forest dan Ada Boost menunjukkan hasil yang kompetitif. Secara keseluruhan, performa model dapat bervariasi tergantung pada karakteristik data dan hubungan yang ada antara fitur dan target.

## Kesimpulan

Dari hasil analisis dan evaluasi yang dilakukan, dapat disimpulkan bahwa model yang dibangun berhasil menjawab dua rumusan masalah utama yang diajukan. Pertama, melalui analisis multivariat dan proses pelatihan model, dapat diidentifikasi bahwa sejumlah fitur seperti GDP, Schooling, BMI, dan Health Expenditure merupakan faktor yang paling signifikan memengaruhi angka harapan hidup (Life Expectancy). Fitur-fitur ini menunjukkan korelasi yang kuat dan relevan dalam menentukan seberapa tinggi tingkat kesehatan dan kesejahteraan populasi di suatu negara. Kedua, model regresi yang dikembangkan juga terbukti mampu memprediksi angka harapan hidup secara akurat berdasarkan fitur-fitur input. Dari evaluasi menggunakan metrik Mean Squared Error (MSE), diketahui bahwa Model Random Forest dan Boosting (AdaBoost) menunjukkan performa terbaik, dengan nilai MSE yang paling rendah baik pada data pelatihan maupun pengujian. Hal ini menandakan bahwa kedua model tersebut sangat efektif dalam menangkap hubungan kompleks antar variabel untuk memprediksi nilai target. Secara khusus, Random Forest unggul dalam menjaga keseimbangan antara akurasi dan generalisasi. prediksi pada indeks 720 menunjukkan bahwa seluruh model memberikan hasil yang cukup mendekati nilai aktual. Hal ini menunjukkan tingkat keandalan prediksi yang baik, terutama oleh KNN dan Boosting, meskipun RF menghasilkan nilai prediksi tertinggi.

## Referensi

Life Expectancy, Healthy Life Expectancy, and Burden of Disease in Older People in The Americas, 1990–2019: a Population-based Study [_( Link Jurnal )_](https://pmc.ncbi.nlm.nih.gov/articles/PMC8489742/)

# Link Repository GitHub

