### **Context Business**

Sebuah perusahaan besar multinasional sedang menghadapi tantangan dalam mengidentifikasi kandidat yang tepat untuk dipromosikan ke level manajerial ataupun yang dibawahnya yang telah memenuhi standar dengan tepat waktu. Jika terjadi keterlambatan dalam mengidentifikasi calon kandidat ini dapat menyebabkan ketidakefisienan operasional dan terjadi perpanjangan transisi ke peran baru setelah evaluasi dilakukan secara menyeluruh yang mana dalam hal ini dapat merugikan perusahaan.

Dalam konteks ini, perusahaan membutuhkan Data Scientist dalam menganalisa kualifikasi karyawan dan membuat model machine learning untuk memprediksi kandidat yang layak dipromosikan dengan kriteria tertentu sehingga mereka dapat mempercepat proses seluruh siklus promosi dan memitigasi risiko lamanya transisi jabatan.

Karyawan yang akan menjadi kandidat promosi memiliki latar belakang yang berbeda-beda. Perusahaan ingin mengetahui kandidat mana yang benar-benar cocok untuk dipilih berdasarkan data yang dimiliki HR. Proses analisis ini sangat diperlukan karena dapat menjadi dasar dalam menentukan kandidat yang tepat agar membantu mempercepat transisi jabatan.

Namun dalam proses penentuan kandidat yang dipromosikan dapat memakan waktu yang lama jika HR melakukan assesment kepada semua calon kandidat tanpa adanya penyaringan terlebih dahulu sehingga hal ini dapat mengakibatkan ketidakefisienan waktu dan beban kerja tersendiri bagi HR. Selain itu, dengan besarnya jumlah kandidat yang akan dipilih untuk dipromosikan dalam waktu yang singkat dapat mengakibatkan terjadinya ketidakefektifan proses penentuan kandidat karena terdapat kemungkinan terjadi ketidaktepatan dalam penentuan kandidat yang seharusnya.

Berdasarkan hasil studi dari Deloitte (kantor akuntan publik Big 4) ditemukan bahwa penggunaan AI (Artifiicial Intelegence) dapat mengurangi waktu hingga 50% dan mengurangi biaya hingga 70% pada proses penyeleksian karyawan.
https://www.searchlight.ai/blog/the-ultimate-ai-tool-for-resume-screening-streamlining-hiring-processes

Hasil dari McKinsey's Global AI Survey yang dilakukan pada responden HR juga menemukan bahwa perusahaan berhasil menurunkan biaya operasional sebesar 10% dan rata-rata pendapatan naik sebesar 6-10% karena HR telah menggunakan AI dalam melakukan pekerjaan mereka. https://www.retorio.com/blog/how-artificial-intelligence-used-human-resources

Berdasakan 2 literatur penelitian ini maka AI/ML dapat dimanfaatkan dalam proses promosi oleh HR dengan Target (is_promoted) :

0 : Not Recommended for promotion

1 : Recommended for promotion

### **Problem Statement**

Berdasarkan dari kedua permasalahan tersebut maka perusahaan/HR perlu mengatasi permasalahan ketidakefisienan dan ketidakefektifan yang dapat terjadi pada proses penentuan kandidat yang akan dipromosikan.
Penggunaan model Machine Learning akan memudahkan HR dalam mengambil keputusan dari bagaimana Machine Learning memprediksi karyawan yang tepat untuk dipromosikan agar proses promosi berkualitas, berjalan efektif dan lebih efisien terhadap waktu ataupun biayanya. Permasalahan yang muncul tersebut dapat dirangkum menjadi 2 problem statement sebagai berikut:

1.   Bagaimana prediksi calon kandidat yang tepat untuk dipromosikan agar proses promosi berjalan dengan efektif dan efisien?
2.   Apa yang harus ditingkatkan dari para karyawan agar dipromosikan sehingga dapat memenuhi kebutuhan kualitas maupun jumlahnya untuk mengisi prosisi jabatan yang dibutuhkan?  


### **Goals**

Berdasarkan permasalahan diatas, HR harus memiliki kemampuan dalam memprediksi kemungkinan seorang kandidat yang akan dipromosikan secara efektif dan efisien. Penggunaan Machine Learning (ML) dapat menjadi tools bagi HR dalam melakukan prediksi tersebut.

Tujuan utama pembuatan model Machine Learning adalah membuat prdiksi yang dapat seakurat mungkin menentukan apakah seorang karyawan akan direkomendasikan untuk promosi pada kriteria tertentu. Model ini akan memungkinkan perusahaan untuk mengidentifikasi kandidat yang memenuhi syarat lebih awal dalam proses tersebut, sehingga mempercepat siklus promosi dan memastikan transisi ke peran baru yang lebih lancar (efisien) dan karyawan yang tepat untuk dipromosikan (efektif).

Selain itu, dengan model ML yang akan dibuat HR ingin mengetahui variabel apa saja yang memberikan pertimbangan lebih besar untuk HR agar karyawan dapat terpilih untuk dipromosikan.

### **Kesimpulan**

1. Pada model benchmarking kita menggunakan recall sebagai metrics evaluation untuk pemilihan model. 
    Dilakukannya promosi di perusahaan, target utama yang ingin dicapai perusahaan pastinya agar jabatan tersebut diisi oleh karyawan yang benar-benar tepat. Oleh karena ini, model diharapkan berhasil memprediksi kelas positif (layak dipromosikan) dengan baik. Karena prioritas tersebut, recall dipilih sebagai metrics evaluation.

2. Model XGBoostClassifier (XGB) memiliki nilai terbaik dalam benchmarking. Model XGBoost adalah metode boosting, yang berarti model dibangun secara bertahap dengan menambahkan pohon keputusan baru yang mencoba memperbaiki kesalahan dari pohon sebelumnya. Setiap pohon baru berusaha untuk memprediksi kesalahan (residuals) dari prediksi sebelumnya.
 
3. Dataset yang dipakai merupakan data yang tidak seimbang dengan kelas negatif sebagai mayoritas sehingga model cenderung lebih mudah mempelajari kelas negatif (0). Metode balancing yang digunakan dalam model ini adalah RandomUnderSampling dengan sampling_strategy 85%.

4. Hasil prediksi model kita berhasil mendapatkan 61% karyawan yang benar-benar layak untuk dipromosikan, serta berhasil mengeliminasi karyawan mengurangi 88% karyawan yang tidak layak untuk dipromosikan.

5. Apabila dibandingkan dengan metode rule-based, model kita menunjukkan performance yang jauh lebih baik. Rule-based prediction hanya mampu memprediksi 15% karyawan yang benar-benar layak. Ini salah satu alasan pendukung mengapa perusahaan membutuhkan model dalam memprediksi karyawan yang layak dipromosikan.

6. Dari hasil feature importance, tiga fitur penting yang memberi dampak terbesar dalam model ini adalah awards_won, previous_year_rating, dan avg_training_score.

7. Prediksi model berhasil menekan biaya sebesar sekitar 75%.
