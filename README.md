# Prediksi Pertandingan Liga Inggris

Proyek ini bertujuan untuk membangun model machnine learning yang memprediksi pertandingan liga inggris untuk musim berikutnya berdasarkan fitur-fitur yang ditetapkan.

## Sumber Dataset
Kagle : [Premier League Match Result](https://www.kaggle.com/datasets/pourea/premier-league-match-results)

## Tahapan Proyek
- Load Dataset,kemudian melakukan Eksp;orasi dan analisis dataset.
- Pemrosesan data dengan mengambil fitur dan labelnya.
- Splitting data
- Membangun model machine learning, dengan membandingkan 3 algoritma yaitu Random Forest,Naive Bayes, dan SVM.

## Dataset
- Dataset : 'Dataset_2023.2024.xlsx'
- Jumlah Data : 760 baris dan 28 kolom.

### Fitur:
| Kolom       | Tipe Data | Deskripsi                                           |
|-------------|-----------|-----------------------------------------------------|
| Team        | String    | Nama tim sepak bola                                 |
| Status      | String    | Status tim (Home atau Guest)                        |
| Team rating | Float     | Rating keseluruhan tim                              |
| CB          | Integer   | Jumlah pemain Center Back                           |
| LB          | Integer   | Jumlah pemain Left Back                             |
| RB          | Integer   | Jumlah pemain Right Back                            |
| ST          | Integer   | Jumlah pemain Striker                               |
| CM          | Integer   | Jumlah pemain Center Midfielder                     |
| AM          | Integer   | Jumlah pemain Attacking Midfielder                  |
| LM          | Integer   | Jumlah pemain Left Midfielder                       |
| DM          | Integer   | Jumlah pemain Defensive Midfielder                  |
| RM          | Integer   | Jumlah pemain Right Midfielder                      |
| LW          | Integer   | Jumlah pemain Left Winger                           |
| RW          | Integer   | Jumlah pemain Right Winger                          |
| CBr         | Integer   | Jumlah pemain CB dari formasi lawan                 |
| LBr         | Integer   | Jumlah pemain LB dari formasi lawan                 |
| RBr         | Integer   | Jumlah pemain RB dari formasi lawan                 |
| STr         | Integer   | Jumlah pemain ST dari formasi lawan                 |
| CMr         | Integer   | Jumlah pemain CM dari formasi lawan                 |
| AMr         | Integer   | Jumlah pemain AM dari formasi lawan                 |
| LMr         | Integer   | Jumlah pemain LM dari formasi lawan                 |
| DMr         | Integer   | Jumlah pemain DM dari formasi lawan                 |
| LWr         | Integer   | Jumlah pemain LW dari formasi lawan                 |
| RWr         | Integer   | Jumlah pemain RW dari formasi lawan                 |
| RMr         | Integer   | Jumlah pemain RM dari formasi lawan                 |
| Round       | Integer   | Putaran atau minggu ke berapa pertandingan berlangsung |

### Label 
| Kolom       | Tipe Data | Deskripsi                                           |
|-------------|-----------|-----------------------------------------------------|
| Result      | String    | Hasil pertandingan (Win, Lost, Draw)                |

## Library yang Digunakan
- `pandas`, `numpy`
- `matplotlib`, `seaborn`
- `scikit-learn` (model, preprocessing, evaluasi)

## Hasil Model
- Perbandingan Model
  - **Random Forest** 
    - Akurasi : 84 %
  - **Naive Bayes**
    - Akurasi : 80 %
  - **Support Vector Machine(SVM)**
    - Akurasi : 70 %

- Algoritma Random Forest mampu memprediksi dengan baik dengan skor akurasi lebih tinggi dari Naive Bayes dan SVM.