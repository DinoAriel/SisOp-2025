# A. Pengertian Container dan Virtualisasi

## a) Pengertian

### 1. Container

> Container adalah teknologi yang memungkinkan pengemasan aplikasi beserta semua dependensinya (library, framework, konfigurasi) ke dalam satu paket yang ringan dan portabel. Container berbagi kernel OS host, sehingga lebih efisien dibandingkan virtualisasi.

### 2. Virtualisasi

> Virtualisasi adalah teknologi yang memungkinkan pembuatan versi virtual dari sumber daya fisik, seperti server, penyimpanan, atau jaringan. Dengan virtualisasi, satu mesin fisik dapat dipecah menjadi beberapa mesin virtual (VM) yang berjalan secara independen.

## b) Perbedaan

| ASPEK               | CONTAINER                              | VIRTUALISASI                              |
|---------------------|----------------------------------------|------------------------------------------|
| Sumber Daya         | Hemat sumber daya (CPU, RAM, penyimpanan). | Lebih boros sumber daya karena setiap VM memerlukan OS lengkap. |
| Waktu Memulai       | Sangat cepat (hitungan detik).         | Lebih lambat (karena harus boot OS lengkap). |
| Isolasi Keamanan    | Isolasi terbatas, karena berbagi kernel host. Risiko keamanan jika kernel host bermasalah. | Isolasi lebih kuat, karena setiap VM terpisah secara penuh. |
| Portabilitas        | Sangat portabel, dapat dijalankan di berbagai lingkungan dengan mudah. | Kurang portabel, karena VM tergantung pada hypervisor dan konfigurasi hardware. |
| Contoh Teknologi    | Docker, Kubernetes, Podman.            | VMware, Hyper-V, KVM, VirtualBox.        |

# B. Perbedaan Multiprogramming dan Multitasking

## a) Multiprogramming

> **Multiprogramming** adalah teknik di mana beberapa program dimuat ke dalam memori utama (RAM) secara bersamaan, tetapi hanya satu program yang dijalankan oleh CPU pada satu waktu. Tujuan utama multiprogramming adalah **meningkatkan utilisasi CPU** dengan memastikan bahwa CPU selalu memiliki pekerjaan untuk dilakukan, bahkan ketika satu program sedang menunggu operasi I/O (seperti membaca dari disk atau menunggu input pengguna).

## b) Multitasking

> **Multitasking** adalah teknik di mana beberapa tugas atau proses dijalankan secara bersamaan dengan membagi waktu CPU (time-sharing). Tujuan utama multitasking adalah **meningkatkan responsivitas sistem** dan memberikan ilusi bahwa beberapa program berjalan secara bersamaan, meskipun sebenarnya CPU hanya menjalankan satu tugas pada satu waktu.

# C. Fungsi OS

- **User Interface**: Semua sistem operasi memiliki User Interface seperti GUI, CLI, touch-screen, Batch.
- **Program Execution**: Program harus bisa memuat file, menjalankan, mengeksekusi, secara normal.
- **Operasi I/O**: Menjalankan program mungkin membutuhkan I/O dari user ataupun dari device.
- **Manipulasi File Sistem**: Program membutuhkan untuk membaca, menulis, membuat, dan menghapus gambar, list informasi file, dan manajemen permission.
- **Komunikasi Proses**: Mungkin membutuhkan pertukaran informasi pada satu komputer atau berbeda komputer.
- **Deteksi Error**: Sistem operasi terkadang terdapat kesalahan dan membutuhkan pendeteksinya.
- **Alokasi Sumber Daya**: Ketika beberapa user atau pekerjaan dijalankan secara bersamaan, maka sumber daya harus dialokasikan di setiapnya.
- **Protection Security**: Ketika bekerja menggunakan internet membutuhkan keamanan dan sistem operasi menyediakan itu.
