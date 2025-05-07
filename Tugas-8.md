 **LAPORAN OPERATION SYSTEM TENTANG “CPU SCHEDULLING”**

 ![alt text](https://github.com/DinoAriel/tes/blob/main/Logo_PENS%20(1).png)


**Anggota Kelompok :**  
Firas Rasendriya Athaillah	   3124500042  
Havid Rosihandanu		   3124500048  
Dino Ariel Ihsan Saputra  	   3124500053

**Dosen Pengajar :**   
Dr Ferry Astika Saputra ST, M.Sc

**PROGRAM STUDI D3 TEKNIK INFORMATIKA POLITEKNIK ELEKTRONIKA NEGERI SURABAYA (PENS) TAHUN 2025**

**A. Analisa Code FCFS Scheduling Algorithm**

* **Code FCFS scheduling :**

![alt text](https://github.com/DinoAriel/tes/blob/main/with.png)


* **Analisa Code :** 

> Code diatas adalah implementasi algoritma penjadwalan CPU FCFS (First-Come, First-Served) . Tujuan utamanya adalah menghitung Completion Time (CT), Turnaround Time (TAT) dan Waiting Time (WT), untuk setiap proses, serta rata-ratanya.

> Kode dimulai dengan struct yang disebut 'proc' yang memiliki beberapa variabel integer: no, at, bt, ct, tat, wt. Ini merupakan singkatan untuk nomor proses, waktu kedatangan, waktu burst, waktu penyelesaian, waktu penyelesaian, dan waktu tunggu. Struct digunakan untuk menyimpan detail setiap proses.

> Selanjutnya, ada fungsi 'read' yang mengambil integer 'i' dan mengembalikan struct 'proc'. Fungsi ini meminta pengguna untuk memasukkan waktu kedatangan dan waktu burst untuk setiap proses, menetapkannya ke kolom at dan bt pada struct. Nomor proses (no) ditetapkan ke 'i', yang diberikan sebagai argumen. Fungsi ini dipanggil dalam loop di fungsi utama untuk membaca semua proses.

> Dalam fungsi utama, variabel dideklarasikan: array struct 'proc', struct sementara untuk pertukaran, float untuk waktu penyelesaian dan waktu tunggu rata-rata, dan bilangan bulat untuk jumlah proses dan waktu penyelesaian. Pengguna diminta untuk memasukkan jumlah proses, lalu loop membaca detail setiap proses menggunakan fungsi 'read'.

> Setelah membaca semua proses, ada loop bersarang menggunakan bubble sort untuk mengurutkan proses berdasarkan waktu kedatangannya (at). Ini penting untuk FCFS, karena proses harus dieksekusi sesuai urutan kedatangannya. Pengurutan memastikan bahwa proses dengan waktu kedatangan paling awal muncul lebih dulu.

> Setelah diurutkan, kode menghitung waktu penyelesaian (ct), waktu penyelesaian (tat) dan waktu tunggu (wt) untuk setiap proses. Waktu penyelesaian diakumulasikan dengan menambahkan waktu burst setiap proses. Waktu penyelesaian dihitung sebagai ct dikurangi waktu kedatangan, dan waktu tunggu adalah waktu penyelesaian dikurangi waktu burst.

> Bagian keluaran mencetak tabel dengan semua waktu yang dihitung. waktu tunggu dalam kasus di mana suatu proses mulai dieksekusi segera setelah tiba tanpa menunggu. 

* **Hasil Compile FCFS Scheduling Algorithm** 

![alt text](https://github.com/DinoAriel/tes/blob/main/with-fcs.png)


**B. Analisa Code FCFS Scheduling Algorithm Withoout Arival Time** 

* **Code FCFS Scheduling Algorithm Withoout Arival Time**  
  
![alt text](https://github.com/DinoAriel/SisOp-2025/blob/main/without-fcs.png)

  **Analisa Code :** 

	  
> Kode dimulai dengan mendefinisikan struktur proc dengan no, bt, ct, tat, wt. Lalu ada fungsi baca yang mengambil bilangan bulat i dan mengembalikan proc. Fungsi ini membaca waktu burst untuk setiap proses. Fungsi utama mendeklarasikan array proc, variabel untuk rata-rata, n untuk jumlah proses, dan ct untuk waktu penyelesaian.

> Bagian utama membaca setiap proses menggunakan fungsi baca. Kemudian menghitung CT, TAT, WT untuk setiap proses dalam urutan yang dimasukkan (karena tidak ada waktu kedatangan, ini murni FCFS berdasarkan urutan input). Tidak ada langkah pengurutan di sini, tidak seperti contoh yang menyebutkan pengurutan gelembung. Itu karena tanpa waktu kedatangan, urutannya hanyalah urutan input.

> Loop di main setelah membaca proses menghitung CT dengan mengakumulasikan waktu burst. Untuk setiap proses, ct dimulai pada 0 dan bertambah dengan bt setiap proses. Maka TAT adalah CT \- 0 (karena tidak ada waktu kedatangan, dengan asumsi semua tiba pada 0), yang sama dengan CT. WT adalah TAT \- bt, yang sama dengan waktu tunggu (waktu yang dihabiskan untuk menunggu sebelum eksekusi dimulai). RT (waktu respons) sama dengan WT di FCFS karena pertama kali proses berjalan adalah waktu mulainya, yaitu saat waktu tunggu berakhir.

> Output dari code diatas adalah hasil hitung CT, TAT dan WT yang disajikan dalam bentuk table.

* **Hasil Compile FCFS Scheduling Algorithm Withoout Arival Time**

![alt text](https://github.com/DinoAriel/SisOp-2025/blob/main/without.png)

**Kesimpulan** 
> Perbedaan utama antara FCFS **dengan dan tanpa arrival time** terletak pada kompleksitas dan realisme. Tanpa arrival time, algoritma ini sangat sederhana dan cocok untuk sistem di mana semua proses dimulai bersamaan, seperti komputasi batch. Namun, ini tidak realistis untuk sistem interaktif di mana proses tiba secara dinamis. Sebaliknya, FCFS dengan arrival time lebih fleksibel tetapi memerlukan pengurutan proses berdasarkan waktu kedatangan, sehingga menambah kompleksitas perhitungan.  


> Contoh output untuk tiga proses dengan BT \= 5, 3, dan 8 menghasilkan CT \= 5, 8, 16; TAT \= 5, 8, 16; dan WT \= 0, 5, 8\. Rata-rata TAT adalah **9.67** dan rata-rata WT adalah **4.33**. Dari sini terlihat bahwa FCFS tanpa arrival time cenderung menyebabkan **waiting time yang tinggi** untuk proses dengan burst time panjang (seperti P3), karena proses harus menunggu proses sebelumnya selesai. Ini dikenal sebagai **efek convoy**, salah satu kelemahan FCFS.  


> Kesimpulannya, FCFS tanpa arrival time adalah pendekatan yang sederhana dan efisien untuk kasus khusus di mana semua proses siap di waktu \`0\`. Namun, untuk sistem yang lebih dinamis, diperlukan varian FCFS dengan arrival time atau algoritma lain seperti Shortest Job First (SJF) yang lebih adil dalam mengurangi waiting time. Pemilihan algoritma bergantung pada karakteristik sistem dan sifat proses yang dijalankan.
