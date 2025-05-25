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




