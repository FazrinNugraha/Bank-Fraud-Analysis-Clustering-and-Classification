# End-to-End Bank Transaction Behavior Segmentation & Fraud Detection

## 📋 Deskripsi Proyek

Repositori ini merupakan **Submission Tugas Akhir (Capstone)** untuk **Basic Machine Learning Program (BMLP)**. Analisis ini menggunakan dataset *Bank Transaction for Fraud Detection* untuk membangun sistem Machine Learning yang komprehensif melalui **End-to-End Pipeline**.

Alih-alih langsung menebak anomali, proyek ini menggunakan **pendekatan dua tahap**:

1. **Unsupervised Learning (Segmentasi/Clustering)** — Memetakan profil perilaku transaksi nasabah untuk memahami pola wajar (*normal behavior*) versus pola dinamis.
2. **Supervised Learning (Klasifikasi)** — Membangun model prediktif berdasarkan profil yang sudah dikelompokkan untuk mendeteksi transaksi penipuan (*fraud detection*).

---

## ⚙️ Persyaratan Sistem

Pastikan lingkungan kerja Anda telah memasang perangkat lunak dan pustaka berikut sebelum menjalankan proyek:

- Python 3.x
- Jupyter Notebook atau Google Colab
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Yellowbrick (`KElbowVisualizer`)
- Scikit-Learn
- Joblib

---

## 🚀 Cara Penggunaan

Ikuti langkah-langkah berikut untuk menjalankan proyek secara menyeluruh:

1. Unduh atau lakukan *clone* repositori ini ke komputer lokal Anda.
2. Buka dan jalankan file `1_Unsupervised_Customer_Segmentation.ipynb` secara berurutan (*Run All*) untuk memahami proses terbentuknya profil nasabah. Pastikan dataset mentah tersedia di direktori yang sama.
3. Setelah file `data_clustering_inverse.csv` berhasil diekspor dari notebook pertama, buka file `2_Supervised_Fraud_Classification.ipynb`.
4. Jalankan sel kode secara berurutan untuk melihat perbandingan performa antara model Decision Tree dan model Random Forest yang telah di-tuning.

---

## 🔄 Alur Kerja Proyek (Project Pipeline)

### Fase 1 — Unsupervised Learning (Customer Segmentation)

Pada fase ini, data mentah diproses untuk menemukan klaster pelanggan berdasarkan perilaku transaksinya.

- **Eksplorasi & Pembersihan Data (EDA)**: Menangani *missing values*, menghapus data duplikat, dan men-*drop* kolom identitas yang tidak relevan (seperti ID, IP Address, Date).
- **Pemrosesan Data (Preprocessing)**: Menerapkan Label Encoding untuk fitur kategorikal, menangani *outliers* (pencilan), melakukan Standard Scaling untuk fitur numerik, serta melakukan *binning* (pengelompokan rentang nilai).
- **Pemodelan K-Means & PCA**: Menggunakan *Elbow Method* untuk menentukan jumlah klaster optimal (K), melatih model K-Means, serta menerapkan PCA (*Principal Component Analysis*) untuk reduksi dimensi.
- **Evaluasi & Interpretasi**: Mengevaluasi klaster menggunakan *Silhouette Score*, dan melakukan *Inverse Transform* untuk mengembalikan data ke rentang nilai aslinya agar menghasilkan wawasan bisnis yang mudah dipahami.

> **Luaran Fase 1:** `clustering.h5`, `PCA_model_clustering.h5`, dan `data_clustering_inverse.csv`

---

### Fase 2 — Supervised Learning (Fraud Classification)

Pada fase ini, dataset berlabel hasil Fase 1 digunakan untuk melatih model pendeteksi fraud.

- **Persiapan Data**: Menggunakan `data_clustering_inverse.csv`, kemudian menerapkan *One-Hot Encoding* (`pd.get_dummies`) pada fitur kategorikal agar dapat dibaca oleh algoritma klasifikasi.
- **Data Splitting**: Membagi dataset menjadi Data Latih (80%) dan Data Uji (20%) dengan parameter `stratify` untuk memastikan proporsi kelas target seimbang.
- **Pemodelan Dasar**: Melatih model klasifikasi menggunakan algoritma **Decision Tree Classifier**.
- **Pemodelan Lanjutan**: Membangun model pembanding yang lebih tangguh menggunakan **Random Forest Classifier**.
- **Hyperparameter Tuning**: Mengoptimalkan model Random Forest menggunakan **GridSearchCV** untuk mencari kombinasi parameter terbaik.
- **Evaluasi Model**: Mengukur performa seluruh model menggunakan *Classification Report* (Accuracy, Precision, Recall, dan F1-Score).

> **Luaran Fase 2:** `decision_tree_model.h5` dan model Random Forest yang telah di-tuning.

---

## 📁 Struktur Repositori
