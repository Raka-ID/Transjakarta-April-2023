# Transjakarta-April-2023

# __Latar Belakang__

Dalam manajemen sistem transportasi publik, BUMD PT Transjakarta ingin meningkatkan kinerja operasional dan layanan bagi penumpangnya, sehingga pemahaman yang mendalam tentang operasional dan kondisi di lapangan sangat penting untuk memastikan efisiensi dan efektivitas layanan guna meningkatkan kepuasan bagi penumpangnya. Dengan mengumpulkan data perjalanan layanan Transjakarta dalam kurun waktu tertentu tim operasional kantor dapat melakukan analisis yang mendalam untuk mengambil keputusan yang berbasis data.

---

# __Pernyataan Masalah__

Perusahaan ingin mengetahui kinerja setiap rute untuk mengidentifikasi faktor-faktor yang memengaruhi keefisienan layanan, yang mungkin memerlukan perbaikan, dan untuk mengoptimalkan penggunaan sumber daya kepuasan penumpang. Pemantauan kinerja rute, waktu tempuh, perilaku dan karakteristik penumpang adalah kunci untuk menyediakan layanan yang memenuhi kebutuhan penumpang dan meningkatkan kepuasan penumpang. Sehingga diangkatlah permasalah berikut untuk dianalisis.

`Bagaimana karakteristik penumpang dan rute perjalanan dari layanan Transjakarta?`

# __Deskripsi Kolom__

No. | Nama Kolom | Dtype | Deskripsi |
| --- | --- | --- | --- |
1 |TransID| `object` | ID Transaksi yang __unik__ di setiap transaksi
2 |CardID| `int64` |Pengidentifikasi utama penumpang. Kartu tersebut digunakan penumpang sebagai tiket masuk dan keluar.
3 |PayCardBank| `object` | __Nama bank__ penerbit kartu penumpang
4 |Name| `object` | __Nama Customer__ yang tercantum di kartu.
5 |Gender| `object` | __Jenis kelamin Customer__ yang tercantum di kartu.
6 |BirthYear| `int64` | __Tahun lahir Customer__ yang tercantum di kartu.
7 |CorridorID| `object` | ID Koridor / __ID Rute__ sebagai kunci pengelompokan rute.
8 |CorridorName| `object` | Nama Koridor / __Nama Rute__ berisi __'awal'__ dan __'akhir'__ untuk setiap rute.
9 |Direction| `float64` | __Arah rute__. __0__ untuk arah __'Pergi'__, __1__ untuk arah __'Kembali'__. 
10 |TapIn_ID| `object` | __ID Pintu Masuk__ (perhentian masuk), untuk mengidentifikasi nama perhentian.
11 |TapIn_Name| `object` | __Nama pintu masuk__ tempat penumpang _tap-in_ kartu.
12 |TapIn_Lat| `float64` | __Garis Lintang__ _tap-in_ kartu di pintu masuk
13 |TapIn_Lon| `float64` | __Garis Bujur__ _tap-in_ kartu di pintu masuk
14 |TapIn_Seq| `int64` | __Urutan pemberhentian__, pemberhentian pertama, pemberhentian kedua, dst. Terkait dengan arah.
15 |TapIn_Time| `datetime64[ns]` | __Waktu__ ketika penumpang masuk (_tap-in_ kartu). __Tanggal dan detail waktu__.
16 |TapOut_ID| `object` | __ID Pintu Keluar__ (perhentian keluar), untuk mengidentifikasi nama perhentian
17 |TapOut_Name| `object` | __Nama pintu keluar__ tempat penumpang _tap-out_ kartu.
18 |TapOut_Lat| `float64` | __Garis Lintang__ _tap-out_ kartu di pintu masuk
19 |TapOut_Lon| `float64` | __Garis Bujur__ _tap-out_ kartu di pintu masuk
20 |TapOut_Seq| `float64` | __Urutan pemberhentian__, pemberhentian pertama, pemberhentian kedua, dst. Terkait dengan arah.
21 |TapOut_Time| `datetime64[ns]` | __Waktu__ ketika penumpang keluar (_tap-out_ kartu). __Tanggal dan detail waktu__.
22 |PayAmount| `float64` | __Jumlah uang yang dibayar__ penumpang. Beberapa gratis. Beberapa tidak.

# __Ringkasan__

Untuk mengoptimalkan kinerja perusahaan BUMD Transjakarta dilakukan analisis data penumpang dan rute perjalanan sehingga didapat beberapa kesimpulan berbasis data yang dapat dijadikan patokan _stakeholder_ dalam menentukan (_decision making_) strategi bisnis yang tepat. Berikut Kesimpulan yang didapat dari hasil analisis karakteristik penumpang dan kinerja rute.

1. Rute yang paling banyak digunakan adalah `1T`: Cibubur - Balai Kota dan `S21`: Ciputat - CSW, sementara Rute yang paling sedikit digunakan adalah `7B`: Kampung Rambutan - Blok M dan `M5`: Matraman Baru - Ancol (M5);
2. Rute yang paling banyak/padat penumpang adalah `JAK.42`: Kampung Melayu - Pondok Kelapa, `JAK.58`: Cilincing - Rorotan, dan `JAK.19`: Pinang Ranti - Kampung Rambutan;
3. Halte paling adalah __Penjaringan__ dan __BKN__, mengindikasikan wilayah populasi yang paling padat di Jakarta dan pusat aktivitas ekonomi di Jakarta;
4. Terdapat perbedaan jumlah TapIn (163) dan TapOut (315) yang cukup tinggi pada Halte BKN, artinya terdapat indikasi kurangnya aksesibilitas atau kesenjangan dalam layanan transportasi di daerah tersebut. Perbedaan besar dalam frekuensi TapIn dan TapOut di halte BKN bisa menunjukkan bahwa jadwal dan frekuensi armada saat ini tidak sesuai dengan kebutuhan penumpang.;
5. Kategori usia lansia cenderung memilih layanan dengan tarif Rp3.500, tidak menggunakan Kartu Layanan Gratis;
6. Proporsi jenis kelamin wanita (53,24%) lebih banyak ±6.48% daripada pria (46,76%);
7. Ada keterkaitan antara _Gender_ dan _PayAmount_: penumpang cenderung tidak memilih layanan Royaltrans;
8. Selain tarif yang lebih tinggi, Median durasi perjalanan Royaltrans lebih tinggi (lama).

# __Rekomendasi__

- Meningkatkan jumlah armada pada koridor yang paling banyak digunakan untuk mengurangi kepadatan dan menghindari overload.
- Meningkatkan infrastruktur dan fasilitas pada koridor dengan frekuensi rendah untuk menarik lebih banyak penumpang.
- Optimalkan rute dan jadwal yang melewati halte Penjaringan dan BKN untuk memastikan bahwa armada yang cukup sering beroperasi di rute-rute yang paling sibuk yang melewati halte tersebut.
- Peningkatan infrastruktur pada kedua halte, seperti perluasan area tunggu, peningkatan fasilitas, atau bahkan penambahan jalur kendaraan.
- Tingkatkan aksesibilitas ke dan/atau dari halte BKN dengan menyediakan lebih banyak rute atau layanan antar-jemput yang menghubungkan halte BKN dengan area-area lain.
- Halte dengan jumlah TapOut yang tinggi (BKN, Penjaringan, dan Term. Senen) mungkin memerlukan fasilitas tambahan untuk menampung jumlah penumpang yang besar. Diperlukan observasi langsung ke lapangan untuk melihat keadaan halte.
- Tingkatkan komunikasi dan informasi melalui papan informasi, aplikasi seluler, dan staf di lapangan untuk membantu penumpang menemukan rute terbaik dan memanfaatkan layanan transportasi secara efisien.
- Buat jalur pendaftaran secara _offline_ untuk Kartu Layanan Gratis bagi lansia. Publikasikan secara optimal (bisa berupa poster, pengumuman/notifikasi, staff di lapangan, dll.) di halte-halte pemberhentian yang banyak dilalui penumpang lansia.
- Karena proporsi penumpang lebih banyak wanita daripada pria maka optimalkan rancangan layanan yang lebih baik dan lebih aman bagi semua pengguna.
- Bila ingin meningkatkan jumlah penumpang dan kepuasannya adalah menurunkan tarif layanan Royaltrans, bila memungkinkan, dan mengoptimalkan jalur/rute dari Royaltrans karena median durasinya lebih tinggi dibanding dengan layanan lain.

# __Kesimpulan__

Dengan pengumpulan data histori setiap penumpang dan perjalanannya, tim operasional kantor dapat menganalisis karakteristik penumpang dan kinerja rute yang dilaluinya. Analisis dilakukan untuk mendapatkan _insight_ dari setiap variabel di dalam dataset untuk dijadikan patokan dalam memilih strategi bisnis yang cocok bagi perusahaan Transjakarta. _Stakeholder_ diharapkan dapat menentukan arah perusahaannya ke jalan yang lebih baik dengan berbasis data.
