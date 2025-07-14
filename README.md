Deskripsi Singkat: Sistem informasi pendaftaran sidang praktek kerja lapangan dan sidang tugas akhir berguna untuk mahasiswa, Admin Jurusan, dan Dosen yang terlibat (Kepala Jurusan dan Kepala Prodi) Jurusan Administrasi Niaga yang mengajar di Politeknik Negeri Padang. Sistem ini memudahkan pengguna, untuk menginputkan persyaratan kemudian verfikasi berkas secara sistematis.

Third-Party / library yang digunakan: 

1. Dependensi PHP (Wajib untuk Produksi & Pengembangan):

PHP: Versi ^8.2 (ini adalah persyaratan versi PHP minimum).

laravel/framework: Versi ^12.0 (core framework Laravel).

laravel/sanctum: Versi ^4.1 (untuk otentikasi API dan SPA).

laravel/tinker: Versi ^2.10.1 (untuk interaksi konsol dengan aplikasi).

maatwebsite/excel: Versi ^3.1 (untuk mengelola impor/ekspor file Excel dan CSV).


2. Dependensi Pengembangan (Hanya untuk Pengembangan & Pengujian):

fakerphp/faker: Versi ^1.23 (untuk menghasilkan data dummy).

laravel/pail: Versi ^1.2.2 (untuk melihat log real-time di terminal).

laravel/pint: Versi ^1.13 (untuk memperbaiki gaya kode PHP).

laravel/sail: Versi ^1.41 (untuk lingkungan pengembangan Docker).

mockery/mockery: Versi ^1.6 (untuk mocking dalam pengujian).

nunomaduro/collision: Versi ^8.6 (untuk laporan error yang lebih baik di konsol).

phpunit/phpunit: Versi ^11.5.3 (framework pengujian unit).


3. Skrip Composer yang Terkait dengan Dependensi/Proses:

Meskipun bukan dependensi langsung, script ini adalah bagian integral dari bagaimana dependensi digunakan dan bagaimana project diatur:

post-autoload-dump: Menjalankan Illuminate\Foundation\ComposerScripts::postAutoloadDump dan @php artisan package:discover --ansi.

post-update-cmd: Menjalankan @php artisan vendor:publish --tag=laravel-assets --ansi --force.

post-root-package-install: Menyalin .env.example ke .env jika belum ada.

post-create-project-cmd: Menghasilkan kunci aplikasi, membuat database.sqlite (jika tidak ada), dan menjalankan migrasi awal.

dev: Perintah kompleks untuk menjalankan server, queue listener, pail, dan proses npm run dev secara bersamaan.

test: Menjalankan @php artisan config:clear --ansi dan @php artisan test untuk pengujian.

Langkah Instalasi:

Langkah 1: Instal Dependensi PHP
Buka terminal atau Command Prompt Anda, arahkan ke folder root project Laravel (tempat file composer.json berada), lalu jalankan perintah berikut:

composer install

Perintah ini akan membaca daftar dependensi dari file composer.json dan mengunduh semua library yang diperlukan ke dalam folder vendor.

Langkah 2: Duplikat File Konfigurasi Lingkungan
Laravel menggunakan file .env untuk menyimpan konfigurasi sensitif seperti kredensial database dan kunci aplikasi. File ini biasanya tidak disertakan di repository Git. Anda harus membuatnya sendiri dari contoh yang sudah disediakan.

Jalankan perintah ini di terminal:


cp .env.example .env
Jika Anda menggunakan Windows, Anda bisa menggunakan perintah copy:

copy .env.example .env

Langkah 3: Hasilkan Kunci Aplikasi (Application Key)
Kunci aplikasi adalah string acak yang digunakan untuk mengenkripsi sesi dan data lainnya. Ini sangat penting untuk keamanan. Laravel memiliki perintah khusus untuk membuat kunci ini.

Jalankan perintah berikut di terminal:

php artisan key:generate

Perintah ini akan secara otomatis memperbarui file .env dengan kunci aplikasi yang baru.

Langkah 4: Konfigurasi Database
Setelah kunci aplikasi dibuat, sekarang saatnya untuk mengkonfigurasi koneksi ke database Anda.

Buat Database: Secara manual buat sebuah database kosong baru di server database Anda (misalnya menggunakan phpMyAdmin, MySQL Workbench, atau HeidiSQL) dengan nama yang Anda inginkan (misalnya nama_project_anda).

Edit File .env: Buka file .env dan sesuaikan baris-baris berikut dengan detail database yang baru saja Anda buat:

Ini, TOML

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=nama_database_anda
DB_USERNAME=username_database_anda
DB_PASSWORD=password_database_anda
Ganti nama_database_anda, username_database_anda, dan password_database_anda dengan informasi yang sesuai.

Langkah 5: Jalankan Migrasi Database
Migrasi adalah cara Laravel untuk mengelola struktur database. Setelah Anda mengkonfigurasi .env, Anda dapat menjalankan semua migrasi yang ada di project.

Jalankan perintah ini:

php artisan migrate
Perintah ini akan membuat semua tabel yang didefinisikan dalam folder database/migrations di database Anda.

Jika project ini memiliki data awal (seeder), Anda bisa menjalankannya bersamaan dengan migrasi:

php artisan migrate --seed

Langkah 6: Jalankan Aplikasi
Sekarang, semuanya sudah siap! Jalankan server pengembangan bawaan Laravel dengan perintah:

php artisan serve

Server akan mulai berjalan, dan Anda bisa mengakses project Anda di web browser dengan membuka alamat http://127.0.0.1:8000 (atau port yang tertera di terminal).

Selamat! Project Laravel Anda sekarang sudah terinstal dan bisa Anda jalankan.

Akun Untuk Akses Login:

1. Admin
   * Email: admin@example.com
   * Nama: Admin
   * Password: 12345678


  2. Dosen
   * Email: ilham@example.com
       * Nama: Ilham Widajaya
       * NIDN: 1234567890
       * Prodi: Rekayasa Perangkat Lunak
       * Jenis Kelamin: Laki-laki
       * Password: password123
   * Email: andrew@example.com
       * Nama: Andrew Diantara
       * NIDN: 0987654321
       * Prodi: Rekayasa Perangkat Lunak
       * Jenis Kelamin: Laki-laki
       * Password: password123
   * Email: dimas@example.com
       * Nama: Dimas Prasetyo
       * NIDN: 1122334455
       * Prodi: Teknik Komputer
       * Jenis Kelamin: Laki-laki
       * Password: password123
   * Email: andi.wijaya@example.com
       * Nama: Prof. Dr. Andi Wijaya
       * NIDN: 197001012000011001
       * Prodi: Rekayasa Perangkat Lunak
       * Jenis Kelamin: Laki-laki
       * Password: password123
   * Email: budi.santoso@example.com
       * Nama: Dr. Budi Santoso
       * NIDN: 198005102005021002
       * Prodi: Teknik Komputer
       * Jenis Kelamin: Laki-laki
       * Password: password123
   * Email: citra.dewi@example.com
       * Nama: Dra. Citra Dewi, M.Kom
       * NIDN: 197511202002032003
       * Prodi: Rekayasa Perangkat Lunak
       * Jenis Kelamin: Perempuan
       * Password: password123
   * Email: Rayhan.dwiwata@example.com
       * Nama: Dra. Rayhan Dwiwata Putra, M.Kom
       * NIDN: 197511202002032004
       * Prodi: Teknik Komputer
       * Jenis Kelamin: Laki-Laki
       * Password: password123


  3. Mahasiswa
   * Email: arlan@example.com
       * Nama: Arlan Diana
       * NIM: 2311082011
       * Prodi: Rekayasa Perangkat Lunak
       * Jenis Kelamin: Perempuan
       * Kelas: TI-1
       * Password: 12345678

  4. Kaprodi
   * Email: kaprodi@example.com
   * Nama: Kaprodi
   * Password: 12345678


  5. Kajur
   * Email: kajur@example.com
   * Nama: Kajur
   * Password: 12345678

Link Demo:https://drive.google.com/drive/folders/1x5mIF5n-4iZggfZpttyqJ7O3J4BVwux7?usp=sharing
