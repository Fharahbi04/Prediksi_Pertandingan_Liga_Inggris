# Laporan Proyek Machine Learning - Muhammad Fharahbi Fachri

## Domain Proyek
 Prediksi pertandingan liga inggris dengan membandingkan algoritma RandomForest,NaiveBayes,dan SVM

 Sepak bola adalah suatu cabang olahraga terbesar di dunia, Bahkan, ada yang berpendapat bahwa tidak diperlukan metode ilmiah untuk mengetahui betapa populernya sepak bola[1]. dalam dunia sepak bola yang sehat,terdapat pembinaan,tim nasional yang baik,dan kompetisi yang bagus didalamnya. Saat ini liga Inggris adalah liga terbaik di dunia, dengan ketatnya persaingan kompetisi dan jarak point antar tim yang memiliki selih yang berdekatan.

 Oleh karena itu, dengan ketatnya persaingan dan perebutan gelar juara liga terbaik didunia ini, membuat manajeman tim pasti memerlukan sebuah metode untuk memprediksi dan mengklasifikasi sebuah pertandingan yang telah mereka selesaikan sebelumnya untuk mengambil keputusan dan memprediksi pada pertandingan selanjutnya untuk meraih kemenangan[2].

 Beberapa penelitian sebelumnya telah dilakukan oleh[3] pada liga italia dengan membandingkan algoritma Random Forest,SVM, dan KNN,hasil yang didapatkan adalah nilai akurasi tertinggi senilai  64% pada algoritma SVM. Pada studi kasus kali ini akan menggunakan dataset dari liga Inggris dan membandingkan 3 algoritma yaitu Random Forest,Naive Bayes,dan SVM.

 ## Referensi
[1] METODE RANDOM FOREST DAN SUPPORT VECTOR MACHINE (Studi Kasus: Data Pertandingan Liga 1 Indonesia Musim 2018),” pp. 1–65, 2020, [Online]. Available: https://dspace.uii.ac.id/handle/123456789/29230%0Ahttps://dspace.uii.ac.id/bitstream/handle/123456789/29230/15611044_Alfari Afdhal_Skripsi.pdf?sequence=1&isAllowed=y

[2] E. Triawan, N. Suarna, and A. Rinaldi Dikananda, “Klasifikasi Tipe Penyerang Sepak Bola Liga Inggris Berdasarkan Data Statistik Pemain Menggunakan Metode Naive Bayes,” JATI (Jurnal Mhs. Tek. Inform., vol. 8, no. 2, pp. 1809–1814, 2024, doi: 10.36040/jati.v8i2.8404.)

[3] A. A. Karim, M. A. Prasetyo, and M. R. Saputro, “Perbandingan Metode Random Forest, K-Nearest Neighbor, dan SVM Dalam Prediksi Akurasi Pertandingan Liga Italia,” Pros. Semin. Nas. Teknol. dan Sains , vol. 2, pp. 377–342, 2023, [Online]. Available: http://www.football-data.co.uk.

## Business Understanding

### Problem Statements:

- Bagaimana cara memprediksi dengan memanfaatkan data liga inggris dengan memanfaaatkan semua fitur(kolom)?

- Algoritma klasifikasi mana yang paling optimal dalam memprediksi hasil pertandingan di antara Random Forest, Naive Bayes, dan Support Vector Machine (SVM)?

### Goals:

- Membuat sistem klasifikasiuntuk memprediksi pertandingan musim berikutnya dengan dataset yang tersedia.

- Mendapatkan satu algoritma yang mampu memberikan akurasi terbaik dengan minimal nilai > 80%.

### Solution Statements

- Membangun model klasifikasi menggunakan 3 algoritma berbeda,dan membandingkannya.

- Menggunakan metrik evaluasi seperti akurasi, precision, recall, dan F1-score untuk mengukur performa model.

## Data Understanding

### Sumber dan Informasi Dataset:

- **Sumber dan Informasi Dataset:** Berikut adalah tautan dataset yang digunakan pada proyek ini [Preamier League Match Result](https://www.kaggle.com/datasets/pourea/premier-league-match-results)

-**Jumlah Data:**  Memiliki 760 Baris dan 28 Kolom. Dimana terdapat 22 data bersifat intejer,3 float, dan 3 object
-**Kondisi Data:**Tidak terdapat data yang kosong,tidak memiliki ooutlier,tidak memiliki data duplikat.

### Fitur-fitur pada Dataset

- **Team**: Nama tim sepak bola yang sedang dianalisis.

- **Status**: Menunjukkan apakah tim tersebut bermain sebagai tuan rumah (Home) atau tim tamu (Guest).

- **Team rating**: Nilai rating keseluruhan tim yang mencerminkan kekuatan tim secara umum.

- **CB**: Jumlah pemain yang bermain di posisi Center Back pada tim.

- **LB**: Jumlah pemain di posisi Left Back.

- **RB**: Jumlah pemain di posisi Right Back.

- **ST**: Jumlah pemain di posisi Striker.

- **CM**: Jumlah pemain di posisi Center Midfielder.

- **AM**: Jumlah pemain di posisi Attacking Midfielder.

- **LM**: Jumlah pemain di posisi Left Midfielder.

- **DM**: Jumlah pemain di posisi Defensive Midfielder.

- **RM**: Jumlah pemain di posisi Right Midfielder.

- **LW**: Jumlah pemain di posisi Left Winger.

- **RW**: Jumlah pemain di posisi Right Winger.

- **Rival Team Rating**: Nilai rating keseluruhan tim lawan yang mencerminkan kekuatan tim lawan secara umum.

- **CBr**: Jumlah pemain Center Back dari tim lawan.

- **LBr**: Jumlah pemain Left Back dari tim lawan.

- **RBr**: Jumlah pemain Right Back dari tim lawan.

- **STr**: Jumlah pemain Striker dari tim lawan.

- **CMr**: Jumlah pemain Center Midfielder dari tim lawan.

- **AMr**: Jumlah pemain Attacking Midfielder dari tim lawan.

- **LMr**: Jumlah pemain Left Midfielder dari tim lawan.

- **DMr**: Jumlah pemain Defensive Midfielder dari tim lawan.

- **LWr**: Jumlah pemain Left Winger dari tim lawan.

- **RWr**: Jumlah pemain Right Winger dari tim lawan.

- **RMr**: Jumlah pemain Right Midfielder dari tim lawan.

- **Round**: Menunjukkan minggu atau putaran ke berapa pertandingan tersebut berlangsung dalam satu musim kompetisi.

- **Result**: Target/Label, merupakan hasil pertandingan (win,lose,draw).

### Analisis Hasil Exploratory Data Analysis (EDA):

- Visualisasi distribusi kemenangan berdasarkan rating. Ditemukan rating tim memiliki pengaruh signifikan terhadap hasil pertandingan.

- Visualisasi distribusi berdasarkan status bertanding. Mendapatkan hasil Tim yang bermain sebagai tuan rumah (Home) memiliki kemungkinan menang lebih tinggi dibandingkan tim tamu (Guest).

## Data Preparation

**Langkah-langkah data preparation:**

1. **Encoding**:
   - Merubah kolom team dan status dari awalnya kategori menjadi numerik.


2. **Train-test split**:
   - Data dibagi 80% untuk training dan 20% untuk testing.

## Model Development
- Model yang digunakan adalah Random Forest,Naive Bayes, dan SVM.
  - Random Forest dalah algoritma ensemble yang membangun banyak pohon keputusan (decision tree) dan menggabungkan  hasilnya untuk meningkatkan akurasi dan mencegah overfitting. Cara Kerja:
    - Bootstrap Sampling: Dataset dilatih secara acak (sampling dengan pengembalian) untuk membuat beberapa subset data (bootstrap samples).
    - Pembangunan Pohon: Untuk setiap subset, dibangun satu pohon keputusan menggunakan sebagian fitur secara acak.
    - Voting (Klasifikasi) atau Rata-rata (Regresi):
    - Untuk klasifikasi: Setiap pohon memberikan suara (vote), dan kelas dengan suara terbanyak adalah hasil akhir.
    - Untuk regresi: Mengambil rata-rata dari hasil semua pohon.
  
  - Naive Bayes adalah algoritma klasifikasi berdasarkan Teorema Bayes dengan asumsi kuat (naive) bahwa fitur-fitur bersifat independen satu sama lain. Cara Kerja :
    - Menghitung Probabilitas Kelas: Misalnya menghitung P(Positif) dan P(Negatif) dari data latih.
    - Menghitung Probabilitas Kondisional: Misalnya P(Fitur | Kelas) untuk setiap fitur.
    - Menerapkan Teorema Bayes.
    - Prediksi: Memilih kelas dengan nilai probabilitas terbesar.

  - SVM(Support Vector Machine) adalah algoritma klasifikasi yang mencari garis pemisah (hyperplane) terbaik yang memisahkan kelas data dengan margin terbesar. Cara Kerja:
    - SVM mencari hyperplane (garis di 2D, bidang di 3D, dst.) yang memaksimalkan margin antara dua kelas.
    - Support Vectors: Titik data paling dekat dengan hyperplane yang menentukan posisinya.
    - Untuk data yang tidak linear, SVM menggunakan kernel trick (misalnya RBF, polynomial) untuk memetakan data ke dimensi lebih tinggi agar bisa dipisahkan secara linear.

## **Tahapan KerjaPemodelan**

### 1. **Data Preparation**
### 2. **Pembagian Data**
### 3. **Pembentukan Random Forest,Naive Bayes,SVM**
### 4. **Prediksi**
### 5. **Evaluasi Model**
### 6. **Cek Akurasi > 80% atau tidak**

![alt text](<prediksiepl.png>)


- Random Forest dipilih karena tahan terhadap overfitting, bisa menangani banyak fitur tanpa perlu feature selection, memberikan feature importance. Parameter yang digunakan:
```python
 RandomForestClassifier(
    n_estimators=100,         # Jumlah pohon dalam hutan (semakin banyak → hasil lebih stabil)
    max_depth=None,           # Tidak ada batasan kedalaman pohon (berpotensi overfitting)
    min_samples_split=2,      # Minimum sampel untuk membagi node (default: 2)
    min_samples_leaf=1,       # Minimum sampel di setiap daun pohon (default: 1 → pohon sangat fleksibel)
    random_state=42           # Seed untuk hasil yang konsisten setiap kali dijalankan
)
```

- Naive Bayes dipilih karena model sederhana dan cepat, efektif pada data kategori dan numerik,serta tahan terhadap noise dan data imbalance. Tidak membutuhhkan banyak parameter eksplisit.

- SVM dipilih karena mampu menangani data non-linear, pengendalian margin klasifikas, performa tinggi dalam banyak studi. Parameter yang digunakan:
```python
SVC(
    kernel='rbf',         # Jenis kernel yang digunakan; 'rbf' cocok untuk data non-linear
    C=1.0,                # Parameter regularisasi; semakin tinggi → penalti kesalahan makin besar
    gamma='scale',        # Koefisien kernel; 'scale' menghitung otomatis berdasarkan fitur
    probability=True,     # Mengaktifkan prediksi probabilitas (dibutuhkan untuk evaluasi seperti ROC AUC)
    random_state=42       # Seed untuk hasil yang konsisten pada percobaan berulang
)
```
Alasan Pemilihan Parameter 
- **Random Forest**:
  - n_estimators=100,100 merupakan nilai umum yang memberikan trade-off bagus antara akurasi dan waktu komputasi
  - max_depth=None,tidak membatasi kedalaman pohon membuat model bisa mempelajari semua pola dalam data dengan maksimal.Cocok digunakan untuk eksplorasi awal sebelum melakukan pruning atau tuning.
  - min_samples_split=2,memberikan model fleksibilitas tinggi dalam membentuk struktur pohon.
  - min_samples_leaf=1,Memberikan keleluasaan pada pohon untuk menyimpan keputusan hingga satu sampel di tiap daun. 
  - random_state=42,Agar hasil eksperimen bersifat reproducible — artinya hasilnya bisa diulang dan diuji kembali secara konsisten.

- **SVM**:
  - kernel='rbf',eksibel untuk menangani berbagai pola.
  - C=1.0 menjaga keseimbangan antara overfitting dan underfitting.
  - gamma='scale' memastikan nilai gamma disesuaikan dengan dataset.
  - probability=True memungkinkan evaluasi model dengan metrik probabilistik seperti AUC.

Algoritma Terbaik yang didapatkan adalah Random Forest dengan nilai akurasi 84%, alasan model ini sangat baik karena mampu menangani data berdimensi tinggi.

## Evaluation

### **Metrik Evaluasi:**
* **Accuracy (Akurasi) Random Forest**: 84%
  Model mampu memprediksi dengan benar lebih dari 84% data pada set pengujian.
* **Accuracy (Akurasi) Naive Bayes**: 80%
  Model mampu memprediksi dengan benar lebih dari 80% data pada set pengujian.
* **Accuracy (Akurasi) SVM**: 70%
  Model mampu memprediksi dengan benar lebih dari 70% data pada set pengujian.

* **Classification Report Random Forest**:

| Class (Label)    | Precision | Recall | F1-Score | Support |
| ---------------- | --------- | ------ | -------- | ------- |
| Draw | 0.57     | 0.48   | 0.52     | 27  |
| Lost     | 0.90    | 0.93  | 0.92     | 60  |
| Win     | 0.88    | 0.91   | 0.89     | 65  |

* **Classification Report Naive Bayes**:

| Class (Label)    | Precision | Recall | F1-Score | Support |
| ---------------- | --------- | ------ | -------- | ------- |
| Draw | 0.44      | 0.41   | 0.42     | 27  |
| Lost     | 0.87     | 0.90  | 0.89     | 60  |
| Win     | 0.86     | 0.86   | 0.86     | 65  |

* **Classification Report SVM**:

| Class (Label)    | Precision | Recall | F1-Score | Support |
| ---------------- | --------- | ------ | -------- | ------- |
| Draw | 0.00      | 0.00   | 0.00     | 27  |
| Lost     | 0.71     | 0.83  | 0.79     | 60  |
| Win     | 0.70     | 0.88   | 0.76     | 65  |

* **Macro Average Random Forest**:

  * Precision: 0.78
  * Recall: 0.77
  * F1-Score: 0.78

* **Weighted Average Random Forest**:

  * Precision: 0.83
  * Recall: 0.84
  * F1-Score: 0.84

* **Macro Average Naive Bayes**:

  * Precision: 0.72
  * Recall: 0.72
  * F1-Score: 0.72

* **Weighted Average Naive Bayes**:

  * Precision: 0.79
  * Recall: 0.80
  * F1-Score: 0.79

* **Macro Average SVM**:

  * Precision: 0.47
  * Recall: 0.57
  * F1-Score: 0.52

* **Weighted Average SVM**:

  * Precision: 0.58
  * Recall: 0.70
  * F1-Score: 0.64
#### **Interpretasi Hasil**

* Algoritma Random Forest lebih baik dengan hasil prediksi diangka 84%,sedangkan Naive Bayes 80%, dan SVM 70%.
* Alasan Algortima Random Forest lebih baik karena :
   - Tahan terhadap overfitting.
   - Bisa menangani banyak fitur tanpa perlu feature  selection.
   - Memberikan feature importance.
* Meskipun hasil Random Forest lebih bagus, algoritma ini belum maksimal untuk melihat hasil draw, karena hasil dari matriks evaluasi melihatkan hasil 57%. Tetapi hal tersebut juga bisa dikarenakan nilai draw lebih sedikit dibangdingkan win dan lost.

#### **Evaluasi terhadap Business Understanding**
- **Bagaimana cara memprediksi dengan memanfaatkan data liga inggris dengan memanfaaatkan semua fitur(kolom)?** 
  Model dapat memprediksi semua fitur dari tabel yang diberikan dengan cukup baik.
- **Algoritma klasifikasi mana yang paling optimal dalam memprediksi hasil pertandingan di antara Random Forest, Naive Bayes, dan Support Vector Machine (SVM)?**
  Algoritma yang memiliki model terbaik adalah Random Forest dengan mendapatkan nilai akurasi 84%.

#### **Rekomendasi Perbaikan**

* Menyesuaikan threshold prediksi untuk meningkatkan recall pada kelas Result.
* Menerapkan teknik penyeimbangan data seperti **SMOTE** atau **undersampling** untuk mengatasi imbalance.