# SIMRSPasien — Aplikasi Pasien RSU Pemasyarakatan

Aplikasi Android (Kotlin + ViewBinding) untuk pasien: janji temu, video call dokter, paket MCU, portal hasil medis, dan riwayat transaksi.

## Struktur kode

```
app/src/main/java/com/rsupemasyarakatan/pasien/
├── data/
│   ├── model/        Data class bersama (KonsultasiAktif)
│   ├── local/        Penyimpanan lokal berbasis SharedPreferences (*Prefs)
│   └── dummy/        Data contoh/sementara (DokterData) — ganti dengan API nanti
├── util/             Helper umum (PdfHelper)
└── ui/
    ├── splash/       Layar pembuka (launcher)
    ├── main/         MainActivity + bottom navigation
    ├── auth/         Login, Register
    ├── home/         Beranda, artikel, video
    ├── notifikasi/   Daftar notifikasi
    ├── igd/          Info IGD
    ├── scan/         Scan QR
    ├── janjitemu/    Alur buat janji temu dokter
    ├── videocall/    Alur video call dokter
    ├── pembatalan/   Alur pembatalan janji / konsultasi
    ├── mcu/          Paket Medical Check Up
    ├── portal/       Portal pasien: lab, radiologi, resume medis, resep, elektrodiagnostik
    ├── transaksi/    Riwayat & transaksi
    ├── profil/       Akun: edit profil, password, hapus akun, logout
    ├── keamanan/     PIN, OTP, biometrik
    ├── pasien/       Daftar & pendaftaran pasien (keluarga)
    └── common/       Dialog yang dipakai lintas fitur
```

## Konvensi

- Satu fitur = satu package di `ui/`. Activity, Fragment, Adapter, Dialog, dan BottomSheet milik fitur itu diletakkan bersama.
- Nama layout mengikuti tipe: `activity_*`, `fragment_*`, `item_*`, `dialog_*`, `bottom_sheet_*`, `mockup_*`.
- Versi library dikelola di `gradle/libs.versions.toml`.
- Folder `build/`, `.gradle/`, `.idea/`, dan `local.properties` tidak perlu dibagikan/di-commit (sudah ada di `.gitignore`).
