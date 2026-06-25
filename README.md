# 📈 Praktikum Analisis Regresi
 
Repositori ini berisi praktikum mata kuliah **Analisis Regresi**. Fokus utama pembelajaran adalah memahami hubungan antar variabel, membangun model prediktif, serta melakukan evaluasi model menggunakan dataset dunia nyata.
 
---
 
## 📚 Rangkuman Materi
 
### 1. Konsep Dasar Regresi
Regresi adalah metode statistik untuk mengukur dan memodelkan hubungan antara **variabel dependen (terikat)** dan satu atau lebih **variabel independen (bebas)**. Tujuannya adalah membuat model yang dapat digunakan untuk memprediksi nilai variabel dependen berdasarkan nilai variabel independen.
 
### 2. Regresi Linear Sederhana
Mempelajari hubungan antara satu variabel independen ($x$) dan satu variabel dependen ($y$) melalui persamaan:
 
$$y = \beta_0 + \beta_1x + \epsilon$$
 
di mana:
- $\beta_0$ = intercept (konstanta)
- $\beta_1$ = koefisien kemiringan (slope)
- $\epsilon$ = error/residual
### 3. Regresi Linear Berganda
Pengembangan dari regresi sederhana dengan menggunakan **lebih dari satu variabel prediktor** untuk memprediksi hasil:
 
$$y = \beta_0 + \beta_1x_1 + \beta_2x_2 + \dots + \beta_nx_n + \epsilon$$
 
Salah satu perhatian utama dalam regresi berganda adalah **Multikolinearitas**, yaitu kondisi di mana antar variabel independen saling berkorelasi tinggi. Hal ini dideteksi menggunakan **VIF (Variance Inflation Factor)** — semakin tinggi nilai VIF, semakin besar kemungkinan terjadi multikolinearitas.
 
### 4. Uji Asumsi Klasik
Sebuah model regresi dikatakan valid (BLUE — *Best Linear Unbiased Estimator*) jika memenuhi beberapa asumsi berikut:
 
| Asumsi | Penjelasan |
|---|---|
| **Linearitas** | Hubungan antara variabel independen dan dependen bersifat linear. |
| **Homoskedastisitas** | Varians dari residual/error bersifat konstan di semua nilai prediksi. |
| **Normalitas** | Residual model berdistribusi normal. |
| **No Autokorelasi** | Tidak ada korelasi antar residual, terutama penting pada data *time-series*. |
 
Jika asumsi-asumsi ini dilanggar, hasil estimasi model bisa menjadi bias atau tidak efisien, sehingga perlu dilakukan penanganan (misalnya transformasi data atau penggunaan model alternatif — lihat bagian [Penanganan Pelanggaran Asumsi](#6-penanganan-pelanggaran-asumsi)).
 
### 5. Metrik Evaluasi Model
Performa dan kualitas model regresi diukur menggunakan beberapa metrik berikut:
 
**Metrik kesalahan prediksi:**
- **R-Squared ($R^2$)** — mengukur sejauh mana variasi data dapat dijelaskan oleh model (semakin mendekati 1, semakin baik).
- **MAE (Mean Absolute Error)** — rata-rata nilai absolut dari kesalahan prediksi.
- **MSE (Mean Squared Error)** — rata-rata kuadrat dari kesalahan prediksi, memberi bobot lebih besar pada error yang besar.
- **RMSE (Root Mean Squared Error)** — akar dari MSE, memiliki satuan yang sama dengan variabel yang diprediksi sehingga lebih mudah diinterpretasi.
**Metrik pemilihan model (model selection):**
- **AIC (Akaike Information Criterion)** — mengukur kualitas model dengan menyeimbangkan *goodness of fit* dan kompleksitas model (jumlah parameter). Semakin kecil nilai AIC, semakin baik model tersebut relatif terhadap model lain.
- **BIC (Bayesian Information Criterion)** — mirip dengan AIC, namun memberikan penalti yang lebih besar terhadap jumlah parameter, sehingga cenderung memilih model yang lebih sederhana (*parsimonious*). Semakin kecil nilai BIC, semakin baik.
- **Cp Mallow** — digunakan untuk membandingkan model dengan jumlah prediktor yang berbeda, dengan menilai trade-off antara bias dan jumlah variabel yang digunakan. Model yang baik biasanya memiliki nilai Cp mendekati jumlah parameter ($p$) model tersebut.
### 6. Penanganan Pelanggaran Asumsi
Ketika hasil uji asumsi klasik menunjukkan adanya pelanggaran, beberapa metode berikut dapat digunakan untuk menanganinya:
 
- **WLS (Weighted Least Squares)** — digunakan untuk menangani **heteroskedastisitas**. Berbeda dari OLS yang memberi bobot sama pada setiap observasi, WLS memberi bobot lebih kecil pada observasi dengan varians error yang besar, sehingga estimasi menjadi lebih efisien.
- **Transformasi Box-Cox** — transformasi pangkat pada variabel dependen untuk mengatasi pelanggaran normalitas dan/atau heteroskedastisitas, dengan mencari nilai $\lambda$ (lambda) optimal yang membuat distribusi data mendekati normal.
- **Transformasi umum lainnya** — beberapa transformasi sederhana yang sering digunakan sebelum atau sebagai alternatif Box-Cox:
  - **Logaritma ($\ln(y)$ atau $\log_{10}(y)$)** — cocok untuk data dengan sebaran yang skewed (menjulur) atau bersifat eksponensial.
  - **Akar kuadrat ($\sqrt{y}$)** — sering digunakan untuk data *count* (cacahan).
  - **Inverse ($1/y$)** — digunakan saat varians error meningkat tajam terhadap nilai prediksi.
