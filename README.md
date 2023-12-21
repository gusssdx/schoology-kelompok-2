![](https://images.squarespace-cdn.com/content/v1/5cb36dc993a63270cfacbc2b/1568407625291-IZ079BSO4AO5K6YIM0PD/ke17ZwdGBToddI8pDm48kC9qu2gvgDc1fHZgGjPXHQ5Zw-zPPgdn4jUwVcJE1ZvWEtT5uBSRWt4vQZAgTJucoTqqXjS3CfNDSuuf31e0tVGsbjzQe8XprMihMEQ9UKdMwALN5jbWCRaeUKHWJatMjmVWdNHs25RwszbEzjDCTQI/Schoology?format=1000w)

# Welcome to my Schoology Kelompok 2
Anggota Kekompok
- Irwan Sadar Anugrah Zega (2210511014)
- Bagus Tri Handoko (2210511025)
- Muhammad Dihya Al Qalby (2210511035)
- Muhammad Azkal Azkia 	(2210511038)


## Prerequisites
harap install `yarn` di environment. untuk install gunakan perintah
```
npm install --global yarn
```
harap install `nodejs` di environment juga. untuk install gunakan perintah
```
npm install --global nodejs
```
 diperlukan juga beberapa alat baris perintah (CLI tools) berikut: `docker` dan `docker-compose` agar semuanya berjalan dengan baik.

## Steps to get the App running
### Tahap pertama
Download source code menggunakan perintah git clone, dengan perintah berikut
```
git clone https://github.com/DanZeuss/schoology.git
```
Ini akan mendownload semua source code didalam folder `schoology`.
### Tahap kedua
Sebelum memulai proses , Pastikan tidak ada layanan yang berjalan di port `3000` (Node), `6379` (Redis), dan `27017` (MongoDB). Sekarang pindah ke folder `schoology` dengan menjalankan perintah `cd schoology/` dan kemudian mulai proses pembangunan dengan menjalankan perintah berikut:
```
yarn build
```
Proses `pembangunan` akan berlangsung sesuai dengan langkah-langkah berikut:
- Menginstal semua dependensi untuk membangun dan mendeploy versi teroptimalkan dari build front-end untuk produksi;
- Menginstal semua dependensi untuk membangun dan mendeploy paket server untuk produksi;
- Mengunduh dan membangun semua kontainer untuk aplikasi. Aplikasi ini menggunakan `MongoDB` sebagai database dan `Redis` untuk caching guna mempercepat respon API;
- Memindahkan semua file konfigurasi ke dalam kontainer;
- Mengisi data palsu ke dalam `MongoDB`.

Jika semuanya berjalan dengan baik, sekarang Anda dapat mengakses `app` dengan membuka URL berikut di browser Anda: `http://localhost:3000`. Anda akan memiliki akses ke halaman utama. Bilah pencarian mencari kursus dengan menggunakan teknik `lazy search`. Jadi, Anda dapat mencari berdasarkan karakter yang ada dalam kata, tanpa menuliskannya dengan benar. Browser hanya akan membuat permintaan setelah pengguna berhenti mengetik selama 400ms. Pendekatan lain yang diambil adalah dengan menggunakan `Redis` untuk menyimpan data yang telah dicari sebelumnya untuk meningkatkan kinerja `app`.
![](https://i.ibb.co/qswbJjh/Kapture-2019-12-18-at-3-19-48.gif)



# Dev environment
Untuk memulai lingkungan develpment, harus mengaktifkan kontainer `MongoDB` dan `Redis` . untuk itu harus menjalankan perintah:
```
docker-compose up -d db redis
```
Anda juga perlu memulai aplikasi web dengan menjalankan perintah berikut di direktori utama:
```
yarn startreload
```
Untuk dapat bekerja pada bagian front-end, Anda perlu melakukan sesuatu yang lain. Silakan akses folder `app` dan kemudian jalankan `yarn start` untuk memulai hotreload dan server untuk file statis.

# Menambahkan Logo UPNVJ
Untuk menambahkan logo UPNVJ anda harus mendownload logo terlebih dahulu lalu memasukkannya di folder `public` yang ada di direktori `app`.
Setelah itu masuk ke kedalam file `index.html` dan edit file tersebut pada bagian tag `body` dengan menambahkan kode berikut untuk memasukkan logo UPNVJ kedalam web Schoology :
<img width="646" alt="image" src="https://github.com/gusssdx/schoology-kelompok-2/assets/117824843/0cbcc2a7-15be-40b1-8a64-c9d8f2972431">

Setelah itu jalankan perintah `yarn start` di direktori `app`, lalu masuk ke link localhost yang diberikan, dan logo UPNVJ telah dimasukkan ke dalam web Schoology
<img width="957" alt="Cuplikan layar 2023-12-07 141847" src="https://github.com/gusssdx/schoology-kelompok-2/assets/117824843/45f13873-1974-468a-ad6f-d0c398d1caad">
