# Hospital Readmissions Predict Project
## Domain Proyek
### Latar Belakang
Sebuah perusahaan konsultan membantu grup rumah sakit dalam memahami lebih dalam mengenai pasien yang mengalami readmisi, yaitu pasien yang harus dirawat kembali di rumah sakit setelah sebelumnya dipulangkan. Dalam kerangka ini, rumah sakit memberikan data historis selama sepuluh tahun terakhir mengenai pasien-pasien yang mengalami readmisi. Dokter dan staf medis ingin mengeksplorasi apakah terdapat pola atau faktor tertentu, seperti diagnosis awal atau jumlah prosedur medis, yang dapat membantu mereka dalam memahami kemungkinan pasien untuk mengalami readmisi.

Tujuan utama dari analisis ini adalah untuk membantu rumah sakit dalam memfokuskan panggilan tindak lanjut dan perhatian pada pasien-pasien yang memiliki risiko tinggi untuk mengalami readmisi, sehingga memungkinkan penyedia layanan kesehatan untuk mengambil tindakan pencegahan yang sesuai dan meningkatkan kualitas perawatan pasien.

### Mengapa Masalahan Ini Harus Diselesaikan
Permasalahan mengenai readmisi pasien merupakan salah satu isu penting dalam industri kesehatan. Readmisi pasien tidak hanya memberikan beban tambahan bagi rumah sakit dan tenaga medis, tetapi juga menandakan adanya potensi masalah dalam perawatan pasien atau sistem kesehatan yang ada. Oleh karena itu, penyelesaian permasalahan ini menjadi krusial untuk meningkatkan efisiensi dan kualitas layanan kesehatan.

Untuk menyelesaikan permasalahan ini, langkah-langkah yang dapat diambil antara lain:
1. Analisis Data: Mengumpulkan dan menganalisis data historis mengenai pasien-pasien yang mengalami readmisi untuk mengidentifikasi pola-pola atau faktor-faktor yang berkaitan dengan kemungkinan readmisi.
2. Pengembangan Model Prediktif: Membangun model prediktif berdasarkan data historis untuk memprediksi kemungkinan pasien mengalami readmisi. Model ini dapat memanfaatkan berbagai teknik machine learning, seperti regresi logistik, decision tree, atau algoritma ensemble seperti random forest atau gradient boosting.
3. Validasi dan Evaluasi Model: Melakukan validasi model menggunakan data independen untuk memastikan keandalan dan ketepatan prediksi. Evaluasi dilakukan dengan menggunakan metrik evaluasi yang sesuai, seperti akurasi, presisi, recall, dan area di bawah kurva ROC (ROC-AUC).
4. Implementasi dan Tindak Lanjut: Mengimplementasikan model prediktif ke dalam sistem informasi rumah sakit untuk mendukung pengambilan keputusan. Selain itu, merancang strategi tindak lanjut yang efektif berdasarkan hasil prediksi untuk mengurangi risiko readmisi pasien, termasuk pengaturan panggilan tindak lanjut, perubahan rencana perawatan, atau penyuluhan kepada pasien.
Dengan pendekatan ini, diharapkan permasalahan mengenai readmisi pasien dapat diselesaikan dengan lebih efektif, sehingga rumah sakit dapat memberikan perawatan yang lebih baik dan meminimalkan beban serta biaya yang terkait dengan readmisi pasien.

## Business Understanding
Berdasarkan kondisi yang telah diuraikan sebelumnya, perusahaan memiliki tujuan untuk mengembangkan sebuah sistem prediksi pasien yang mengalami readmisi dalam rangka menjawab beberapa permasalahan kunci:

1. Identifikasi Fitur yang Signifikan: Perusahaan ingin mengetahui fitur-fitur mana yang paling berpengaruh terhadap kemungkinan seorang pasien mengalami readmisi. Dengan memahami fitur-fitur yang paling berkorelasi, rumah sakit dapat menyesuaikan strategi perawatan dan tindak lanjut pasca-pulang untuk mencegah atau mengurangi kemungkinan readmisi.
2. Analisis Pola dan Faktor: Perusahaan tertarik untuk menemukan pola atau faktor tertentu yang dapat mempengaruhi kemungkinan seorang pasien mengalami readmisi. Analisis ini dapat membantu dokter dan staf medis dalam memahami profil pasien yang lebih rentan terhadap readmisi, sehingga tindakan pencegahan yang sesuai dapat diambil dengan lebih efektif.
3. Pembangunan Model Prediktif: Perusahaan bermaksud untuk membuat model machine learning yang dapat memprediksi dengan seakurat mungkin apakah seorang pasien akan mengalami readmisi berdasarkan fitur-fitur yang ada. Dengan memiliki model prediktif yang handal, rumah sakit dapat mengidentifikasi pasien dengan risiko tinggi untuk mengalami readmisi dan mengambil tindakan yang diperlukan untuk meningkatkan kualitas perawatan dan mengurangi beban readmisi pasien.

Dengan demikian, tujuan utama dari proyek ini adalah untuk memberikan wawasan yang berharga kepada rumah sakit dalam hal pengelolaan pasien yang berpotensi mengalami readmisi, serta membantu mereka dalam mengoptimalkan strategi perawatan dan pengambilan keputusan klinis.


## Data Understanding
Data yang digunakan berasal dari dataset kompetisi di DataCamp, yang dapat diakses melalui tautan <a href='https://app.datacamp.com/learn/competitions/hospital-patient-readmissions'>Competitions - DataCamp</a>. Dataset ini terdiri dari 25.000 baris data dan 17 kolom dengan 16 kolom fitur yang digunakan untuk memprediksi variabel target, yaitu readmitted.

Berikut adalah informasi mengenai kolom fitur dalam dataset:
- `age` : kelompok usia pasien
- `time_in_hospital` : jumlah hari tinggal di rumah sakit (dari 1 hingga 14)
- `n_procedures` : jumlah prosedur yang dilakukan selama pasien dirawat di rumah sakit
- `n_lab_procedures` : jumlah prosedur laboratorium yang dilakukan selama masa rawat inap
- `n_medications` : jumlah obat yang diberikan selama rawat inap di rumah sakit
- `n_outpatient` : jumlah kunjungan rawat jalan pada tahun sebelum rawat inap di rumah sakit
- `n_inpatient` : jumlah kunjungan rawat inap pada tahun sebelum tinggal di rumah sakit
- `n_emergency` : jumlah kunjungan ke unit gawat darurat pada tahun sebelum rawat inap di rumah sakit
- `medical_specialty` : spesialisasi dokter yang merawat
- `diag_1` : diagnosis primer (Peredaran Darah, Pernapasan, Pencernaan, dll.)
- `diag_2` : diagnosis sekunder
- `diag_3` : diagnosis sekunder tambahan
- `glucose_test` : hasil tes serum glukosa (tinggi, normal, atau tidak dilakukan)
- `A1Ctest` : hasil tes A1C (tinggi, normal, atau tidak dilakukan)
- `change` : apakah ada perubahan dalam pengobatan diabetes ('ya' atau 'tidak')
- `diabetes_med` : apakah obat diabetes diresepkan ('ya' atau 'tidak')
- `readmitted` : apakah pasien dirawat inap di rumah sakit ('ya' atau 'tidak')

Referensi:
Strack, Beata, et al. "Impact of HbA1c Measurement on Hospital Readmission Rates: Analysis of 70,000 Clinical Database Patient Records." BioMed Research International, vol. 2014, Article ID 781670, 11 pages, 2014.
