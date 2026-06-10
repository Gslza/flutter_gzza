# Flutter GZZA - Firebase Authentication App

Aplikasi Flutter modern yang mengintegrasikan sistem autentikasi lengkap menggunakan **Firebase Authentication**. Aplikasi ini dirancang dengan antarmuka pengguna (UI) gelap (*dark theme*) yang premium, modern, dan dilengkapi dengan animasi transisi yang halus.

## 🚀 Fitur Utama

* **Login Email & Password**: Dilengkapi dengan validasi format email dan panjang password.
* **Registrasi Akun Baru**: Form pendaftaran dengan verifikasi konfirmasi password.
* **Google Sign-In**: Login cepat menggunakan akun Google Anda.
* **Lupa Password**: Fitur reset password yang langsung mengirimkan link ke email pengguna.
* **Autentikasi Real-time**: Otomatis mendeteksi status login pengguna menggunakan `StreamBuilder` (jika sudah login akan langsung masuk ke halaman utama, dan sebaliknya).
* **Desain UI Modern**: Menggunakan perpaduan warna gradasi gelap (*dark gradient*), efek *glassmorphism*, dan animasi masuk (*fade & slide*).
* **Penanganan Error**: Pesan kesalahan autentikasi Firebase disajikan dalam Bahasa Indonesia yang mudah dipahami.

---

## 🛠️ Prasyarat

Sebelum menjalankan proyek ini, pastikan Anda telah menginstal:
* [Flutter SDK](https://docs.flutter.dev/get-started/install) (versi terbaru direkomendasikan)
* [Dart SDK](https://dart.dev/get-started/sdk)
* [Firebase CLI](https://firebase.google.com/docs/cli) (opsional, untuk konfigurasi mudah)

---

## ⚙️ Cara Instalasi & Konfigurasi Firebase

Proyek ini memerlukan konfigurasi Firebase sebelum dapat dijalankan di perangkat/emulator Anda. Silakan ikuti langkah-langkah berikut:

### 1. Kloning Repository
```bash
git clone https://github.com/Gslza/flutter_gzza.git
cd flutter_gzza
```

### 2. Instal Dependensi Flutter
```bash
flutter pub get
```

### 3. Konfigurasi Proyek Firebase (FlutterFire CLI)
Pastikan Anda sudah login ke akun Firebase Anda melalui Firebase CLI di terminal:
```bash
dart pub global activate flutterfire_cli
firebase login
flutterfire configure
```
> 💡 *Perintah `flutterfire configure` akan meminta Anda memilih/membuat project Firebase baru dan secara otomatis mengunduh file konfigurasi android (`google-services.json`) serta memperbarui file `lib/firebase_options.dart`.*

### 4. Aktifkan Metode Login di Firebase Console
1. Buka [Firebase Console](https://console.firebase.google.com/) dan pilih proyek Anda.
2. Masuk ke menu **Build** > **Authentication** > **Get Started**.
3. Pada tab **Sign-in method**, aktifkan penyedia berikut:
   * **Email/Password**
   * **Google** (masukkan nama proyek dan email dukungan)

---

## 🏃 Cara Menjalankan Aplikasi

Setelah konfigurasi Firebase selesai, jalankan perintah berikut untuk memulai aplikasi pada emulator atau perangkat fisik Anda:

```bash
flutter run
```

---

## 📁 Struktur Folder Penting

```text
lib/
├── main.dart                 # Inisialisasi Firebase & routing auth state
├── firebase_options.dart     # Opsi konfigurasi Firebase (digenerate otomatis)
├── services/
│   └── auth_service.dart     # Logika Firebase Auth (Sign In, Sign Up, Google, Logout)
└── pages/
    ├── login_page.dart       # UI Halaman Login & Lupa Password
    ├── register_page.dart    # UI Halaman Registrasi Akun
    └── home_page.dart        # UI Halaman Utama setelah sukses login
```

---

## 🔒 Konfigurasi Keamanan (.gitignore)

File sensitif seperti file konfigurasi Firebase lokal (`google-services.json`, `firebase_options.dart`) telah didaftarkan ke dalam `.gitignore` untuk mencegah kebocoran kunci API pribadi Anda ke repositori publik.
