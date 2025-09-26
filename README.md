Aplikasi CRUD Kabupaten di Indonesia
1. Deskripsi
Aplikasi ini merupakan sistem sederhana untuk mengelola data kabupaten di Indonesia menggunakan Java Swing sebagai antarmuka pengguna (GUI) dan PostgreSQL sebagai basis data.
Fitur utama meliputi:
- Menampilkan daftar kabupaten.
- Menambahkan data kabupaten baru.
- Mengubah data kabupaten yang sudah ada.
- Menghapus data kabupaten.
Aplikasi menggunakan JFrame sebagai jendela utama dan JDialog untuk form input atau konfirmasi, sehingga interaksi dengan pengguna lebih mudah dan terstruktur.

2. Struktur Kode
GUIMainClass.java
- JFrame utama aplikasi.
- Menampilkan tabel kabupaten (JTable) dan tombol Insert, Update, dan Delete.
- Mengatur aksi tombol untuk menambahkan, memperbarui, atau menghapus data.
InsertData.java
- JDialog untuk menambahkan data kabupaten baru.
- Memvalidasi input (tidak boleh kosong, luas wilayah harus desimal, jumlah penduduk harus bilangan bulat).
- Mengirim data kembali ke GUIMainClass untuk disimpan di database.
UpdateData.java
- JDialog untuk memperbarui data kabupaten yang dipilih di tabel.
- Menyediakan getter untuk mengambil data hasil edit.
- Mengirimkan data kembali ke GUIMainClass untuk diupdate di database.
DeleteData.java
- JDialog untuk konfirmasi penghapusan data kabupaten.
- Menghapus data berdasarkan kode_bps jika dikonfirmasi pengguna.
KoneksiDB.java
- Mengatur koneksi ke PostgreSQL.
- Database: db_dialogmodal
- User: postgres
- Password: ABCDE12345VWXYZ
Alur Kerja Aplikasi
- Menampilkan Data
Saat GUIMainClass dibuka, tabel akan langsung menampilkan data dari database.
- Menambah Data
Klik tombol Insert → muncul InsertData → isi form → klik Simpan → data tersimpan di database dan tabel di-refresh.
- Mengubah Data
Pilih baris pada tabel → klik Update → muncul UpdateData → ubah data → klik Simpan → data di-update di database.
- Menghapus Data
Pilih baris pada tabel → klik Delete → muncul konfirmasi → klik Ya → data dihapus dari database.
Validasi Input
- Semua field wajib diisi.
- Luas wilayah harus berupa angka desimal (contoh: 1234.56).
- Jumlah penduduk harus berupa bilangan bulat (contoh: 1000000).

Catatan Teknis
- Koneksi database menggunakan JDBC PostgreSQL Driver (org.postgresql.Driver).
- Gunakan PostgreSQL versi terbaru dan pastikan database db_dialogmodal sudah dibuat beserta tabel kabupaten dengan kolom:
1. kode_bps (VARCHAR)
2. nama_kabupaten (VARCHAR)
3. pusat_pemerintahan (VARCHAR)
4. luas_wilayah (DOUBLE)
5. jumlah_penduduk (INTEGER)
- Gunakan Java SE 8+ atau NetBeans untuk menjalankan proyek ini.

Cara Menjalankan
- Pastikan PostgreSQL aktif dan database sudah ada.
- Buka proyek di NetBeans.
- Jalankan GUIMainClass.java.
- Gunakan tombol Insert, Update, dan Delete untuk mengelola data.
