**PROGRAMMING EXERCISE**

**a.	Penerapan Thread pada contoh SumTask.java**

      Program SumTask.java biasanya menggunakan multithreading untuk menghitung jumlah elemen array secara paralel. 
      Berikut penjelasan implementasi menggunakan divide-and-conquer (misal: dengan ForkJoinPool atau ExecutorService):
      
      Penjelasan Metode compute():
      • Divide: Jika ukuran array > THRESHOLD, bagi menjadi 2 subtask (leftTask dan rightTask).
      • Conquer:
        o fork(): Menjalankan leftTask di thread terpisah.
        o compute(): Menghitung rightTask di thread saat ini.
      • Combine: join() untuk menggabungkan hasil kedua subtask.
      Penjelasan Metode main():
      
        1.	Inisialisasi Array: Membuat array besar (contoh: 10.000 elemen).
        2.	Buat Thread Pool: ForkJoinPool mengelola thread secara otomatis.
        3.	Jalankan Task:
              o	pool.invoke(task): Memulai task utama dan menunggu hasil.
              o	Task akan dipecah secara rekursif oleh compute().  
        4.	Output Hasil: Jumlah total elemen array.
        
            Code
            public class SumTask implements Runnable {
                private int[] array;
                private int start;
                private int end;
                private int sum;
            
                public SumTask(int[] array, int start, int end) {
                    this.array = array;
                    this.start = start;
                    this.end = end;
                }
            
                public int getSum() {
                    return sum;
                }
            
                @Override
                public void run() {
                    sum = 0;
                    for (int i = start; i < end; i++) {
                        sum += array[i];
                    }
                }
            }

**b.	Penerapan thread di Linux (thrd-posix.c)**

    Penerapan thread di Linux biasanya menggunakan POSIX Threads (pthreads) — standar threading API untuk sistem operasi Unix-like, termasuk Linux. 
    Dalam konteks file seperti thrd-posix.c, kita berbicara tentang implementasi abstraksi thread untuk standar C11 dengan membungkus pthread menjadi 
    fungsi-fungsi seperti thrd_create, thrd_join, dan lainnya.File thrd-posix.c umumnya merupakan bagian dari pustaka seperti tinycthread atau implementasi 
    C11 threads untuk sistem non-Windows. Tujuannya adalah membuat kode threading yang portabel dan sesuai standar C11, tetapi menggunakan pthread di balik layar.

Tujuan : 

  1.Menyediakan implementasi thread standar C11 menggunakan POSIX Thread (pthread) di sistem Unix/Linux.
  
  2.Membuat API seperti thrd_create, thrd_join, thrd_exit, mtx_lock, dll., yang kompatibel dengan C11 standard.
  
  3.Membungkus langsung fungsi-fungsi dari pustaka pthread.


**c.	Penerapan Thread  di Microsoft Windows (thrd-win32.c)**

    Penerapan thread di Microsoft Windows, terutama melalui Win32 API, sangat penting dalam mendukung multitasking dan manajemen paralelisme dalam aplikasi. 
    Salah satu sumber kode yang sering dijadikan referensi dalam konteks ini adalah file seperti thrd-win32.c, yang umumnya ditemukan dalam pustaka cross-platform 
    sepertitinycthread, libc11, atau bagian dari C11 thread implementation yang menyediakan abstraction layer untuk thread di berbagai platform, termasuk Windows.
    
    File ini biasanya merupakan bagian dari pustaka thread C11 (seperti tinycthread) yang menyediakan implementasi fungsi-fungsi thread yang sesuai standar C11 (thrd_create, thrd_join, dsb.)
    dengan memanfaatkan API Win32 di Windows.Dengan kata lain, thrd-win32.c mengabstraksikan detail Win32 thread ke dalam fungsi standar C, agar kode C yang menggunakan thread bisa tetap portabel 
    antar sistem operasi.

