# Resume Chapter 1: 1.34 - 1.40

Name: Firda Rahayu

NRP: 3124521002

Class: 1 TI A

## Peralihan dari Mode Pengguna ke Mode Kernel

- Timer digunakan untuk mencegah infinite loop atau proses yang memonopoli sumber daya.

- Timer diatur untuk menginterupsi komputer setelah periode waktu tertentu.

- Sebuah counter disimpan dan dikurangi oleh clock fisik.

- Sistem operasi mengatur counter (instruksi privileged).

- Ketika counter mencapai nol, sebuah interrupt dihasilkan.

- Timer diatur sebelum penjadwalan proses untuk mendapatkan kembali kontrol atau menghentikan program yang melebihi waktu yang dialokasikan.


## Manajemen Proses

- Sebuah proses adalah program yang sedang dieksekusi, merupakan unit kerja dalam sistem.

- Proses memerlukan sumber daya seperti CPU, memori, I/O, dan file untuk menyelesaikan tugasnya.

- Penghentian proses memerlukan pengembalian sumber daya yang dapat digunakan kembali.

- Proses berutas tunggal memiliki satu penghitung program yang menentukan lokasi instruksi berikutnya yang akan dieksekusi.

- Proses berutas ganda memiliki satu penghitung program per utas.

- Sistem biasanya memiliki banyak proses yang berjalan secara bersamaan di satu atau lebih CPU.

- Konkurensi dicapai dengan multipleksing CPU di antara proses/utas


## Aktivitas Manajemen Proses

Sistem operasi bertanggung jawab atas aktivitas-aktivitas berikut dalam manajemen proses:

- Membuat dan menghapus proses pengguna dan sistem.

- Menunda dan melanjutkan proses.

- Menyediakan mekanisme untuk sinkronisasi proses.

- Menyediakan mekanisme untuk komunikasi proses.

- Menyediakan mekanisme untuk penanganan kebuntuan (deadlock).   


## Manajemen Memori

- Untuk menjalankan program, semua (atau sebagian) instruksi harus berada di memori.

- Manajemen memori menentukan apa yang ada di memori dan kapan.

- Aktivitas manajemen memori meliputi: 
  * Melacak bagian memori mana yang sedang digunakan dan oleh siapa.

  * Memutuskan proses (atau bagiannya) dan data mana yang akan dipindahkan ke dan dari memori.

  * Mengalokasikan dan membebaskan ruang memori sesuai kebutuhan.


## Manajemen Sistem Berkas

- Sistem operasi menyediakan tampilan penyimpanan informasi yang seragam dan logis.

- Sistem operasi mengabstraksi properti fisik ke unit penyimpanan logis - berkas (file).

- Aktivitas manajemen sistem berkas meliputi: 

  * Membuat dan menghapus berkas dan direktori.

  * Primitif untuk memanipulasi berkas dan direktori.

  * Pemetaan berkas ke penyimpanan sekunder.

  * Pencadangan berkas ke media penyimpanan yang stabil (non-volatile).


## Manajemen Penyimpanan Massal

- Disk biasanya digunakan untuk menyimpan data yang tidak muat di memori utama atau data yang harus disimpan untuk waktu yang lama.

- Manajemen yang tepat sangat penting karena kecepatan operasi komputer bergantung pada subsistem disk dan algoritmanya.

- Aktivitas sistem operasi meliputi: 
  * Pemasangan dan pelepasan (mounting and unmounting).

  * Manajemen ruang kosong.

  * Alokasi penyimpanan.

  * Penjadwalan disk.

  * Pemartisian.
  
  * Perlindungan.

- Beberapa penyimpanan tidak perlu cepat, seperti penyimpanan tersier yang meliputi penyimpanan optik dan pita magnetik, yang juga harus dikelola oleh sistem operasi atau aplikasi.


## Caching

- Caching adalah prinsip penting yang dilakukan di berbagai tingkatan dalam komputer, baik di perangkat keras, sistem operasi, maupun perangkat lunak.

- Informasi yang sedang digunakan disalin dari penyimpanan yang lebih lambat ke penyimpanan yang lebih cepat untuk sementara.

- Penyimpanan yang lebih cepat (cache) diperiksa terlebih dahulu untuk menentukan apakah informasi ada di sana.

- Jika ada, informasi digunakan langsung dari cache (cepat).

- Jika tidak, data disalin ke cache dan digunakan di sana.

- Cache lebih kecil dari penyimpanan yang di-cache.

- Manajemen cache adalah masalah desain yang penting, termasuk ukuran cache dan kebijakan penggantian.

