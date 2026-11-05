# OmniClock Proyektor - Jam Multifungsi & Ujian 🕒

OmniClock Proyektor adalah aplikasi web jam digital multifungsi berbasis web yang dirancang khusus untuk kebutuhan **layar proyektor, ujian sekolah/kampus, presentasi, dan live streaming (OBS Studio)**.

Dibuat dengan HTML5, Tailwind CSS, dan Vanilla JavaScript murni tanpa ketergantungan server sehingga dapat langsung dijalankan di browser manapun atau dideploy secara gratis ke **GitHub Pages**.

---

## ✨ Fitur Utama

1. **Auto-Hide Header di Mode Fullscreen (Layar Penuh)**
   - Saat masuk ke mode fullscreen (tekan `F`), bilah navigasi atas (header) otomatis tersembunyi.
   - Jam terpusat rapi di tengah layar secara vertikal dan horizontal.
   - Gerakkan kursor ke tepi atas layar (*hover* di atas) untuk memunculkan kembali menu secara mulus.
   - Tombol keluar fullscreen mengambang (*floating exit button*) halus di pojok kanan atas.

2. **Clean Minimalist View saat Fullscreen**
   - Dalam mode fullscreen, tombol pengaturan cepat, slider ukuran, tombol edit, dan toolbar disembunyikan.
   - Hanya menampilkan elemen utama: **Jam Digital**, **Detik** (opsional), **AM/PM**, dan **Tanggal**.
   - Jika Mode Ujian aktif, teks pengumuman berjalan dan peringatan menit terakhir tetap tampil demi kenyamanan peserta ujian.

3. **Pengatur Ukuran Teks Jam (Zoom In / Out)**
   - Perbesar atau perkecil skala jam secara fleksibel mulai dari **50% hingga 250%**.
   - Tombol cepat `A-`, badge persentase (misal `100%`), `A+`, dan tombol `Reset` di bawah jam.
   - Pengaturan slider presisi di menu **Pengaturan (Settings Modal)**.
   - Mendukung hotkey keyboard langsung:
     - Tekan `+` atau `=` : Perbesar ukuran jam (+10%)
     - Tekan `-` atau `_` : Perkecil ukuran jam (-10%)
     - Tekan `0` : Reset ukuran jam ke 100%

4. **Kontrol Transparansi & Mode Overlay OBS**
   - Dropdown kontrol opasitas dengan tombol klik stabil tanpa bug hilang saat kursor digeser.
   - Slider opasitas 0% - 100% dengan tombol preset instan:
     - `0% (Bening)` : Khusus OBS Browser Source / overlay proyektor transparan.
     - `35%` & `70%` : Semi-transparan elegan dengan teks berbayang kontras tinggi.
     - `Solid (100%)` : Latar belakang solid gelap pekat.
   - Pilihan tema: **Deep Dark**, **Pure Black OLED**, dan **Proyektor Overlay**.

5. **Mode Ujian & Peringatan Flash Fleksibel (Flash 1x & Countdown)**
   - Banner teks berjalan (*marquee*) untuk tata tertib ujian yang dapat disunting posisi, ukuran, warna, dan kecepatannya.
   - Pilihan peringatan visual: **Flash 1x** (berkedip satu kali selama 1.2 detik saat menyentuh waktu tertentu) dan **Countdown Flashing** (berkedip terus sampai 00:00).
   - Tombol cepat tambah aturan **+ Flash 1x** di toolbar dan modal, serta tombol uji coba efek flash langsung di layar.
   - Audio bel sintetis (*Web Audio API*) tanpa perlu file MP3 eksternal.

6. **Presisi Milidetik 60 FPS & Mode Tampil/Sembunyi Halus (Semua Mode)**
   - **Tampilan Angka Halus Tanpa Stutter / Loncat**: Milidetik diperbarui dengan tick rate 16ms (~60 FPS) saat aktif, menghasilkan penambahan/pengurangan angka yang mulus dan natural.
   - **Mode Hemat Daya saat Sembunyi**: Saat milidetik disembunyikan, interval otomatis beralih ke mode hemat CPU (250ms - 500ms) tanpa frame drop.
   - **Dukungan Penuh di Semua 5 Mode**: Jam Digital, Stopwatch, Timer, Queue (Antrean), dan Jam Dunia.
   - **Sinkronisasi 100%**: Tombol toolbar `Ms: Tampil` / `Ms: Sembunyi` dan checkbox di menu Pengaturan terhubung secara real-time dan tersimpan di penyimpanan lokal.
   - **Zero Layout Shift**: Tipografi monospace dengan metrik `tabular-nums lining-nums` sehingga angka yang berganti tidak menggeser posisi elemen lain.

7. **Antrean Waktu Bertahap (Queue Timer) Canggih & Fleksibel**
   - **Jadwal Jam Mulai Otomatis (*Scheduled Start Time*)**: Setiap sesi antrean dapat ditentukan waktu mulainya (misal: Sesi 1 mulai jam 04:00, Sesi 2 mulai jam 05:10, atau dikosongkan untuk langsung lanjut). Saat jam mulai belum tiba, antrean otomatis masuk ke status hitung mundur menuju waktu mulai dan membunyikan bel saat sesi resmi dimulai.
   - **Tampilan Jam "Saat Ini" Simetris**: Menampilkan jam digital aktual secara vertikal (atas label "Saat Ini", bawah waktu digital) tepat di tengah-tengah antara sesi selanjutnya dan bagian bawah layar proyektor.
   - **Indikator Cuaca, Suhu & Meteran AQI Penuh**: Di samping jam saat ini, terdapat widget live yang menampilkan nama kota aktual di bagian atas tengah kotak (berbasis *reverse geocoding* lokasi & *timezone*), suhu aktual (°C), kondisi cuaca (Cerah, Berawan, Hujan, dsb.), serta meteran angka AQI berukuran penuh dan tebal dengan status kualitas udara (misal: Baik, Sedang, Tidak Sehat) tepat di bawahnya secara faktual berbasis geolokasi browser.
   - **Kontrol Visibilitas Independen (Jam & Cuaca)**: Tombol ikon jam dan tombol ikon cuaca tersendiri di toolbar sehingga pengguna dapat menampilkan atau menyembunyikan jam saat ini maupun widget cuaca/AQI secara terpisah dan fleksibel, dilengkapi stepper ukuran waktu (`-`, `+`, `Reset`) dari 50% hingga 250%.
   - **Fleksibilitas Jam Mulai Otomatis & Dark Time Picker**: Menyetel jam mulai otomatis dapat dilakukan langsung tanpa kewajiban mengisi durasi jam, menit, dan detik. Input jam mulai dirancang ulang dengan kontrol angka dark mode (`⏰ [ 00 ] : [ 00 ]`) yang modern dan elegan tanpa memunculkan popup putih bawaan sistem operasi.
   - **Template Preset Test Debug & Auto-Refresh**: Pilihan preset bawaan "Test Debug" (jadwal mulai otomatis 01:00 AM, sesi `debug 1` durasi 1m 15d, dan sesi `debug 2` durasi 1m dengan flash kustom). Memilih template preset langsung me-refresh seluruh antrean dan waktu tampilan secara seketika tanpa perlu menekan tombol reset.
   - **Transisi Sesi & Audio Mulus**: Melewati (*skip*) sesi yang sedang menunggu jadwal langsung beralih ke sesi berikutnya secara akurat, serta bel pengingat (*chime*) berbunyi tunggal tanpa duplikasi suara saat jam mulai otomatis tiba.
   - **Input Nilai Dasar Bersih (0 0 0)**: Form input durasi sesi dan timer diawali dari 0 jam 0 menit 0 detik agar pengguna tidak perlu repot menghapus angka bawaan.
   - **Drag & Drop Reordering**: Geser urutan sesi dengan mudah menggunakan handle grip atau tombol panah atas/bawah.
   - **Duplikasi Sesi & Preset Kustom**: Gandakan sesi dengan satu klik dan simpan susunan antrean lengkap sebagai template preset kustom yang dapat digunakan kembali kapan saja.
   - **Kustomisasi Flash per Sesi**: Sesi dapat memilih menggunakan aturan Flash Global atau aturan Flash Kustom tersendiri.

8. **Redesign Tombol Berbasis Ikon Seragam & Floating Tooltip**
   - Seluruh tombol kontrol di semua mode (Jam Utama, Stopwatch, Timer, Queue, Jam Dunia) didesain ulang menjadi tombol ikon modern yang ringkas dan seragam.
   - Dilengkapi *floating tooltip* informatif saat kursor diarahkan ke tombol agar fungsi tombol dan shortcut keyboard selalu jelas dan tidak membingungkan.

9. **Tab Multifungsi Lengkap**
   - **Stopwatch**: Penghitung waktu presisi milidetik dengan pencatat waktu putaran (*Lap / Split recording*).
   - **Countdown Timer**: Timer melingkar dengan preset cepat (5m, 10m, 15m, 20m, 30m, 45m, 1 jam, dst.).
   - **Jam Dunia**: Pantau zona waktu Indonesia (WIB, WITA, WIT) serta kota-kota internasional (Tokyo, London, New York, UTC) secara bersamaan.

10. **Reset Total ke Setelan Awal Pabrik & Penyimpanan Lokal**
   - **Reset Total**: Tombol reset menyeluruh di menu Pengaturan untuk menghapus seluruh data lokal dan mengembalikan jam ke setelan awal pabrik.
   - **Penyimpanan Otomatis (Local Storage)**: Seluruh preferensi ukuran teks, visibilitas milidetik, opasitas layar, tema, pengumuman ujian, daftar antrean, dan preset tersimpan otomatis di browser tanpa akun/login.

---

## ⌨️ Daftar Shortcut Keyboard

| Tombol | Fungsi |
|---|---|
| `Space` | Mulai / Jeda (*Timer, Stopwatch, Queue*) |
| `R` | Reset waktu aktif |
| `F` | Masuk / Keluar Fullscreen |
| `B` | Gelapkan layar seketika (*Blank screen*) |
| `M` | Mute / Unmute suara bel audio |
| `+` atau `=` | Perbesar ukuran jam (+10%) |
| `-` atau `_` | Perkecil ukuran jam (-10%) |
| `0` | Reset ukuran jam ke default (100%) |
| `1` - `5` | Pindah tab (Jam, Stopwatch, Timer, Queue, Dunia) |
| `?` | Buka jendela bantuan shortcut |
| `Esc` | Keluar mode fullscreen / tutup modal |

---

## 🎥 Penggunaan di OBS Studio (Browser Source)

1. Tambahkan Source baru di OBS: **Browser Source**.
2. Masukkan URL GitHub Pages atau file lokal `index.html`.
3. Atur resolusi sesuai kanvas (misal: `1920x1080`).
4. Klik tombol **Transparan** pada OmniClock dan pilih **0% (Bening)**.
5. OmniClock kini akan tampil melayang rapi di atas slide presentasi atau kamera Anda tanpa latar belakang yang menghalangi!
