# Panduan Integrasi Cusdis dengan Hugo + PaperMod

## 📋 Ringkasan

Cusdis telah berhasil diintegrasikan ke blog Hugo + PaperMod Anda. File-file berikut telah dibuat/dimodifikasi:

1. ✅ **layouts/partials/comments.html** - Template komentar Cusdis
2. ✅ **hugo.toml** - Konfigurasi Cusdis ditambahkan

## 🚀 Langkah Setup

### Langkah 1: Daftar di Cusdis

1. Buka [https://cusdis.com/dashboard](https://cusdis.com/dashboard)
2. Daftar akun baru atau login
3. Klik **"Add Website"**
4. Masukkan informasi website:
   - **Website URL**: `https://rakhmatwh.my.id/`
   - **Website Name**: Cathetanku (atau nama lain)

### Langkah 2: Copy App ID

Setelah website ditambahkan, Anda akan mendapatkan **App ID** dari dashboard. App ID berbentuk seperti ini:
```
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

### Langkah 3: Update hugo.toml

Buka file `hugo.toml` dan cari bagian `[params.cusdis]`, kemudian ganti:

```toml
[params.cusdis]
    appId = "GANTI_DENGAN_APP_ID_ANDA"  # <-- Ganti dengan App ID Anda
    lang = "id"
```

Contoh setelah diganti:
```toml
[params.cusdis]
    appId = "12345678-abcd-1234-abcd-123456789abc"
    lang = "id"
```

### Langkah 4: Aktifkan Komentar (Per Post)

Cusdis akan muncul di semua post secara default karena `comments = true` di `hugo.toml`.

Jika Anda ingin **menonaktifkan komentar di post tertentu**, tambahkan di front matter post:

```yaml
---
title: "Judul Post"
date: 2024-01-01
comments: false  # <-- Nonaktifkan komentar untuk post ini
---
```

### Langkah 5: Test Lokal

Jalankan Hugo dev server:

```bash
hugo server -D
```

Buka browser dan kunjungi post mana saja, Anda akan melihat widget komentar Cusdis di bagian bawah post.

## 🎨 Tampilan & Tema

### Integrasi Seamless (Baru)

Script khusus telah ditambahkan untuk memastikan Cusdis menyatu dengan blog:
- ✅ **Auto-Sync Tema**: Ketika Anda menekan tombol switch light/dark mode di blog, Cusdis akan otomatis berubah tema secara real-time.
- ✅ **Hapus Border**: Frame "kotak" yang mengganggu telah dihapus agar komentar terlihat menyatu dengan halaman.
- ✅ **Hapus Scrollbar**: Script Cusdis akan otomatis mengatur tinggi komentar.

### Catatan Penting (Limitasi)

Cusdis menggunakan teknologi **iframe** untuk keamanan dan privasi. Ini memiliki beberapa konsekuensi:
1. **Styling Terbatas**: Kita tidak bisa mengubah font atau padding di _dalam_ kotak komentar secara langsung lewat CSS blog.
2. **Warna Input**: Warna kotak input ditentukan oleh server Cusdis berdasarkan tema (light/dark).

Jika Anda melihat scrollbar muncul, coba refresh halaman. Script Cusdis biasanya akan menghitung ulang tinggi frame setelah loading selesai.

**File CSS**: `assets/css/extended/custom.css` (hanya styling container luar)
**Script JS**: `layouts/partials/comments.html` (logika sinkronisasi tema)

## 🎨 Customization

### Mengganti Bahasa

Edit di `hugo.toml`:
```toml
lang = "en"  # Bahasa Inggris
lang = "id"  # Bahasa Indonesia
lang = "zh-cn"  # Mandarin
```

### Tema Komentar

Uncomment baris `theme` di `hugo.toml`:
```toml
theme = "light"  # Tema terang
theme = "dark"   # Tema gelap
theme = "auto"   # Otomatis mengikuti tema website
```

## 📝 Moderasi Komentar

1. Login ke [Cusdis Dashboard](https://cusdis.com/dashboard)
2. Klik website Anda
3. Anda akan melihat semua komentar yang masuk
4. **Approve** komentar untuk menampilkannya di website
5. **Delete** komentar spam

> **Catatan**: Secara default, komentar tidak langsung muncul. Anda harus approve terlebih dahulu dari dashboard.

## 🔧 Troubleshooting

### Komentar tidak muncul?

1. ✅ Pastikan `comments = true` di `hugo.toml`
2. ✅ Pastikan `appId` sudah diganti dengan App ID yang benar
3. ✅ Pastikan front matter post tidak memiliki `comments: false`
4. ✅ Clear cache browser (Ctrl + Shift + R)

### Widget Cusdis menampilkan error?

- Cek App ID sudah benar
- Pastikan URL website di dashboard Cusdis sama dengan `baseURL` di `hugo.toml`

## 📚 Referensi

- [Cusdis Documentation](https://cusdis.com/doc)
- [Cusdis Dashboard](https://cusdis.com/dashboard)
- [Cusdis GitHub](https://github.com/djyde/cusdis)

## 🎯 Fitur Cusdis

- ✅ Lightweight (~5kb gzipped)
- ✅ Privacy-first (tidak tracking user)
- ✅ Open-source
- ✅ Email notification untuk komentar baru
- ✅ Quick approve via email
- ✅ Webhook support
- ✅ Multi-language support

## 💡 Tips

1. **Free tier** Cusdis memberikan 1 website dan 100 approved comments/bulan
2. Gunakan **Quick Approve** di email untuk approve komentar tanpa login dashboard
3. Setup **Webhook** untuk integrasi dengan Discord/Slack jika perlu notifikasi real-time
