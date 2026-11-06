# Maverick POS Fuel — PWA Android

PWA kasir dan pencatatan BBM. Dapat dipasang dari Chrome Android setelah file di-host pada alamat HTTPS.

## Isi paket
- `index.html`: antarmuka responsif.
- `app.js`: logika transaksi, tangki, stok masuk, laporan, backup dan restore.
- `manifest.webmanifest`: metadata instalasi PWA.
- `sw.js`: cache aset agar aplikasi dapat dibuka offline setelah kunjungan pertama.
- `icon-192.png` dan `icon-512.png`: ikon aplikasi.

## Cara termudah tanpa laptop: hosting melalui GitHub dari HP
1. Buka Chrome Android dan masuk ke https://github.com. Buat akun atau login.
2. Buat repository baru bernama `maverick-pos-fuel`. Pilih Public dan buat repository.
3. Pada repository, pilih **Add file → Upload files**.
4. Unggah semua file di dalam folder hasil ekstrak ZIP ini (bukan folder ZIP-nya). Pastikan `index.html`, `app.js`, `manifest.webmanifest`, `sw.js`, `icon-192.png`, dan `icon-512.png` berada di root repository.
5. Tekan **Commit changes**.
6. Buka **Settings → Pages**.
7. Pada **Build and deployment**, pilih **Deploy from a branch**, branch `main`, folder `/ (root)`, lalu **Save**.
8. Tunggu proses publikasi. URL biasanya berbentuk `https://USERNAME.github.io/maverick-pos-fuel/`.
9. Buka URL tersebut melalui Chrome Android. Tunggu aplikasi termuat. Pilih tombol **Pasang aplikasi** jika muncul. Jika tidak, buka menu Chrome (⋮) → **Instal aplikasi** atau **Tambahkan ke layar utama**.
10. Setelah dibuka pertama kali dengan internet, service worker menyimpan aset agar halaman bisa dibuka offline.

## Cara memasang lewat HP dengan layanan hosting lain
Anda dapat memakai layanan static hosting yang menerima unggahan file/folder dan menyediakan HTTPS. Unggah seluruh isi folder ini dan gunakan URL HTTPS yang diberikan, kemudian lakukan langkah instalasi Chrome pada langkah 9.

## Fitur
- Dashboard stok per tangki, kapasitas, level visual, persentase dan peringatan minimum.
- Multi-jenis BBM.
- Kasir input liter atau rupiah, hitung volume, total, pembayaran dan kembalian.
- Validasi stok dan pengurangan stok otomatis saat transaksi.
- Stok masuk dengan validasi kapasitas tangki.
- Riwayat transaksi dan pengisian.
- Cetak/simpan struk melalui dialog cetak browser.
- Laporan omzet, liter, laba kotor, dan rekap per jenis BBM.
- Ekspor dan impor cadangan JSON.
- Penyimpanan lokal browser dan cache offline.

## Catatan penting
- PWA harus disajikan melalui HTTPS agar service worker dan instalasi PWA aktif. Membuka file `index.html` langsung dari penyimpanan HP tidak cukup.
- Data transaksi tersimpan pada browser/perangkat yang digunakan. Data tidak otomatis tersinkron ke HP lain. Jangan hapus data situs/browser sebelum mengekspor backup JSON.
- Offline berarti aplikasi dapat dibuka dan digunakan setelah aset berhasil dicache. Fitur cetak dan beberapa kemampuan sistem Android dapat bergantung pada browser/perangkat.
- Angka stok adalah pencatatan manual, bukan pembacaan sensor tangki, ATG, dispenser, atau flow meter.
- Laba yang ditampilkan adalah estimasi laba kotor, belum termasuk biaya operasional, pajak, susut/selisih ukur, dan biaya lain.
- Data awal Pertalite, Pertamax, Solar, harga, kapasitas, dan stok hanyalah contoh. Ganti sesuai data usaha dan ketentuan yang berlaku sebelum operasional.
- Versi ini belum memiliki akun operator, sinkronisasi cloud, integrasi dispenser, EDC/payment gateway, maupun backup otomatis.
