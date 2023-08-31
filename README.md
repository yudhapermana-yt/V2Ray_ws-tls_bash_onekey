## Skrip penginstalan satu-klik vmess+ws+tls berbasis V2Ray Nginx Translate Bahasa Indonesia

> Terima kasih kepada JetBrains atas lisensi pengembangan perangkat lunak sumber terbuka non-komersial.

> Thanks for non-commercial open source development authorization by JetBrains
### Tentang Mekanisme Penghapusan Pesan Otentikasi VMess MD5
> Mulai 1 Januari 2022, kompatibilitas sisi server dengan pesan autentikasi MD5 akan dinonaktifkan secara default. Klien mana pun yang menggunakan pesan autentikasi MD5 tidak akan dapat menyambung ke server dengan pesan autentikasi MD5 VMess yang dinonaktifkan.

Pengguna yang terkena dampak sangat disarankan untuk menginstal ulang dan mengatur alterid ke 0 (nilai default sekarang telah diubah menjadi 0) dan tidak lagi menggunakan mekanisme autentikasi VMess MD5!
Jika Anda tidak ingin menginstal ulang, Anda dapat memaksa kompatibilitas dengan mekanisme autentikasi MD5 untuk diaktifkan dengan menggunakan https://github.com/KukiSa/VMess-fAEAD-disable.

### Grup Telegram
* grup pertukaran telegram: https://t.me/wulabing_v2ray 
* saluran pengumuman pembaruan telegram: https://t.me/wulabing_channel

### Persiapan
* Siapkan nama domain dan tambahkan catatan A atau AAA ke dalamnya.
* [Petunjuk resmi V2ray] (https://www.v2ray.com/) untuk informasi terkait TLS WebSocket dan V2ray
* Instal wget.

### Metode instalasi/pembaruan (versi h2 dan ws telah digabungkan)
VMESS + soket web + TLS + Nginx + Situs web
```
wget -N --no-check-certificate -q -O install.sh "https://raw.githubusercontent.com/yudhapermana-yt/V2Ray_ws-tls_bash_onekey/master/install.sh" && chmod +x install.sh && bash install.sh
```

VLESS + soket web + TLS + Nginx + Situs web
```
wget -N --no-check-certificate -q -O install.sh "https://raw.githubusercontent.com/wulabing/V2Ray_ws-tls_bash_onekey/dev/install.sh" && chmod +x install.sh && bash install.sh
```

### Catatan
* Jika Anda tidak memahami arti spesifik dari pengaturan dalam skrip, kecuali untuk nama domain, silakan gunakan nilai default yang disediakan oleh skrip.
* Untuk menggunakan skrip ini, Anda harus memiliki dasar Linux dan pengalaman, memahami bagian jaringan komputer dari pengetahuan, operasi dasar komputer.
* Saat ini mendukung Debian 9+ / Ubuntu 18.04+ / Centos7+, beberapa templat Centos mungkin sulit untuk menangani masalah kompilasi, disarankan agar ketika Anda mengalami masalah kompilasi, harap ganti templat ke sistem lain.
* Pemilik grup hanya menyediakan dukungan yang sangat terbatas, jika Anda memiliki pertanyaan, silakan tanyakan kepada teman Anda.
* Setiap hari Minggu pukul 3:00 pagi, Nginx akan memulai ulang secara otomatis untuk bekerja sama dengan tugas pengatur waktu penerbitan sertifikat, selama periode ini, node tidak dapat terhubung secara normal, durasi yang diharapkan adalah beberapa detik hingga dua menit.

### Perbarui Log
> Lihat CHANGELOG.md untuk pembaruan.

### Ucapan Terima Kasih
* ~~本脚本的另一个分支版本（Use Host）地址： https://github.com/dylanbai8/V2Ray_ws-tls_Website_onekey 请根据需求进行选择~~ Penulis ini mungkin telah berhenti memelihara
* Versi MTProxy-go TLS dari skrip ini direferensikan di proyek https://github.com/whunt1/onekeymakemtg dengan ucapan terima kasih kepada whunt1.
* Proyek skrip Riptide 4-in-1 asli dalam skrip ini direferensikan di https://www.94ish.me/1635.html dengan ucapan terima kasih.
* Versi modifikasi dari skrip Riptide 4-in-1 dalam skrip ini direferensikan di https://github.com/ylx2016/Linux-NetSpeed Terima kasih kepada ylx2016.

### Sertifikat
> Jika Anda sudah memiliki file sertifikat dari nama domain yang Anda gunakan, Anda dapat menamai file crt dan key sebagai v2ray.crt v2ray.key dan meletakkannya di direktori /data (jika direktori tidak ada, buat direktori terlebih dahulu), harap perhatikan izin file sertifikat dan validitas sertifikat, dan perbarui sertifikat sendiri saat masa berlaku sertifikat khusus berakhir.

Skrip ini mendukung pembuatan otomatis sertifikat terenkripsi Let's Encrypted dengan masa berlaku 3 bulan, dan secara teoritis sertifikat yang dibuat secara otomatis mendukung pembaruan otomatis.

### Melihat konfigurasi klien
`cat ~/v2ray_info.txt`

### Pengenalan ke V2ray

* V2Ray adalah alat proxy jaringan open source yang sangat baik yang dapat membantu Anda menikmati Internet dengan lancar, dan saat ini memiliki dukungan platform penuh untuk Windows, Mac, Android, iOS, Linux, dan sistem operasi lain untuk digunakan.
* Skrip ini adalah skrip yang dapat dikonfigurasi sepenuhnya dengan sekali klik, setelah semua proses berjalan normal, langsung sesuai dengan hasil keluaran dari pengaturan klien dapat digunakan
* Harap diperhatikan: Kami tetap sangat menyarankan agar Anda memahami sepenuhnya alur kerja dan prinsip-prinsip dari keseluruhan program ini!

### Direkomendasikan untuk menyiapkan hanya satu proxy untuk satu server.
* Skrip ini menginstal versi terbaru V2ray core secara default.
* Versi terbaru V2ray core adalah 4.22.1 (harap perhatikan pembaruan sinkron dari core sisi klien, Anda harus memastikan bahwa versi kernel sisi klien >= versi kernel sisi server)
* Direkomendasikan untuk menggunakan port default 443 sebagai port koneksi
* Konten kamuflase dapat diganti.

### Catatan
* Direkomendasikan untuk menggunakan skrip ini di lingkungan yang murni. Jika Anda baru mengenal Centos, jangan gunakan skrip ini.
* Jangan gunakan skrip ini di lingkungan produksi hingga Anda mencobanya.
* Pengguna yang telah menginstal Nginx menggunakan [LNMP] (https://lnmp.org) atau skrip pembawa Nginx serupa lainnya harus memberikan perhatian khusus pada fakta bahwa penggunaan skrip ini dapat menyebabkan bug yang tidak dapat diprediksi (belum teruji, tetapi jika sudah teruji, rilis berikutnya dapat menangani masalah ini).
* Bagian dari fungsionalitas V2Ray bergantung pada waktu sistem, pastikan bahwa waktu UTC dari sistem tempat Anda menggunakan aplikasi V2RAY dalam waktu tiga menit dari kesalahan, zona waktu tidak relevan.
* Bash ini bergantung pada [skrip instalasi resmi V2RAY] (https://install.direct/go.sh) dan [acme.sh] (https://github.com/Neilpang/acme.sh) agar dapat bekerja.
* Untuk pengguna Centos, silakan lepaskan port yang relevan di firewall Anda (default: 80, 443).


### Metode memulai

mulai V2ray：`systemctl start v2ray`

stop V2ray：`systemctl stop v2ray`

mulai Nginx：`systemctl start nginx`

stop Nginx：`systemctl stop nginx`

### Katalog terkait

Web direktori：`/home/wwwroot/3DCEList`

V2ray Konfigurasi Server：`/etc/v2ray/config.json`

V2ray Konfigurasi Klien: `~/v2ray_info.inf`

Nginx direktori： `/etc/nginx`

Dokumen untuk sertifikat: `/data/v2ray.key 和 /data/v2ray.crt` Harap perhatikan pengaturan otoritas sertifikat

### Donasi

Anda bisa membeli VPS dengan Mover AFF saya!

https://bandwagonhost.com/aff.php?aff=63939

Anda dapat menggunakan justmysocks AFF saya untuk membeli proksi yang disediakan oleh pemindah ubin!

https://justmysocks.net/members/aff.php?aff=17621




