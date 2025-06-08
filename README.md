# KitaFit: Model Prediksi Penyakit Jantung

Proyek *capstone* ini bertujuan untuk membangun model *machine learning* yang mampu membantu pengguna mengenali risiko penyakit jantung secara mandiri dan akurat. Model ini merupakan komponen inti dari platform digital berbasis website bernama **KitaFit**.

---

### Fitur Utama Proyek

-   **HeartTrack:** Algoritma *machine learning* yang dibangun menggunakan TensorFlow/Keras untuk memprediksi kondisi jantung berdasarkan data klinis seperti usia, tekanan darah, kolesterol, dan riwayat kesehatan.

---

### Dataset

Proyek ini menggunakan dataset **Heart Disease UCI** yang populer dan bersumber dari [Kaggle](https://www.kaggle.com/datasets/redwankarimsony/heart-disease-data). Dataset ini merupakan kompilasi data dari beberapa institusi medis dan berisi 14 atribut utama yang digunakan untuk prediksi, di antaranya:
1.  **age**: Usia (tahun)
2.  **sex**: Jenis kelamin
3.  **cp**: Tipe nyeri dada (*chest pain type*)
4.  **trestbps**: Tekanan darah saat istirahat
5.  **chol**: Kadar kolesterol serum
6.  **fbs**: Gula darah puasa > 120 mg/dl
7.  **restecg**: Hasil elektrokardiografi saat istirahat
8.  **thalach**: Detak jantung maksimum yang dicapai
9.  **exang**: Angina yang dipicu oleh olahraga
10. **oldpeak**: Depresi ST yang diinduksi oleh olahraga
11. **slope**: Kemiringan segmen ST saat puncak olahraga
12. **ca**: Jumlah pembuluh darah mayor yang terwarnai oleh fluoroskopi
13. **thal**: Status thalassemia
14. **num**: Variabel target (diagnosis penyakit jantung)

---

### Struktur Proyek

Berikut adalah struktur direktori dari proyek ini:


KitaFit/
├── Dataset/
│   └── heart_disease_uci.csv
├── Notebook/
│   └── fix_model.ipynb
├── heart_disease_prediction_model.h5
├── heart_disease_preprocessor.joblib
└── requirements.txt

-   **Dataset/**: Berisi file dataset mentah.
-   **Notebook/**: Berisi file Jupyter Notebook untuk analisis dan pelatihan model.
-   **Artefak Model**: File `.h5` (model terlatih) dan `.joblib` (preprocessor terlatih) adalah hasil akhir dari notebook.
-   **requirements.txt**: Daftar pustaka Python yang dibutuhkan.

---

### Teknologi yang Digunakan

-   **Bahasa**: Python 3.10
-   **Pustaka Utama**:
    -   **Analisis Data**: Pandas, NumPy
    -   **Visualisasi Data**: Matplotlib, Seaborn
    -   **Machine Learning**: Scikit-learn, TensorFlow (Keras)
-   **Lingkungan**: Jupyter Notebook (dijalankan melalui VS Code atau Google Colab)

---

### Instalasi dan Setup Lingkungan

Untuk menjalankan notebook ini di lingkungan lokal, disarankan untuk membuat *environment* terpisah menggunakan Conda untuk menghindari konflik dependensi.

1.  **Clone Repositori (jika ada)**
    ```bash
    git clone [https://www.andarepository.com/](https://www.andarepository.com/)
    cd [nama folder proyek]
    ```

2.  **Buat Environment Conda Baru**
    ```bash
    conda create --name kitafit_env python=3.10
    ```

3.  **Aktifkan Environment**
    ```bash
    conda activate kitafit_env
    ```

4.  **Install Semua Pustaka yang Dibutuhkan**
    Pastikan file `requirements.txt` ada di direktori Anda, lalu jalankan:
    ```bash
    pip install -r requirements.txt
    ```

5.  **Atasi Konflik Dependensi (jika terjadi)**
    Jika Anda mengalami error terkait `typing-extensions` saat instalasi, jalankan perintah ini untuk memaksa instalasi versi yang kompatibel:
    ```bash
    pip install typing-extensions==4.5.0 --force-reinstall
    ```

---

### Cara Menjalankan Notebook

1.  Pastikan environment `kitafit_env` sudah aktif.
2.  Buka proyek ini di VS Code atau jalankan Jupyter Notebook dari terminal.
3.  Buka file `Notebook/fix_model.ipynb`.
4.  Di VS Code, pastikan Anda memilih kernel yang benar (pojok kanan atas) yaitu `kitafit_env`.
5.  Jalankan sel-sel notebook secara berurutan untuk melihat keseluruhan proses, mulai dari Analisis Data Eksploratif (EDA), pra-pemrosesan, pelatihan model, hingga evaluasi performa.

---

### Hasil Model

Model Jaringan Saraf Tiruan (ANN) yang telah dilatih dievaluasi menggunakan data uji (*test set*) yang belum pernah dilihat sebelumnya. Hasil evaluasi utama adalah sebagai berikut:

-   **Akurasi Keseluruhan**: **~84%**
-   **Performa pada Kelas "Sakit Jantung" (Kelas 1)**:
    -   **Precision**: 0.82 (Dari semua yang diprediksi sakit, 82% benar-benar sakit).
    -   **Recall**: 0.91 (Dari semua pasien yang sebenarnya sakit, model berhasil mengidentifikasi 91% di antaranya).

Hasil ini menunjukkan bahwa model memiliki kemampuan yang baik dalam "menemukan" pasien yang berisiko, yang ditandai dengan nilai *Recall* yang tinggi.

---

*Dokumentasi ini dibuat untuk proyek Capstone KitaFit.*
