# Quick Start Guide

## Cara Tercepat Menjalankan Aplikasi

### 1. Install Dependencies
```bash
flutter pub get
```

### 2. Jalankan di Web (Recommended untuk Testing)
```bash
flutter run -d chrome
```

Aplikasi akan otomatis terbuka di browser Chrome.

## Fitur yang Sudah Dibuat

✅ Login dengan email & password
✅ Register akun baru  
✅ Logout
✅ Validasi form
✅ Error handling
✅ Auto-redirect berdasarkan status login

## Testing Aplikasi

1. Aplikasi akan terbuka di browser
2. Klik tombol "Daftar" untuk membuat akun baru
3. Masukkan email dan password (minimal 6 karakter)
4. Setelah berhasil register, akan kembali ke halaman login
5. Login dengan akun yang baru dibuat
6. Anda akan masuk ke halaman Home
7. Klik icon logout untuk keluar

## Struktur Kode

```
lib/
├── main.dart                    # Entry point
├── services/
│   └── auth_service.dart       # Service autentikasi
├── screens/
│   ├── login_screen.dart       # Halaman login
│   ├── register_screen.dart    # Halaman register
│   └── home_screen.dart        # Halaman home
└── widgets/
    └── auth_wrapper.dart       # Auto-redirect widget
```

## Platform Support

| Platform | Status | Catatan |
|----------|--------|---------|
| Web | ✅ Ready | Tidak perlu setup tambahan |
| Android | ✅ Ready | Perlu Android SDK |
| Windows | ⚠️ Perlu CMake | Install CMake 3.19+ |
| iOS | ✅ Ready | Perlu Xcode (macOS only) |
| macOS | ✅ Ready | Perlu Xcode |

## Troubleshooting

### Windows Build Error
Jika error CMake di Windows, lihat `WINDOWS_SETUP.md`

### Firebase Not Configured
Pastikan Email/Password authentication sudah diaktifkan di Firebase Console:
1. Buka https://console.firebase.google.com/
2. Pilih project: tutorial-firebase-def27
3. Authentication > Sign-in method
4. Enable "Email/Password"

### Dependency Conflict
Jika ada masalah dependency:
```bash
flutter clean
flutter pub get
```

## Next Steps

Setelah aplikasi berjalan, Anda bisa menambahkan:
- Email verification
- Password reset
- Social login (Google, Facebook)
- Profile management
- Remember me functionality
