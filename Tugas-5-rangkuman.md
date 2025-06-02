# Sejarah Perkembangan Sistem Operasi

## Early System (Sebelum 1940-an)
- Komputer dirancang untuk tugas tetap.
- **Alan Turing** dan **John von Neumann** mengembangkan konsep komputer dengan penyimpanan program.
- Perkembangan perangkat keras dan lunak termasuk driver dan compiler (FORTRAN, COBOL).
- Sistem awal memerlukan langkah manual → waktu idle CPU tinggi.
- Solusi: 
  - Sistem batch dengan monitor residen.
  - Penggunaan pita magnetik dan disk.
  - Teknologi **spooling** untuk paralelisasi CPU-I/O.

---

## Atlas (1950-an)
- Dikembangkan di Universitas Manchester.
- Sistem operasi batch dengan **spooling**.
- Fitur unggulan: **Manajemen memori** menggunakan drum (98 KB) dan inti (16 KB).
- Memori dibagi menjadi halaman 512-word.
- Algoritma pengganti halaman dengan 1 frame kosong untuk transfer drum.

---

## XDS-940 (1960-an)
- Dikembangkan di Universitas California.
- Menggunakan **paging** untuk realokasi (bukan demand paging).
- Modifikasi dari XDS-930 dengan tambahan mode monitor pengguna.
- Instruksi khusus untuk I/O dan manajemen sumber daya (file, proses).

---

## THE (1960-an)
- Sistem batch di Belanda (komputer EL X8, 32 KB memori).
- Proses statis dengan sinkronisasi **semaphore**.
- Penjadwalan berbasis prioritas (prioritas tinggi untuk I/O).
- Paging perangkat lunak + bahasa Algol.
- Algoritma **bankir** untuk deadlock avoidance.

---

## RC4000 (1960-an)
- Dirancang untuk komputer Denmark RC4000.
- **Kernel modular** dengan struktur berlapis.
- Penjadwalan **round-robin** untuk proses konkuren.

---

## CTSS (1961)
- Sistem **time-sharing** pertama (MIT, IBM 7090).
- Dukung 32 pengguna interaktif.
- Penjadwalan: **antrean umpan balik bertingkat** (kuantum waktu = 2^I unit).

---

## MULTICS (1965-1970)
- Dikembangkan MIT dengan alamat virtual 18-bit segmen + 16-bit offset.
- Halaman 1 KB + penjadwalan umpan balik bertingkat.
- Dukungan **multi-prosesor**.

---

## IBM OS/360 (1960-an)
- Keluarga OS untuk berbagai mesin IBM.
- Dua versi:
  - **OS/MFT**: Wilayah memori tetap.
  - **OS/MVT**: Wilayah memori variabel.
- Masalah: estimasi ukuran output manual + relokasi statis.

---

## TOPS-20 (1970-an)
- Evolusi dari TENEX (DEC PDP-10).
- Tambahan **paging memori virtual**.
- Dijual sebagai DECSYSTEM-20.

---

## MS-DOS (1981-2000)
- Populer di PC dengan batas memori 640 KB.
- Kelemahan: **tanpa proteksi memori**.

---

## Macintosh & Windows
- **Mac OS**: GUI pertama untuk pengguna rumahan.
- **Windows** (1985): Kompatibel dengan berbagai hardware.
- Fitur baru: memori terlindungi, multitasking.

---

## Mach (1980-an)
- Dikembangkan di Carnegie Mellon University.
- Mikrokernel modular (terpisah dari BSD).
- Dukungan **multiprosesor** + arsitektur berbasis pesan.
- Landasan untuk NeXTSTEP/OS X.

---

## Hydra & CAPS
- **Hydra**: Sistem capability dengan rights amplification.
- **CAPS**: Dua jenis capability (data + software).
- Fokus: keamanan berbasis abstraksi berlapis.
