# Setup untuk Windows

## Masalah CMake

Jika Anda mendapat error CMake saat build untuk Windows:
```
CMake Error: Compatibility with CMake < 3.5 has been removed
```

### Solusi 1: Install CMake (Recommended)

1. Download CMake dari: https://cmake.org/download/
2. Install CMake dan pastikan mencentang "Add CMake to system PATH"
3. Restart terminal/IDE Anda
4. Verifikasi instalasi: `cmake --version`
5. Pastikan versi CMake minimal 3.19 atau lebih baru

### Solusi 2: Gunakan Platform Lain

Jika tidak ingin install CMake, Anda bisa menjalankan aplikasi di platform lain:

#### Web (Paling Mudah)
```bash
flutter run -d chrome
```

#### Android
```bash
flutter run -d android
```

Pastikan Anda sudah:
- Install Android Studio
- Setup Android SDK
- Enable USB Debugging di device Android atau gunakan emulator

### Solusi 3: Update Flutter

Pastikan Flutter Anda sudah versi terbaru:
```bash
flutter upgrade
flutter doctor -v
```

## Catatan

Firebase Authentication bekerja di semua platform:
- ✅ Web - Tidak perlu CMake
- ✅ Android - Tidak perlu CMake
- ⚠️ Windows - Perlu CMake 3.19+
- ⚠️ iOS/macOS - Perlu Xcode (hanya di macOS)

Untuk development dan testing, disarankan menggunakan Web atau Android terlebih dahulu.

## Quick Start untuk Web

```bash
# Jalankan di browser
flutter run -d chrome

# Atau build untuk production
flutter build web
```

Aplikasi akan berjalan di browser dan semua fitur autentikasi Firebase akan bekerja dengan baik.
