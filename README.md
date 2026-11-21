# Keuangan Keluarga: APK lewat GitHub

Repo ini membangun APK Android dari `index.html` memakai GitHub Actions (Capacitor). Tidak perlu Android Studio.

## Langkah
1. Buat repository baru di GitHub (public atau private).
2. **Dari komputer:** ekstrak zip ini, lalu di GitHub pilih Add file > Upload files dan seret SEMUA isi folder, termasuk folder `.github`. Commit ke branch `main`.
3. **Dari HP:** unggah `index.html`, `icon.png`, `package.json`, `capacitor.config.json` lewat Upload files. Lalu Add file > Create new file, ketik nama `.github/workflows/build-apk.yml` dan tempel isi file itu dari zip.
4. Buka tab **Actions**. Workflow "Build APK" jalan otomatis (atau Run workflow). Tunggu sekitar 5 sampai 10 menit sampai ada tanda centang hijau.
5. Buka run yang berhasil, bagian **Artifacts**, unduh `keuangan-keluarga-apk`. Ekstrak, di dalamnya ada `app-debug.apk`.
6. Pasang APK di HP (izinkan "Instal dari sumber tidak dikenal").

## Lisensi (trial 15 hari + kode admin)
- Aplikasi gratis dicoba 15 hari, lalu terkunci sampai diisi kode aktivasi 10 karakter (huruf dan angka).
- Pengguna melihat **ID Perangkat** di layar kunci atau tab Data > Lisensi, lalu mengirimnya ke admin.
- Admin membuat kode dengan file `admin-generator-kode.html` (file terpisah, RAHASIA, jangan diunggah ke GitHub). Kode hanya berlaku untuk satu perangkat.
- Pengaturan ada di bagian atas script `index.html`: `LIC_S` (kunci rahasia, harus sama dengan di file admin), `TRIAL` (lama trial), `ADMIN_WA` (nomor WhatsApp admin, format 628xxx, untuk tombol kirim ID di versi web).
- Ini pengaman dasar yang berjalan di perangkat. Pengguna yang menghapus data aplikasi akan mendapat trial baru, dan orang yang mahir bisa membongkar kode. Untuk perlindungan penuh perlu verifikasi lewat server.

## Catatan
- Ini APK debug, cukup untuk pemakaian pribadi. Play Store perlu APK/AAB release yang ditandatangani.
- Untuk memperbarui aplikasi, ganti `index.html` di repo. APK baru otomatis dibangun.
- Di APK, tombol backup, Excel, dan bagikan membuka menu bagikan Android.
- Jika build gagal, salin pesan error dari langkah yang gagal dan kirim ke Claude.
