# Latihan 5: Kontensi Akses Sumber Daya Bersama dalam Sistem Multitasking

## Deskripsi Proyek
Latihan ini bertujuan untuk memperlihatkan **kontensi akses** pada sumber daya bersama dalam sistem multitasking. Dalam latihan ini, dua tugas (task) yang berjalan secara bersamaan akan saling mengakses sebuah item data yang digunakan bersama tanpa adanya mekanisme perlindungan, sehingga dapat menyebabkan kontensi atau konflik saat kedua tugas mencoba mengakses sumber daya tersebut secara bersamaan.

## Tujuan
- Menunjukkan masalah **kontensi akses** dalam sistem multitasking.
- Mengamati bagaimana interferensi antara tugas yang mengakses sumber daya bersama dapat mempengaruhi konsistensi data.
- Memperkenalkan mekanisme sederhana untuk mendeteksi kontensi akses menggunakan **flag**.

## Komponen Sistem
- **Tugas 1**: Menyalakan LED Hijau, mengakses sumber daya bersama, mematikan LED Hijau, lalu menunggu selama 0,5 detik sebelum memulai kembali.
- **Tugas 2**: Menyalakan LED Merah, mengakses sumber daya bersama, mematikan LED Merah, lalu menunggu selama 0,1 detik sebelum memulai kembali.
- **Sumber Daya Bersama**: Item data yang dapat dibaca dan ditulis oleh kedua tugas.
- **Kontensi Akses**: Jika kedua tugas mencoba mengakses sumber daya pada saat yang bersamaan, LED Biru akan menyala menandakan bahwa kontensi akses terjadi.

## Mekanisme Kontensi Akses
- **Start Flag** digunakan untuk mendeteksi kapan tugas pertama atau kedua dapat mengakses sumber daya bersama.
  - Jika **Start Flag** dalam keadaan "Up", sumber daya dapat diakses.
  - Jika **Start Flag** dalam keadaan "Down", tugas kedua tidak bisa mengakses sumber daya dan LED Biru akan menyala untuk menandakan **kontensi akses**.

## Demo
   (file)

## Kesimpulan
   - Kontensi Akses: Latihan ini menunjukkan bahwa tanpa perlindungan yang memadai (misalnya, semaphore atau mutex), tugas yang berbagi sumber daya bersama dapat menyebabkan gangguan atau kerusakan data.
   - Pentingnya penggunaan mekanisme mutual exclusion (seperti semaphore, mutex, atau critical section) untuk menghindari kontensi akses dalam sistem multitasking.

## Instalasi
   
1. **Clone repositori ini**:
   ```bash
   git clone https://github.com/username/repository.git
2. Buka Proyek di IDE: Pastikan proyek ini dibuka pada IDE yang mendukung pemrograman mikroprosesor dan RTOS, seperti STM32CubeIDE atau Keil uVision.

3. Kompilasi dan Unduh ke Sistem Target:
   Pastikan tugas dijalankan sesuai dengan konfigurasi di atas, perhatikan LED Biru yang menyala untuk menandakan terjadinya kontensi akses.