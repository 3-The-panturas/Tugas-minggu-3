# SIAP(Sistem antrian pasien)
# THE PANTURAS
# Mochammad Akbar_613260014 (Programmer)
# Muhammad Yusuf Abdurrahman_7143260034 (Programmer)
# Mukti Abimanyu H.S_714260022 (perancang flowchart)
# Kayla Fauzia Rahman_613260005 (Desainer Poster)
# Alvin Rizqo Majid_613260015 (Dokumentasi)
# Fikri Widhyadana_714260003 (penguji)
# Tiara Permatasari_714260012 (Editor Video)

# Deskripsi Apilikasi
# SIAP (Sistem Antri Pasien) 
adalah aplikasi berbasis terminal (CLI) yang dibuat dengan python untuk membantu pengelolahan pendaftaran dan antrean pasien rawat jalan di klinik atau rumah sakit. Aplikasi ini memakai menu interaktif dan dibagi menjadi tiga modul:
- main.py berisi menu utama dan alur program.
- fitur.py berisi data dokter dan fitur utama (jadwal, pendaftaran, antrean, pemanggilan).
- utils.py berisi fungsi bantuan seperti validasi input, garis pemisah, dan tampilan judul.

# Masalah yang Diselesaikan
1. Antrean manual yang tidak tertib. Dengan antrean di atas kertas atau sistem "siapa datang duluan", urutan mudah tertukar dan memicu perselisihan. SIAP memberi nomor otomatis yang berurutan sehingga urutan pelayanan jelas dan adil.
2. Informasi jadwal dokter yang sulit diakses.Pasien sering datang tanpa tahu hari dan jam praktik dokter. SIAP menyediakan jadwal yang bisa dilihat langsung sebelum mendaftar.
3. Pendaftaran tanpa syarat yang jelas. Alur pendaftaran memeriksa surat rujukan lebih dulu. Pasien tanpa rujukan diarahkan mengurusnya ke fasilitas kesehatan tingkat pertama, sehingga petugas tidak perlu menolak secara manual.
4. Input data yang tidak valid. Validasi memastikan kolom tidak kosong, umur berupa angka lebih dari 0, dan pilihan menu atau dokter benar. Ini mengurangi kesalahan pencatatan.
5. Status pasien yang tidak terpantau. Setiap pasien punya status ("Menunggu" atau "Sedang diperiksa"), sehingga petugas dan pasien bisa melihat posisi antrean dan siapa yang sedang dilayani.

# FItur
1. Melihat jadwal dokter. Menampilkan nama, spesialis, hari, dan jam praktik semua dokter.
2. Melihat jadwal dokter tertentu. Pasien memilih ID dokter untuk melihat detailnya.
3. Pendaftaran pasien. Mencatat nama, umur, dan nomor HP. Sistem memeriksa surat rujukan, lalu pasien memilih dokter tujuan dan mendapat nomor antrean otomatis (format A-001).
4. Melihat semua antrean. Menampilkan nomor, nama, dokter, dan status setiap pasien.
5. Mencari nomor antrean. Mencari data pasien berdasarkan nomor antrean.
6. Memanggil pasien berikutnya. Memanggil pasien dengan status "Menunggu" sesuai urutan datang, lalu mengubah statusnya menjadi "Sedang diperiksa".

# Cara Penggunaan
Setelah program dijalankan dengan python main.py, tampil menu utama berisi enam fitur dan satu opsi keluar. Pengguna memilih menu dengan mengetik angka lalu menekan ENTER. Setelah setiap fitur selesai, program meminta pengguna menekan ENTER untuk kembali ke menu.
1. Melihat Jadwal Dokter (Menu 1)
- Ketik 1 pada menu utama, lalu tekan ENTER.
- Program menampilkan daftar empat dokter beserta jadwalnya.
- Tekan ENTER untuk kembali ke menu.

2. Melihat Jadwal Dokter Tertentu (Menu 2)
- Ketik 2 pada menu utama.
- Program menampilkan daftar dokter, lalu meminta ID dokter.
- Masukkan ID dokter (1 sampai 4), atau 0 untuk kembali tanpa melihat detail.
- Program menampilkan nama, spesialis, hari, dan jam praktik dokter tersebut.
- Jika ID yang dimasukkan tidak valid, program meminta pengguna mengulang.

3. Pendaftaran Pasien (Menu 3)
- Ketik 3 pada menu utama.
- Isi data pasien secara berurutan:
Nama lengkap (tidak boleh kosong)
Umur (harus angka lebih dari 0)
Nomor HP (tidak boleh kosong)
- Jawab pertanyaan surat rujukan: 1 untuk Ya, 2 untuk Tidak.
Jika memilih 2, program menampilkan pesan agar pasien mengurus rujukan terlebih dahulu, dan pendaftaran dihentikan.
Jika memilih 1, pendaftaran dilanjutkan.
- Program menampilkan jadwal dokter. Masukkan ID dokter tujuan.
- Program menampilkan bukti pendaftaran berupa nama pasien, dokter, nomor antrean (contoh A-001), dan status (Menunggu).

4. Melihat Semua Antrean (Menu 4)
- Ketik 4 pada menu utama.
- Program menampilkan nomor antrean, nama pasien, dokter, dan status setiap pasien.
- Jika belum ada pasien, program menampilkan pesan (Belum ada pasien dalam antrean).

5. Mencari Nomor Antrean (Menu 5)
- Ketik 5 pada menu utama.
- Masukkan nomor antrean lengkap dengan format A-001 (huruf kecil seperti a-001 juga diterima).
- Jika ditemukan, program menampilkan nama pasien, dokter, nomor, dan status.
- Jika tidak ditemukan, program menampilkan pesan (Nomor antrean tidak ditemukan.)
- Jika antrean masih kosong, program langsung menampilkan pesan (Belum ada antrean.)

6. Memanggil Pasien Berikutnya (Menu 6)
- Ketik 6 pada menu utama.
- Program memanggil pasien pertama yang berstatus (Menunggu), menampilkan nomor, nama, dan dokternya.
- Status pasien tersebut berubah menjadi (Sedang diperiksa).
- Jika tidak ada pasien yang menunggu, program menampilkan pesan (Tidak ada pasien yang sedang menunggu.)

7. Keluar (Menu 0)
- Ketik 0 pada menu utama. 
- Program menampilkan pesan terima kasih lalu berhenti. 

# Penjelasan Alur Logika 
1. main.py dijalankan untuk memanggil menu
2. menu berulang dalam loop: menampilkan judul, menu utama, lalu meminta pilihan (divalidasi oleh input_pilihan).
3. pilih fitur apa aja yang ingin digunakan yang udah di tulis dalam fitur.py

# Fungsi Tiap File
1. main.py: fungsinya menampilkan menu utama, meminta pengguna memilih angka untuk menjalankan fitur yang sesuai. Berulang terus sampai pengguna menilih angka 0.
2. fitur.py: fitur ini memiliki 6 fungsu untuk tiap fitur.
    1. tampilkan jadwal: menampilkan jadwal semua dokter.
    2. pilih dokter: menampilkan detail satu doketer berdasarkan ID yang dipilih.
    3. pendaftaran pasien: mendaftarkan pasien, memeriksa surat rujukan, dan memberika nomer antrean. 
    4. lihat antrean: menampilkan semua pasien yang ada di antrean. 
    5. cari antrean: mencari pasien berdasarkan nomer antrean
    6. panggil pasien: memanggil pasien yang menunggu paling awal dan mengubah statusnya menjadi sedang di periksa
3. utils.py: fitur ini memiliki 5 fungsi kecil yang di pakai oleh file lain.
    1. garis: mencetak garis pemisah 
    2. tampilkan judul: mencetak logo "SIAP" di atas menu
    3. jeda: menahan layar sampai pengguna menekan enter 
    4. input wajid: mamastikan kolom terisi tidak boleh kosong
    5. input pilihan: memastikan pilihan pengguna sesuai daftar yang diizinkan

# Petunjuk Menjalankan Program di Komputer Lain
Prasyarat
- Python 3.8 atau lebih baru (unduh di https://www.python.org/downloads/). Di Windows, centang "Add Python to PATH" saat instalasi.
- Git (opsional, untuk cara 1 di bawah). Unduh di https://git-scm.com/downloads.
- Tidak perlu menginstal library tambahan.

Langkah 1: Unduh program
Cara 1 (memakai Git):
```bash
git clone https://github.com/USERNAME/NAMA-REPOSITORY.git
cd NAMA-REPOSITORY
```
Cara 2 (tanpa Git):
1. Buka halaman repository di GitHub.
2. Klik tombol hijau **Code**, lalu pilih **Download ZIP**.
3. Ekstrak file ZIP, lalu buka folder hasil ekstraknya.
Pastikan `main.py`, `fitur.py`, dan `utils.py` berada di folder yang sama.

Langkah 2: Buka terminal di folder program
- Windows: buka folder di File Explorer, klik address bar, ketik `cmd`, lalu tekan ENTER.
- macOS/Linux: klik kanan folder, pilih "Open in Terminal".

Langkah 3: Cek Python
```bash
python --version
```
Di macOS/Linux, gunakan `python3 --version`.

Langkah 4: Jalankan program
```bash
python main.py
```
Di macOS/Linux, gunakan `python3 main.py`.
Menu utama akan tampil. Ketik angka menu, lalu tekan ENTER.

Jika terjadi masalah
1. 'python' is not recognized`Python belum terpasang atau belum masuk PATH Instal ulang Python dan centang "Add Python to PATH".
2. `ModuleNotFoundError: No module named 'utils'` File tidak satu folder, atau terminal dibuka di folder yang salah Pastikan ketiga file satu folder dan terminal dibuka di folder itu.
