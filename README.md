Prediksi Laba UMKM dengan Regresi Linear
========================================

Deskripsi Proyek
----------------

Repositori ini berisi analisis data dan kode untuk memprediksi laba Usaha Mikro, Kecil, dan Menengah (UMKM) menggunakan algoritma Regresi Linear. Pemodelan prediksi dibangun berdasarkan berbagai faktor utama bisnis, dengan fokus pada aset, omset, dan biaya operasional (karyawan). Proyek ini bertujuan untuk memberikan wawasan terkait variabel-variabel yang paling memengaruhi tingkat keuntungan UMKM.

Persyaratan Sistem
------------------

Pastikan lingkungan kerja Anda telah memasang perangkat lunak dan pustaka berikut sebelum menjalankan proyek:

*   Python 3.x
    
*   Jupyter Notebook atau Google Colab
    
*   Pandas
    
*   NumPy
    
*   Matplotlib
    
*   Seaborn
    
*   Scikit-Learn
    

Cara Penggunaan
---------------

Ikuti langkah-langkah di bawah ini untuk menjalankan kode analisis:

*   Unduh atau lakukan _clone_ repositori ini ke komputer lokal Anda.
    
*   Buka fail notebook UMKM (1).ipynb menggunakan aplikasi Jupyter Notebook atau unggah fail tersebut ke Google Colab.
    
*   Pastikan dataset dataset\_umkm.csv sudah tersedia. Sesuaikan _path_ atau direktori fail dataset pada blok kode pembacaan data jika diperlukan.
    
*   Jalankan blok kode secara berurutan mulai dari impor pustaka, pemuatan data, prapemrosesan, hingga evaluasi model regresi.
    

Tahapan Analisis dan Pemodelan
------------------------------

Proyek ini mencakup beberapa proses utama untuk memastikan model dapat memprediksi laba secara optimal:

*   **Eksplorasi Data (EDA)**: Meninjau struktur dataset, jumlah fitur, tipe data, serta nilai statistik deskriptif dari data UMKM.
    
*   **Prapemrosesan Data**:
    
    *   Melakukan konversi tipe data pada kolom numerik yang terdeteksi sebagai teks.
        
    *   Mengatasi nilai yang hilang (_missing values_) dengan menggunakan nilai median untuk variabel numerik dan nilai modus untuk variabel kategorikal.
        
    *   Membuang kolom yang tidak memiliki relevansi terhadap model prediktif (contoh: ID UMKM dan Nama Usaha).
        
*   **Penanganan Pencilan (**_**Outlier**_**)**: Mendeteksi dan menghapus pencilan pada variabel laba menggunakan metode Rentang Interkuartil (IQR) agar tidak merusak performa model.
    
*   **Transformasi Data**: Menerapkan transformasi logaritmik (_log transformation_) pada variabel laba untuk menormalkan distribusi data.
    
*   **Pelatihan Model**: Melatih model Regresi Linear menggunakan variabel independen (seperti aset, omset, dan biaya karyawan) untuk memprediksi variabel dependen (laba), serta mengevaluasi akurasi prediksinya.