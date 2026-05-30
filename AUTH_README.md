# Firebase Authentication Flutter

Aplikasi Flutter dengan sistem autentikasi menggunakan Firebase Authentication.

## Fitur

- ✅ Login dengan email dan password
- ✅ Register akun baru
- ✅ Logout
- ✅ Auto-redirect berdasarkan status login
- ✅ Validasi form
- ✅ Error handling

## Struktur File

```
lib/
├── main.dart                    # Entry point aplikasi
├── firebase_options.dart        # Konfigurasi Firebase
├── services/
│   └── auth_service.dart       # Service untuk autentikasi
├── screens/
│   ├── login_screen.dart       # Halaman login
│   ├── register_screen.dart    # Halaman register
│   └── home_screen.dart        # Halaman home setelah login
└── widgets/
    └── auth_wrapper.dart       # Widget untuk cek status autentikasi
```

## Cara Menggunakan

### 1. Install Dependencies

```bash
flutter pub get
```

### 2. Pastikan Firebase sudah dikonfigurasi

File `firebase_options.dart` sudah berisi konfigurasi Firebase untuk semua platform.

### 3. Aktifkan Email/Password Authentication di Firebase Console

1. Buka [Firebase Console](https://console.firebase.google.com/)
2. Pilih project Anda
3. Ke menu Authentication > Sign-in method
4. Enable "Email/Password"

### 4. Jalankan Aplikasi

Untuk Web (paling mudah, tidak perlu CMake):
```bash
flutter run -d chrome
```

Untuk Android:
```bash
flutter run -d android
```

Untuk Windows (memerlukan CMake 3.19+):
```bash
flutter run -d windows
```

Jika ada masalah dengan Windows build, lihat file `WINDOWS_SETUP.md` untuk solusinya.

## Cara Kerja

1. **AuthWrapper**: Widget yang mendengarkan perubahan status autentikasi
   - Jika user sudah login → tampilkan HomeScreen
   - Jika user belum login → tampilkan LoginScreen

2. **AuthService**: Service yang menangani semua operasi autentikasi
   - `registerWithEmailPassword()` - Daftar akun baru
   - `signInWithEmailPassword()` - Login
   - `signOut()` - Logout
   - `authStateChanges` - Stream untuk monitor status login

3. **LoginScreen**: Halaman login dengan validasi form

4. **RegisterScreen**: Halaman register dengan konfirmasi password

5. **HomeScreen**: Halaman utama setelah login dengan tombol logout

## Testing

Untuk testing aplikasi:

1. Jalankan aplikasi
2. Klik "Daftar" untuk membuat akun baru
3. Isi email dan password (minimal 6 karakter)
4. Setelah berhasil, akan otomatis kembali ke halaman login
5. Login dengan akun yang baru dibuat
6. Akan masuk ke HomeScreen
7. Klik icon logout untuk keluar

## Error Handling

Aplikasi sudah dilengkapi dengan error handling untuk:
- Email sudah terdaftar
- Password terlalu lemah
- Email tidak valid
- User tidak ditemukan
- Password salah

Semua error akan ditampilkan dalam bentuk SnackBar.


## Troubleshooting

### Error NDK di Android

Jika Anda mendapat error terkait NDK seperti:
```
[CXX1101] NDK at D:\Android\Sdk\ndk\28.2.13676358 did not have a source.properties file
```

Solusi yang sudah diterapkan:
1. Menghapus `ndkVersion = flutter.ndkVersion` dari `android/app/build.gradle.kts`
2. Update `kotlinOptions` ke `kotlin.compilerOptions` untuk menghindari deprecation warning

### Build Failed - Unable to delete directory

Jika terjadi error saat clean build, tutup semua aplikasi yang mungkin mengakses folder build (IDE, terminal, file explorer) lalu coba lagi.

### Platform Specific

Aplikasi ini sudah dikonfigurasi untuk:
- ✅ Android
- ✅ iOS
- ✅ Web
- ✅ Windows
- ✅ macOS

Untuk menjalankan di platform tertentu:
```bash
flutter run -d chrome        # Web
flutter run -d windows       # Windows
flutter run -d android       # Android
flutter run -d ios           # iOS (hanya di macOS)
```

## Catatan Penting

1. Pastikan Firebase Authentication sudah diaktifkan di Firebase Console
2. Untuk production, jangan lupa tambahkan proper error handling dan loading states
3. Pertimbangkan untuk menambahkan fitur:
   - Email verification
   - Password reset
   - Social login (Google, Facebook, dll)
   - Remember me functionality
   - Biometric authentication
