# OmniClock Proyektor - Jam Multifungsi & Ujian 🕒

OmniClock Proyektor adalah aplikasi web jam digital multifungsi berbasis web yang dirancang khusus untuk kebutuhan **layar proyektor, ujian sekolah/kampus, presentasi, dan live streaming (OBS Studio)**.

Dibuat dengan HTML5, Tailwind CSS, dan Vanilla JavaScript murni tanpa ketergantungan server sehingga dapat langsung dijalankan di browser manapun atau dideploy secara gratis ke **GitHub Pages**.

---

## ✨ Fitur Utama

1. **Auto-Hide Header di Mode Fullscreen (Layar Penuh)**
   - Saat masuk ke mode fullscreen (tekan `F`), bilah navigasi atas (header) otomatis tersembunyi.
   - Jam terpusat rapi di tengah layar secara vertikal dan horizontal.
   - Gerakkan kursor ke tepi atas layar (`hover` di atas) untuk memunculkan kembali menu secara mulus.
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

4. **Kontrol Transparansi & Mode Overlay OBS (Fix Bug)**
   - Dropdown kontrol opasitas dengan tombol klik stabil tanpa bug hilang saat kursor digeser.
   - Slider opasitas 0% - 100% dengan tombol preset instan:
     - `0% (Bening)` : Khusus OBS Browser Source / overlay proyektor transparan.
     - `35%` & `70%` : Semi-transparan elegan dengan teks berbayang kontras tinggi.
     - `Solid (100%)` : Latar belakang solid gelap pekat.
   - Pilihan tema: **Deep Dark**, **Pure Black OLED**, dan **Proyektor Overlay**.

5. **Mode Ujian & Peringatan Flash Merah**
   - Banner teks berjalan (*marquee*) untuk tata tertib ujian yang dapat disunting.
   - Visual alert berkedip merah otomatis saat sisa waktu pengerjaan kurang dari menit yang ditentukan (misal 10 menit).
   - Audio bel sintetis (*Web Audio API*) tanpa perlu file MP3 eksternal.

6. **Tab Tambahan Multifungsi**
   - **Stopwatch**: Penghitung waktu presisi milidetik dengan fitur Split & Lap recording.
   - **Countdown Timer**: Timer melingkar dengan preset cepat (5m, 10m, 15m, 30m, 60m, 90m).
   - **Auto Queue Timer**: Antrean waktu bertahap otomatis (Ujian bertahap, Pomodoro, Sidang Skripsi).
   - **Jam Dunia**: Pantau waktu Indonesia (WIB, WITA, WIT) serta kota internasional secara bersamaan.

7. **Penyimpanan Lokal Otomatis (Local Storage)**
   - Preferensi ukuran jam, transparansi, tema, preset antrean, dan pengumuman ujian tersimpan otomatis di browser.

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

