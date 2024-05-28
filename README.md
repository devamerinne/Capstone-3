**1. Business Problem Understanding**

**1.1 Context**

Shopaku merupakan sebuah perusahaan yang mempunyai platform e-commerce di mana anda bisa berbelanja berbagai merek yang sudah anda kenal, sekaligus menemukan toko dan penjual  perusahaan secara online terutama untuk produk gadget yaitu laptop dan mobile phone. Dalam dunia e-commerce, keloyalan pelanggan adalah kunci keberhasilan jangka panjang. Salah satu tantangan utama yang dihadapi oleh perusahaan e-commerce adalah churn pelanggan, yaitu pelanggan yang berhenti menggunakan aplikasi dalam periode tertentu. Memahami dan mengelola churn pelanggan sangat penting salah satunya untuk mengoptimalkan strategi pemasaran.

Dengan menganalisis data churn, perusahaan e-commerce dapat mengidentifikasi faktor-faktor yang berkontribusi terhadap churn dan mengembangkan strategi untuk meningkatkan retensi pelanggan. Misalnya, perusahaan dapat menawarkan promosi atau insentif kepada pelanggan dengan skor kepuasan rendah atau mengoptimalkan proses pengiriman untuk mengurangi waktu pengiriman bagi pelanggan yang tinggal jauh dari gudang. Analisis churn membantu dalam mengarahkan upaya pemasaran yang lebih efektif dan meningkatkan pengalaman pelanggan secara keseluruhan.

**1.2 Probelm Statement**

Saat perusahaan berusaha untuk membuat seseorang menjadi pelanggan di perusahaan tersebut, perusahaan pasti sudah mengeluarkan banyak strategi, tenaga, dan waktu untuk mendapatkannya. Hal ini tentu akan sangat disayangkan jika pelanggan tersebut lepas begitu saja.

Oleh sebab itu, sangat penting bagi perusahaan untuk memastikan growth rate perusahaan terus meningkat dan menjaga agar churn rate dapat menurun. Salah satu langkah yang dapat diambil untuk menjaga churn rate dapat menurun adalah dengan memprediksi target pelanggan yang tepat agar dapat disesuaikan metode yang akan diambil guna mencegah churn.

**1.3 Goals :**

Berdasarkan permasalahan tersebut, perusahaan ingin dapat memprediksi peluang pelanggan  yang akan churn atau tidak, sehingga dapat melakukan tindakan pencegahan yang diperlukan. Karena jika perusahaan berfokus pada semua pelanggan, biaya yang dikeluarkan tentu tikdaklah murah. Dan jika perusahaan ingin fokus untuk mendapatkan pelanggan baru tentu akan sulit dan memakan biaya iklan yang lebih mahal.

Dan juga, perusahaan ingin mengetahui apa faktor yang membuat pelanggan churn dan tidak, sehingga dapat memberikan insentif atau promosi khusus untuk mempertahankan pelanggan yang memiliki kecenderungan akan berhenti dan me-maintaince pelanggan yang masih akan tetap tidak churn.

##**1.4 Analytic Approach**

Jadi yang akan dilakukan adalah menganalisis data untuk menemukan pola yang membedakan pelanggan yang churn dan tidak. Kemudian akan dilanjutkan dengan membangun model klasifikasi yang akan membantu perusahaan untuk dapat memprediksi probabilitas seorang pelanggan akan churn atau tidak.

![image](https://github.com/devamerinne/Capstone-3/assets/124213904/f2664985-b59c-4f6e-9b64-187407c87d9a)

Gambar diatas merupakan confusion matrix yang merupakan cross tabulasi antara nilai prediksi dengan nilai aktual. Secara umum kelas terbagi menjadi dua kelas yaitu kelas positif dan kelas negatif atau bisa juga 0 dan 1.

TP adalah singkatan dari True Positif yaitu banyaknya prediksi kelas positif yang memang benar positif. TN adalah True Negatif yaitu banyaknya prediksi kelas negatif yang benar-benar negatif. Keduanya merupakan jenis hasil prediksi yang sesuai dengan kenyataan.
FP merupakan singkatan dari False Positif yang berarti banyaknya prediksi kelas positif yang sebenarnya masuk ke dalam kelas negatif. Sedangkan FN adalah False Negatif, banyaknya prediksi kelas negatif yang pada kenyataanya masuk ke dalam kelas positif. Keduanya mengindikasikan hasil prediksi yang ternyata salah. FN dikenal juga dengan istilah type I error sedangkan FP dikenal dengan istilah type II error

Pada data yang telah kami dapatkan maka confusion matrux dapat diinterpretasikan sebagai beriku.

**Target**

0 (Negative): No Churn

1 (Positive): Churn

**Interpretasi**
- True Positive (TP) : Prediksi Pelanggan Churn padahal Aktualnya Churn
- True Negative (TN) : Prediksi Pelanggan No Churn padahal Aktualnya No Churn
- False Positive (FP) : Prediksi Pelanggan Churn padahal Aktualnya No Churn
- False Negative (FN) : Prediksi Pelanggan No Churn padahal Aktualnya Churn

Berdasarkan interpretasi diatas, diketahui ada 2 Error yang akan terjadi, yang dapat merugikan perusahaan
- Type 1 error : False Positive, prediksi pelanggan Churn padahal aktualnya No Churn

    Konsekuensi: Melakukan upaya pencegahan Churn yang tidak perlu, seperti memberikan insentif atau promosi khusus untuk mempertahankan pelanggan yang sebenarnya tidak churn.

- Type 2 error : False Negative, prediksi pelanggan No Churn padahal aktualnya Churn

    Konsekuensi: Perusahaan mungkin kehilangan pelanggan tanpa melakukan tindakan pencegahan yang diperlukan.

Berikut adalah confusion matrix dari Ecommerce Churn yang telah dijabarjkan
![image](https://github.com/devamerinne/Capstone-3/assets/124213904/318376d0-8f22-42f6-8a0e-96d8f27ee208)


Pada analisis ini akan dititikberatkan pada perhitungan **recall** karena kami ingin melihat berapa persen pelanggan yang diprediksi churn dibandingkan dengan keseluruhan pelanggan yang benar-benar churn. Kami juga menganggap bahwa False Positif lebih baik daripada False Negatif. Yang artinya kami lebih memilih mentreatment orang-orang yang diprediksi churn padahal tidak churn daripada membiarkan orang-orang yang diprediksi tidak churn padahal aktualnya churn. [disni](https://rey1024.medium.com/mengenal-accuracy-precission-recall-dan-specificity-serta-yang-diprioritaskan-b79ff4d77de8)



Data yang kami dapatkan bersumber dari kaggle [disini](https://www.kaggle.com/datasets/ankitverma2010/ecommerce-customer-churn-analysis-and-prediction/data)

Dataset ini menyajikan informasi yang dapat digunakan untuk menganalisis perilaku churn pelanggan dan mengidentifikasi faktor-faktor yang mempengaruhi keputusan mereka untuk berhenti berlangganan. Berikut adalah ringkasan informasi dalam dataset ini:

1. Informasi Demografi Pelanggan (Dependents): Data ini memberikan wawasan tentang pribadi pelanggan, yang mungkin dapat memengaruhi kestabilan keanggotaan mereka dalam layanan. Misal pada feature `Warehouse To Home` dan `Marital Status`
2. Penggunaan Aplikasi Oleh Pelanggan: Dataset mencakup informasi tentang bagaimana pelanggan dalam menggunakan aplikasi tersebut, seperti: `Tenure`,`Number of Device Registered`, `Prefer Order Cat`, `Number Of Address`, `Day Since Last Order`, dan `Cashbak Amount` .
3. Kepuasan Pelanggan: Data ini meliputi penilaian pelanggan `Satisfaction Score` dan adanya komplain dari pelanggan `Complain`.
4. Status Churn Pelanggan: Terakhir, kolom yang kritis dalam dataset adalah kolom `Churn`, yang menunjukkan apakah seorang pelanggan telah berhenti dari aplikasi. Analisis terhadap kolom ini akan membantu dalam memahami pola churn pelanggan dan mengidentifikasi faktor-faktor yang berkaitan dengan keputusan mereka untuk meninggalkan layanan.

Dengan menggunakan dataset ini, akan dilakukan analisis yang cermat untuk mengidentifikasi pola-pola yang terkait dengan churn pelanggan. Hal ini akan membantu dalam mengembangkan strategi retensi yang lebih efektif dan meminimalkan kehilangan pelanggan yang bernilai bagi perusahaan.

Tujuan dari project ini adalah untuk mengetahui prediksi seorang customer apakah akan melakukan churn atau tidak dari ecommerce ini. Berdasarkan business problem di atas, diketahui bahwa:

- model dapat mengetahui 74% pelanggan yang tidak churn dan 91% pelanggan yang churn (Berdsarkan Recall)
- Selain itu model memiliki kemungkinan prediksi benar untuk pelanggan yang akan churn sebesar 41%. Maka masih ada pelanggan yang churn dan diprediksi sebagai tidak churn sebesar 9%.


Type 1 error : False Positive

Konsekuensi: *operation loss* karena mengeluarkan biaya promo untuk pelanggan yang tidak tepat. Biaya yang dikeluarkan sebesar 50 USD per customer per bulan [disini](https://sci-hub.se/https://doi.org/10.1016/j.jretconser.2017.10.007).

Type 2 error : False Negative

Konsekuensi: *profit loss* karena customer churn. biaya yang dikeluarkan 5x lipat dari biaya promo ke customer 250 USD per customer per bulan [disini](https://sci-hub.se/https://doi.org/10.1016/j.jretconser.2017.10.007).

**TANPA MENGGUNAKAN MACHINE LEARNING**

Perusahaan e-commerce tidak dapat mengetahui customer yang akan melakukan churn, sehingga perusahaan e-commerce harus memberikan promosi ke semua customer, agar perusahaan tidak kehilangan customer. Ini menyebabkan perusahaan e-commerce harus mengeluarkan biaya yang besar dalam mengimplentasikan strategi promosinya.

- Pengeluaran perusahaan untuk promosi ke semua customer 50 USD x 653 = 32.650 USD
- Promosi yang tepat sasaran pada orang yang churn: 250 USD X 107 = 26.750 USD

Sehingga diketahui bahwa perusahaan mengeluarkan biaya yang tidak tepat sasaran (biaya promosi untuk customer yang loyal) sebesar: - 32.650 + 26.750 USD = - 5.900 USD. Karena 653 customer adalah 1/5 dari total customer (3.261) maka -5.900 USD x 5 = -29.500 USD. Biaya tersebut seharusnya dapat ditekan jika menggunakan Machine Learning

**DENGAN MENGGUNAKAN MACHINE LEARNING**

Biaya yang tidak tepat sasaran di atas, dapat ditekan jika menggunakan Machine Learning, dengan memprediksi customer yang akan melakukan churn. Sehingga biaya promosi dapat difokuskan kepada customer yang akan melakukan churn, berdasarkan dari hasil prediksi dari Machine Learning.

- Pengeluaran promosi oleh perusahaan yang diprediksi churn (FP+TP): (142+97) x 50 USD = 11.950 USD
- Perusahaan kehilangan customer karena tidak terprediksi akan churn (FN): 10 x 250 USD = 2.500 USD
- Promosi tepat sasaran (TP): 97 x 250 USD = 24.250 USD

Sehingga diketahui bahwa perusahaan e-commerce berhasil menghasilkan Revenue per bulan sebesar: - 11.950 - 2.500 + 24.250 = 9.800 USD. Karena 653 customer adalah 1/5 dari total customer (3.261) maka 9.800 USD x 5 = 49.000 USD

**PERBANDINGAN PENGGUNAAN MACHINE LEARNING**

- Sebelum pakai ML: perusahaan merugi -29.500 USD per bulan
- Setelah menggunakan ML: perusahaan berhasil menghasilkan profit 49.000 USD per bulan

Dapat disimpulkan bahwa Machine Learning dengan menggunakan algoritma Logistic Regression berhasil menghasilkan profit 49.000 per bulan.

**Faktor yang mempengaruhi Customer Churn**

Berdasarkan Feature Importance dan Summary Plot, 3 Faktor utama yang mempengaruhi prediksi Customer Churn secara berurutan adalah

1. ***Tenure***, semakin kecil nilai Tenure artinya semakin baru customer berlangganan semakin besar kemungkinan Customer akan churn dan semakin lama customer berlangganan semakin betah dia terhadap layanan perusahaan.

2. ***Prefered Order Cat***, terutama pada pembelian kategori barang yang memiliki durasi pakai panjang seperti laptop dan ponsel.

3. ***Complain***, semakin besar nilai Complain semakin besar kemungkinan Customer akan Churn dan sebaliknya. nilai yang besar artinya customer melakukan complain atau customer tidak puas terhadap layanan.

**Recommendation**
***For Business***

Customer yang melakukan churn dapat menimbulkan kerugian bagi perusahaan.

perusahaan e-commerce perlu menyusun strategi agar dapat tetap menjaga kualitas produk dan pelayanan agar dapat menghindari complain yang masuk.
perusahaan e-commerce perlu menyusun strategi agar dapat menciptakan loyalitas pelanggan, baik dengan melakukan inovasi pada produk yang dipasarkan dan memberikan penawaran yang menarik, sehingga tenure customer semakin tinggi.
Perusahaan perlu menggunakan machine learning yang sudah dibuat, agar dapat mengurangi kerugian bagi perusahaan dengan memberikan promosi tepat sasaran kepada customer yang akan melakukan churn.
Untuk prediksi customer selanjutnya dapat menggunakan WebApp yang sudah disediakan, guna memudahkan perusahaan dan dapat mendeteksi sedini mungkin kemungkinan customer churn.


***For Model***

Akurasi model machine learning yang dibuat terbatas sehingga diperlukan

- Mengumpulkan lebih banyak data, terutama pada Minority Class
- Menambahkan fitur2 atau kolom2 baru yang kemungkinan bisa berhubungan seperti lama pengiriman produk, ketepatan waktu pengiriman, dan lain-lain.
- Meminimalisir kesalahan penulisan data dan memastikan data yang diperoleh tidak ada yang kosong atau tidak terisi

Semoga laporan ini dapat membantu perusahaan untuk menprediksi customer yang akan churn sehingga dapat mengurangi profit loss. Terima kasih.
