# 📈 Praktikum Analisis Regresi

Repositori ini merupakan catatan praktikum dalam memahami dan mengimplementasikan **Analisis Regresi**. Fokus utama saya adalah memahami hubungan antar variabel, membangun model prediktif, dan melakukan evaluasi model menggunakan dataset dunia nyata.

---

## 📚 Topik yang Dipelajari

### 1. Regresi Linear Sederhana
Mempelajari hubungan antara satu variabel independen ($x$) dan satu variabel dependen ($y$) dengan persamaan:
$$y = \beta_0 + \beta_1x + \epsilon$$

### 2. Regresi Linear Berganda
Menggunakan lebih dari satu prediktor untuk memprediksi hasil. Fokus pada penanganan **Multikolinearitas** menggunakan VIF (*Variance Inflation Factor*).

### 3. Asumsi Klasik
Memastikan model valid dengan uji:
* **Linearitas**: Hubungan linear antara variabel.
* **Homoskedastisitas**: Varians error yang konstan.
* **Normalitas**: Residual berdistribusi normal.
* **No Autokorelasi**: Terutama untuk data *time-series*.

### 4. Metrik Evaluasi
Untuk mengukur performa model, saya menggunakan:
* **R-Squared ($R^2$)**: Sejauh mana varians data dijelaskan oleh model.
* **MAE / MSE / RMSE**: Mengukur besarnya kesalahan prediksi.
