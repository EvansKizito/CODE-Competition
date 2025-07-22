# Proyek Prediksi Mobilitas Perkotaan - Smart Society Starter

Proyek ini bertujuan untuk mengembangkan model *machine learning* guna memprediksi jumlah perjalanan harian (`trips_thousands`) di berbagai zona pada sebuah kota fiktif. Proyek ini merupakan submisi untuk kompetisi Kaggle "Smart Society Starter - Tahap Penyisihan".

---

## 📖 Gambaran Umum

Tantangan utama dari proyek ini adalah menganalisis dan menggabungkan berbagai sumber data—mencakup demografi, aktivitas perkotaan, cuaca, dan infrastruktur—untuk membangun model prediksi yang akurat. Solusi ini diharapkan dapat mendukung perencanaan kota cerdas yang lebih efisien.

---

## 📊 Dataset

Dataset yang digunakan berasal dari halaman kompetisi di Kaggle. Data terdiri dari beberapa file CSV yang dapat dikelompokkan sebagai berikut:

* **File Utama:**
    * `mobility_train.csv`: Data latih berisi target prediksi.
    * `mobility_test.csv`: Data uji yang harus diprediksi.
    * `sample_submission.csv`: Contoh format file submisi.

* **Data Pendukung (Fitur):**
    * **Demografi:** `resident_data.csv`, `workforce_data.csv`, `education_data.csv`
    * **Aktivitas Urban:** `business_activity.csv`, `event_data.csv`, `tourism_data.csv`, `traffic_data.csv`
    * **Cuaca:** `weather_conditions.csv`, `air_quality.csv`
    * **Infrastruktur Transportasi:** `transit_stations.csv`, `bike_sharing.csv`, `road_network.csv`, `parking_data.csv`

---

## ⚙️ Metodologi

Alur kerja proyek ini dibagi menjadi beberapa tahapan utama:

1.  **Eksplorasi dan Pra-pemrosesan Data:**
    * Menggabungkan semua file data menjadi satu dataset latih dan uji yang komprehensif menggunakan `zone_id` dan `date` sebagai kunci.
    * Menangani nilai yang hilang (*missing values*) dengan metode imputasi yang relevan, seperti imputasi berbasis median atau interpolasi per zona untuk menjaga karakteristik data time series.

2.  **Rekayasa Fitur (Feature Engineering):**
    * Membuat fitur-fitur baru dari kolom tanggal (misalnya, hari dalam seminggu, akhir pekan, bulan).
    * Menciptakan fitur berbasis waktu seperti **Lag Features** (nilai dari hari-hari sebelumnya) dan **Rolling Features** (rata-rata dan standar deviasi bergerak) untuk menangkap tren dan volatilitas.

3.  **Pemodelan:**
    * Membagi data menjadi set latih dan validasi untuk mengukur performa model secara lokal.
    * Melatih beberapa model regresi, seperti Regresi Linier (sebagai baseline) dan model yang lebih canggih seperti LightGBM atau XGBoost.

4.  **Evaluasi:**
    * Performa model dievaluasi menggunakan metrik **Root Mean Squared Error (RMSE)**, sesuai dengan kriteria kompetisi.

---

## 🏆 Hasil

Model yang dikembangkan berhasil mencapai skor RMSE sebesar **[masukkan skor Anda di sini]** pada *leaderboard* privat Kaggle.

---

## 🚀 Cara Menjalankan

1.  **Kloning Repositori:**
    ```bash
    git clone [URL-repositori-Anda]
    cd [nama-folder-repositori]
    ```

2.  **Instalasi Dependensi:**
    Pastikan Anda memiliki Python dan instal library yang dibutuhkan.
    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn lightgbm
    ```

3.  **Jalankan Notebook:**
    Buka dan jalankan file `CODE.ipynb` (atau ganti dengan nama file notebook Anda) menggunakan Jupyter Notebook atau Google Colab.
