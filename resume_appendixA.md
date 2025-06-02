# Resume Appendix A - Tugas Pertemuan 5 (18 Maret 2025)

NAMA: Firda Rahayu

NRP: 3245211002

KELAS: IT A

## SISTEM OPERASI YANG BERPENGARUH

pentingnya mempelajari sistem operasi lama untuk memahami bagaimana fitur-fitur sistem operasi modern berkembang. Fitur-fitur canggih yang awalnya hanya ada di komputer besar (mainframe) kini telah bermigrasi ke komputer yang lebih kecil, seperti mikrokomputer dan perangkat genggam. Mempelajari sistem operasi lama membantu kita memahami evolusi sistem operasi dan bagaimana konsep-konsep seperti multitasking dan jaringan telah menjadi standar dalam komputasi modern.

### A.1 MIGRASI FITUR

evolusi sistem operasi, dimulai dari sistem operasi lama yang kompleks hingga sistem operasi modern yang lebih sederhana. Fitur-fitur canggih yang awalnya hanya ada di komputer besar (mainframe) kini telah bermigrasi ke komputer yang lebih kecil, seperti mikrokomputer dan perangkat genggam. Contohnya, sistem operasi MULTICS yang dikembangkan pada tahun 1960-an menjadi dasar bagi pengembangan UNIX dan sistem operasi modern lainnya. Mempelajari sistem operasi lama membantu kita memahami bagaimana konsep-konsep seperti multitasking dan jaringan telah menjadi standar dalam komputasi modern.

### A.2 SISTEM AWAL

perbedaan signifikan antara komputasi sebelum dan sesudah tahun 1940-an, di mana sebelum era tersebut, perangkat komputasi dirancang untuk tugas spesifik dan tetap, memerlukan upaya manual yang besar untuk modifikasi, namun perubahan revolusioner terjadi dengan munculnya konsep komputer program tersimpan tujuan umum, yang diinisiasi oleh Alan Turing dan John von Neumann, memungkinkan komputer untuk melakukan berbagai tugas dengan mengubah program, menandai lompatan besar dalam fleksibilitas dan kemampuan komputasi, dengan Manchester Mark 1 dan Ferranti Mark 1 sebagai tonggak penting, masing-masing sebagai komputer program tersimpan tujuan umum pertama yang berfungsi dan komputer komersial pertama, di mana operasi komputer awal sangat berbeda dengan komputer modern, dengan pemrograman dan operasi dilakukan langsung dari konsol, debugging dilakukan dengan memeriksa memori dan register, dan keluaran dicetak atau diponskan ke media seperti pita kertas atau kartu, mencerminkan keterbatasan teknologi pada masa itu

    A.2.1 SISTEM KOMPUTER KHUSUS
    perkembangan sistem komputer awal yang ditandai dengan munculnya perangkat keras dan perangkat lunak tambahan seperti pembaca kartu, pencetak garis, pita magnetik, assembler, loader, dan linker. Perkembangan ini bertujuan untuk mempermudah tugas pemrograman dan meningkatkan penggunaan ulang perangkat lunak.

    Proses menjalankan program pada masa itu sangat rumit dan memakan waktu, melibatkan serangkaian langkah seperti memuat dan membongkar pita magnetik, pita kertas, dan kartu pons. Waktu pengaturan pekerjaan menjadi masalah utama karena CPU sering menganggur saat operator memuat pita atau mengoperasikan konsol. Mengingat mahalnya biaya komputer pada masa itu, pemanfaatan yang tinggi menjadi prioritas untuk memaksimalkan investasi. Jika terjadi kesalahan pada salah satu langkah, seluruh proses harus diulang dari awal, yang semakin memperparah masalah efisiensi.

    A.2.2 SISTEM KOMPUTER BERSAMA
    evolusi sistem komputer dari era di mana pemrogram langsung mengoperasikan mesin hingga era di mana operator profesional mengambil alih. Peralihan ini bertujuan untuk mengurangi waktu pengaturan pekerjaan (setup time) dan meningkatkan efisiensi. Operator, dengan keahliannya dalam memasang pita, dapat menjalankan pekerjaan secara lebih efisien daripada pemrogram. Namun, operator tidak dapat men-debug program, sehingga kesalahan program memerlukan dump memori dan register untuk di-debug oleh pemrogram.

    Untuk lebih meningkatkan efisiensi, pekerjaan dengan kebutuhan serupa dikelompokkan (batched) dan dijalankan bersamaan. Hal ini mengurangi frekuensi pengaturan ulang mesin untuk pekerjaan yang berbeda. Namun, masih ada masalah dengan waktu idle CPU saat operator memuat pekerjaan baru. Untuk mengatasi masalah ini, dikembangkanlah monitor residen, sebuah program kecil yang secara otomatis mentransfer kontrol antara pekerjaan. Monitor residen menggunakan kartu kontrol untuk menentukan program mana yang akan dijalankan, sehingga memungkinkan pengurutan pekerjaan otomatis.

    A.2.3 I/O TUMPANG TINDIH
    era komputer awal, I/O lambat seperti pembaca kartu dan pencetak garis diganti dengan pita magnetik yang lebih cepat. Operasi off-line memungkinkan CPU bekerja lebih efisien dengan membaca/menulis ke pita melalui perangkat terpisah. Beberapa pembaca-ke-pita dan pita-ke-pencetak dapat digunakan untuk satu CPU, meningkatkan throughput. Namun, ada penundaan dalam menjalankan pekerjaan karena harus menunggu pita penuh.

    Sistem disk kemudian menggantikan pita, menghilangkan masalah akses berurutan. Disk memungkinkan akses acak, sehingga CPU dapat membaca data dari disk saat perangkat lain menulisnya. Spooling digunakan untuk membaca input ke disk dan menyimpan output di disk sampai perangkat output siap. Ini meningkatkan efisiensi dan mengurangi waktu idle CPU.

### A.3 ATLAS

Sistem operasi Atlas, yang dikembangkan di Universitas Manchester pada akhir 1950-an hingga awal 1960-an, memperkenalkan banyak konsep inovatif yang menjadi dasar sistem operasi modern. Fitur utamanya meliputi manajemen memori dengan paging permintaan menggunakan drum sebagai memori utama dan memori inti sebagai cache, serta algoritma penggantian halaman yang canggih berdasarkan prediksi perilaku akses memori di masa lalu. Atlas juga merupakan sistem operasi batch dengan spooling yang efisien untuk mengelola perangkat periferal.

### A.4 XDS-940

Sistem operasi XDS-940, yang dikembangkan di Universitas California, Berkeley pada awal 1960-an, adalah sistem berbagi waktu yang menggunakan paging untuk manajemen memori tetapi hanya untuk relokasi, bukan paging permintaan. Fitur utamanya mencakup mode monitor pengguna untuk membatasi akses ke instruksi istimewa, panggilan sistem untuk manajemen sumber daya seperti file, dan kemampuan untuk membuat dan mengelola subproses dalam struktur pohon. XDS-940 memungkinkan beberapa proses pengguna untuk berada dalam memori secara bersamaan dan mendukung berbagi halaman untuk kode reentrant hanya baca, meningkatkan jumlah pengguna yang dapat ditangani sistem.

### A.5 THE

Sistem operasi THE, yang dikembangkan di Belanda pada pertengahan 1960-an, terkenal karena desain berlapisnya yang bersih dan penggunaan semaphore untuk sinkronisasi proses statis. Sistem ini menggunakan algoritma penjadwalan CPU prioritas, skema paging perangkat lunak untuk manajemen memori dalam lingkungan Algol terbatas, dan algoritma bankir untuk menghindari kebuntuan. Sistem Venus, yang terkait erat, meningkatkan desain THE dengan implementasi mikrokode untuk kecepatan yang lebih baik dan menggunakan memori tersegmentasi halaman dalam lingkungan berbagi waktu.

### A.6 RC 4000

Sistem operasi RC 4000 dirancang dengan fokus pada konsep inti (kernel) yang fleksibel untuk mendukung berbagai jenis sistem operasi. Kernel ini mengelola proses konkuren dengan penjadwalan round-robin dan komunikasi berbasis pesan. Fitur utamanya mencakup primitif untuk pengiriman dan penerimaan pesan, penanganan I/O sebagai proses, dan kemampuan untuk menyesuaikan urutan antrian pesan. Desain ini menekankan modularitas dan kemampuan adaptasi.

### A.7 CTSS

CTSS, dikembangkan di MIT pada tahun 1961, adalah sistem berbagi waktu eksperimental yang berhasil mendukung hingga 32 pengguna interaktif. Sistem ini menggunakan algoritma antrian umpan balik bertingkat untuk penjadwalan CPU dan mengelola memori dengan melakukan swap gambar memori pengguna antara memori dan drum. Meskipun memiliki keterbatasan, CTSS membuktikan bahwa berbagi waktu adalah konsep yang layak dan efektif, serta digunakan hingga tahun 1972.

### A.8 MULTICS

MULTICS, yang dikembangkan di MIT dari tahun 1965 hingga 1970, dirancang sebagai sistem berbagi waktu yang ambisius dengan tujuan untuk menyediakan layanan komputasi seperti utilitas listrik. Sistem ini memperkenalkan konsep memori tersegmentasi-halaman, ruang alamat virtual terintegrasi dengan sistem file, dan struktur file hierarkis. MULTICS juga menggunakan penjadwalan CPU antrian umpan balik bertingkat dan mekanisme perlindungan yang canggih. Meskipun kompleks dan ditulis dalam PL/1 dengan sekitar 300.000 baris kode, MULTICS berkontribusi pada perkembangan sistem operasi modern dengan inovasi-inovasinya dalam manajemen memori dan sistem file.

### A.9 IBM OS/360

IBM OS/360 dirancang untuk menjadi sistem operasi universal untuk berbagai komputer IBM, tetapi ambisinya yang besar membuatnya kompleks dan tidak efisien. Sistem ini memiliki masalah dengan manajemen file, bahasa kontrol pekerjaan yang rumit, manajemen memori yang terbatas, dan overhead yang tinggi. Meskipun upaya dilakukan untuk meningkatkan sistem dengan penambahan memori virtual dan sistem berbagi waktu, OS/360 dan penerusnya, MVS, tetap menjadi sistem batch yang kompleks dan sulit untuk dikelola. Sistem berbagi waktu yang direncanakan, TSS/360, gagal karena terlalu besar dan lambat, sehingga sistem sementara seperti TSO dan CMS terus digunakan. Kegagalan ini sebagian disebabkan oleh kompleksitas sistem dan asumsi yang salah tentang ketersediaan daya komputasi jarak jauh

### A.10 TOPS-20

TOPS-20, yang berasal dari proyek penelitian TENEX di BBN dan dikembangkan lebih lanjut oleh DEC, adalah sistem operasi berbagi waktu yang sangat berpengaruh. Dengan interpreter baris perintah canggih dan dukungan memori virtual melalui paging perangkat keras, TOPS-20 menjadi sistem berbagi waktu paling populer pada masanya. Meskipun DEC kemudian beralih ke sistem VAX dan VMS, TOPS-20 tetap menjadi tonggak penting dalam sejarah sistem operasi.

### A.11 CP/M & MS/DOS

CP/M dan MS-DOS adalah sistem operasi penting dalam sejarah komputasi pribadi. CP/M, yang dikembangkan oleh Gary Kindall, adalah sistem operasi "standar" awal untuk komputer hobi pada tahun 1970-an, berjalan pada CPU Intel 8080. MS-DOS, yang dikembangkan oleh Microsoft untuk IBM, mirip dengan CP/M tetapi dengan fitur yang lebih kaya dan menjadi sistem operasi komputer pribadi yang dominan selama tahun 1980-an dan 1990-an. Namun, MS-DOS memiliki keterbatasan seperti kurangnya memori terlindungi.

### A.12 SISTEM OPERASI MACHINTOS DAN WINDOWS

Apple Macintosh mempelopori GUI untuk komputer rumahan pada tahun 1984, tetapi kemudian dikalahkan oleh Microsoft Windows, yang dilisensikan untuk berbagai komputer. Seiring kemajuan teknologi, sistem operasi komputer pribadi menyerap fitur-fitur dari mainframe dan minikomputer, meningkatkan daya dan kegunaannya. Persaingan antara Windows dan Mac OS terus berlanjut hingga kini, sementara Linux juga mendapatkan popularitas, khususnya di kalangan pengguna teknis.

### A.13 MACH

Mach adalah sistem operasi yang dikembangkan di Universitas Carnegie Mellon, yang terkenal karena desain mikrokernelnya yang fleksibel dan dukungannya terhadap multiprosesor dan komputasi terdistribusi. Sistem ini berevolusi dari BSD UNIX dan dirancang untuk kompatibel dengan aplikasi UNIX sambil menyediakan fitur-fitur canggih seperti manajemen memori virtual yang efisien dan komunikasi berbasis pesan. Arsitektur mikrokernel Mach memungkinkan berbagai sistem operasi untuk diimplementasikan di atasnya, dan sistem ini juga digunakan sebagai dasar untuk OSF/1, sebuah upaya sistem operasi penting pada awal 1990-an.

### A.14.1 HYDRA

Hydra adalah sistem operasi yang menekankan perlindungan berbasis kapabilitas, memberikan fleksibilitas yang signifikan dalam manajemen hak akses. Sistem ini memungkinkan pengguna untuk mendefinisikan hak mereka sendiri dan mengelola operasi pada objek melalui prosedur. Fitur penting dari Hydra adalah amplifikasi hak, yang memungkinkan prosedur yang dapat dipercaya untuk mengakses objek dengan hak yang lebih tinggi daripada proses panggilan. Sistem ini juga menyediakan mekanisme untuk mengatasi masalah subsistem yang saling mencurigai. Hydra menawarkan pustaka besar prosedur yang ditentukan sistem dan memungkinkan pemrogram untuk mengintegrasikan panggilan ke prosedur ini ke dalam kode mereka.

### A.14.2 SISTEM CAP CAMBRIDGE

Sistem CAP Cambridge menerapkan pendekatan perlindungan berbasis kapabilitas yang lebih sederhana dibandingkan Hydra, dengan dua jenis kapabilitas: data dan perangkat lunak. Kapabilitas data memberikan akses dasar ke objek, sedangkan kapabilitas perangkat lunak memungkinkan implementasi kebijakan perlindungan yang lebih kompleks melalui prosedur terlindungi. Meskipun memberikan fleksibilitas, perancang subsistem harus memiliki pemahaman yang mendalam tentang prinsip-prinsip perlindungan karena sistem tidak menyediakan pustaka prosedur siap pakai.

### A.15 SISTEM LAINYA

Selain sistem-sistem yang telah dibahas sebelumnya, ada sistem operasi lain dengan fitur-fitur unik. MCP untuk komputer Burroughs adalah yang pertama ditulis dalam bahasa pemrograman sistem dan mendukung segmentasi serta multi-CPU. SCOPE untuk CDC 6600 juga merupakan sistem multi-CPU dengan desain koordinasi dan sinkronisasi proses yang sangat baik.
