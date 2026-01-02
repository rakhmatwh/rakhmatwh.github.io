# Cathetanku - Blog Dokumentasi

> Personal blog tentang hobi, teknologi, dan kehidupan | Hugo + PaperMod

[![Hugo](https://img.shields.io/badge/Hugo-0.152.2-ff4088?logo=hugo)](https://gohugo.io/)
[![PaperMod](https://img.shields.io/badge/Theme-PaperMod-blue)](https://github.com/adityatelange/hugo-PaperMod)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

**Live Website**: [https://rakhmatwh.my.id/](https://rakhmatwh.my.id/)

---

## 📋 Daftar Isi

- [Tentang Blog](#-tentang-blog)
- [Fitur Utama](#-fitur-utama)
- [Tech Stack](#-tech-stack)
- [Struktur Project](#-struktur-project)
- [Setup & Installation](#-setup--installation)
- [Konfigurasi](#-konfigurasi)
- [Customization](#-customization)
- [Content Management](#-content-management)
- [Deployment](#-deployment)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)

---

## 🎯 Tentang Blog

**Cathetanku** adalah blog pribadi milik Rakhmat Wahyu (IT Network Engineer) yang membahas berbagai topik:
- 💻 Teknologi & IT Networking
- 🏓 Tenis Meja (Table Tennis)
- 🚲 Fixed Gear (Fixie) Culture
- 📝 Catatan Pribadi & Pemikiran

Blog ini dibangun menggunakan **Hugo** dengan tema **PaperMod** yang telah di-customize untuk memberikan pengalaman membaca yang nyaman dengan skema warna eye-friendly.

---

## ✨ Fitur Utama

### 🎨 Design & UI
- ✅ **Eye-Friendly Color Scheme** - Palet warna hangat yang mengurangi ketegangan mata
- ✅ **Dark/Light Mode** - Toggle tema dengan smooth transition
- ✅ **Responsive Design** - Mobile-first dan tablet-friendly
- ✅ **Custom 404 Page** - Halaman error yang estetik
- ✅ **Gradient Borders** - Accent colors yang modern
- ✅ **Smooth Animations** - Micro-interactions untuk UX yang lebih baik

### 📝 Content Features
- ✅ **Search Functionality** - Fuse.js powered search
- ✅ **Table of Contents** - Auto-generated ToC untuk artikel panjang
- ✅ **Reading Time** - Estimasi waktu baca
- ✅ **Breadcrumbs Navigation** - Navigasi hierarki
- ✅ **Post Navigation** - Previous/Next post links
- ✅ **Related Posts** - Rekomendasi artikel terkait
- ✅ **Tags System** - Kategorisasi dengan tag

### 💬 Interaksi
- ✅ **Cusdis Comments** - Comment system yang privacy-first
  - Auto-sync dengan tema blog
  - Header section dengan gradient border
  - Card-based container design
  - Moderasi komentar via dashboard

### 🔧 Technical
- ✅ **Syntax Highlighting** - Dracula theme untuk code blocks
- ✅ **Share Buttons** - Social media sharing
- ✅ **RSS Feed** - XML feed untuk subscribers
- ✅ **JSON Output** - Search index generation
- ✅ **Custom CSS** - Extended styling system
- ✅ **SEO Optimized** - Meta tags dan structured data

---

## 🛠️ Tech Stack

| Component | Technology | Version |
|-----------|-----------|---------|
| **Static Site Generator** | Hugo | 0.152.2 |
| **Theme** | PaperMod | Latest |
| **Comment System** | Cusdis | Cloud |
| **Search** | Fuse.js | Built-in |
| **Syntax Highlighting** | Chroma | Dracula |
| **Deployment** | GitHub Pages / Cloudflare Pages | - |
| **Version Control** | Git | - |

---

## 📁 Struktur Project

```
cathetanku/
├── .git/                      # Git repository
├── .github/                   # GitHub workflows
│   └── workflows/
├── archetypes/               # Content templates
│   └── default.md
├── assets/                   # Asset files (CSS, JS, images)
│   └── css/
│       └── extended/
│           └── custom.css    # Custom styling
├── content/                  # Blog content
│   ├── about.md             # About page
│   ├── archives.md          # Archive page
│   ├── search.md            # Search page
│   └── posts/               # Blog posts
│       ├── _index.md
│       ├── fixed-gear-101.md
│       ├── sejarah-fixie.md
│       └── ...
├── layouts/                  # Custom layouts
│   ├── 404.html             # Custom 404 page
│   ├── index.html           # Homepage layout
│   ├── _default/
│   │   └── baseof.html
│   ├── partials/            # Reusable components
│   │   ├── breadcrumbs.html
│   │   ├── comments.html    # Cusdis integration
│   │   ├── home_info.html
│   │   └── related_posts.html
│   └── posts/
│       └── single.html
├── static/                   # Static files (images, favicon)
│   ├── me.jpg
│   └── me.png
├── themes/                   # Hugo themes
│   └── PaperMod/            # PaperMod theme (git submodule)
├── hugo.toml                 # Hugo configuration
├── PANDUAN_CUSDIS.md        # Cusdis integration guide
└── README.md                # This file
```

---

## 🚀 Setup & Installation

### Prerequisites

Pastikan Anda sudah menginstall:
- **Git** - Version control
- **Hugo Extended** - v0.152.2+ ([Download](https://gohugo.io/installation/))
- **Text Editor** - VS Code / Sublime / Vim / etc.

### 1. Clone Repository

```bash
git clone https://github.com/rakhmatwh/rakhmatwh.github.io.git cathetanku
cd cathetanku
```

### 2. Install PaperMod Theme

Theme sudah include sebagai git submodule:

```bash
git submodule update --init --recursive
```

Atau manual download:

```bash
git clone https://github.com/adityatelange/hugo-PaperMod themes/PaperMod --depth=1
```

### 3. Run Development Server

```bash
hugo server -D
```

Buka browser: `http://localhost:1313/`

### 4. Build untuk Production

```bash
hugo --minify
```

Output akan ada di folder `public/`

---

## ⚙️ Konfigurasi

### File Konfigurasi: `hugo.toml`

#### Base Configuration

```toml
baseURL = "https://rakhmatwh.my.id/"
languageCode = 'en-us'
title = 'Cathetanku'
theme = "PaperMod"
```

#### Syntax Highlighting

```toml
[markup.highlight]
    style = "dracula"          # Tema syntax highlighting
    lineNos = true             # Nomor baris
    lineNumbersInTable = true  # Nomor baris dalam tabel
```

#### Pagination

```toml
[pagination]
pagerSize = 5  # Jumlah post per halaman
```

#### PaperMod Parameters

```toml
[params]
mainSections = ["posts"]
ShowPageNums = true
ShowBreadCrumbs = true
ShowToc = true
TocOpen = true
ShowShareButtons = true
ShowReadingTime = true
ShowPostNavLinks = true
comments = true
```

#### Cusdis Comment System

```toml
[params.cusdis]
    appId = "your-app-id-here"  # Dari dashboard Cusdis
    lang = "id"                  # Bahasa: id, en, zh-cn, dll
    theme = "auto"               # auto, light, dark
```

📖 **Detail setup**: Lihat [PANDUAN_CUSDIS.md](PANDUAN_CUSDIS.md)

#### Menu Navigation

```toml
[[menu.main]]
    name = "Home"
    url = "/"
    weight = 5

[[menu.main]]
    name = "Search"
    url = "/search/"
    weight = 10

[[menu.main]]
    name = "Archive"
    url = "/archives/"
    weight = 15

[[menu.main]]
    name = "Tags"
    url = "/tags/"
    weight = 20

[[menu.main]]
    name = "About"
    url = "/about/"
    weight = 25
```

---

## 🎨 Customization

### Custom CSS: `assets/css/extended/custom.css`

Blog ini menggunakan custom CSS untuk:

#### 1. Eye-Friendly Color Scheme

**Light Mode:**
```css
:root {
  --theme: #faf8f5;        /* Warm off-white background */
  --entry: #ffffff;        /* Pure white for cards */
  --primary: #2d3436;      /* Soft dark gray for headings */
  --secondary: #636e72;    /* Muted gray for secondary text */
  --content: #4a4a4a;      /* Comfortable reading gray */
  --border: #e0dcd6;       /* Subtle warm border */
}
```

**Dark Mode:**
```css
[data-theme="dark"] {
  --theme: #1a1d21;        /* Not pure black, slight warmth */
  --entry: #22262b;        /* Slightly lighter for cards */
  --primary: #e8e6e3;      /* Warm white, not harsh */
  --content: #d4d0cc;      /* Easy reading warm gray */
  --border: #3a3f46;       /* Subtle dark border */
}
```

#### 2. Typography

```css
body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto;
  letter-spacing: 0.01em;
  line-height: 1.7;
}

.post-content {
  font-size: 1.05rem;
  line-height: 1.8;
}
```

#### 3. Link Colors

```css
/* Light mode */
a {
  color: #0077b6;
}

/* Dark mode */
[data-theme="dark"] a {
  color: #64b5f6;
}
```

#### 4. Cusdis Comment Styling

- Gradient border header dengan ikon chat
- Card container dengan shadow
- Responsive untuk mobile
- Auto-sync tema dengan blog

### Custom Layouts

#### Custom Homepage: `layouts/index.html`
- Modified untuk menampilkan tag buttons
- Custom home info section

#### Custom 404: `layouts/404.html`
- Aesthetic error page
- Link kembali ke home

#### Custom Comments: `layouts/partials/comments.html`
- Cusdis integration
- Theme synchronization script
- Aesthetic section design

---

## 📝 Content Management

### Membuat Post Baru

```bash
hugo new posts/judul-post.md
```

### Front Matter Template

```yaml
---
title: "Judul Post Anda"
date: 2024-01-01T10:00:00+07:00
draft: false
tags: ["tag1", "tag2"]
categories: ["kategori"]
description: "Ringkasan singkat post"
cover:
    image: "images/cover.jpg"
    alt: "Alt text image"
    caption: "Caption untuk image"
ShowToc: true
TocOpen: true
comments: true
---

Konten post dimulai di sini...
```

### Menonaktifkan Komentar per Post

Tambahkan di front matter:

```yaml
comments: false
```

### Menambahkan Gambar

1. **Simpan di folder static:**
   ```
   static/images/nama-gambar.jpg
   ```

2. **Gunakan dalam markdown:**
   ```markdown
   ![Alt text](/images/nama-gambar.jpg)
   ```

### Code Blocks dengan Syntax Highlighting

````markdown
```python
def hello_world():
    print("Hello, World!")
```
````

Bahasa yang didukung: `python`, `javascript`, `go`, `bash`, `css`, `html`, dll.

---

## 🌐 Deployment

### Option 1: GitHub Pages

1. **Push ke repository GitHub:**
   ```bash
   git add .
   git commit -m "Update blog"
   git push origin main
   ```

2. **Build dengan GitHub Actions:**
   
   File: `.github/workflows/hugo.yml`

3. **Configure GitHub Pages:**
   - Repository Settings → Pages
   - Source: GitHub Actions
   - Custom domain (optional): `rakhmatwh.my.id`

### Option 2: Cloudflare Pages

1. **Connect repository ke Cloudflare:**
   - Cloudflare Dashboard → Pages → Create Project

2. **Build Settings:**
   - Framework preset: Hugo
   - Build command: `hugo --minify`
   - Build output: `public`
   - Environment variable: `HUGO_VERSION = 0.152.2`

3. **Custom Domain:**
   - Add DNS record di Cloudflare

### Option 3: Manual Deployment

```bash
# Build
hugo --minify

# Upload folder public/ ke hosting
rsync -avz public/ user@server:/var/www/html/
```

---

## 🐛 Troubleshooting

### Hugo Server Tidak Jalan

```bash
# Cek versi Hugo
hugo version

# Pastikan minimal v0.152.2 Extended
# Download dari: https://github.com/gohugoio/hugo/releases
```

### Theme Tidak Muncul

```bash
# Update submodule
git submodule update --init --recursive

# Atau clone manual
git clone https://github.com/adityatelange/hugo-PaperMod themes/PaperMod
```

### Custom CSS Tidak Apply

1. Pastikan file ada di: `assets/css/extended/custom.css`
2. Hard refresh browser: `Ctrl + Shift + R`
3. Check build output untuk error

### Cusdis Tidak Muncul

1. ✅ Pastikan `comments = true` di `hugo.toml`
2. ✅ Pastikan App ID sudah benar
3. ✅ Pastikan front matter post tidak ada `comments: false`
4. ✅ Clear cache browser

📖 **Troubleshooting lengkap**: Lihat [PANDUAN_CUSDIS.md](PANDUAN_CUSDIS.md)

### Build Error: Module Not Found

```bash
# Inisialisasi Hugo module
hugo mod init github.com/rakhmatwh/rakhmatwh.github.io

# Atau hapus go.mod dan go.sum jika ada
rm go.mod go.sum
```

---

## 📚 Dokumentasi Tambahan

- **[PANDUAN_CUSDIS.md](PANDUAN_CUSDIS.md)** - Panduan lengkap integrasi Cusdis comment system
- **[Hugo Documentation](https://gohugo.io/documentation/)** - Official Hugo docs
- **[PaperMod Documentation](https://github.com/adityatelange/hugo-PaperMod/wiki)** - PaperMod theme wiki
- **[Cusdis Documentation](https://cusdis.com/doc)** - Cusdis official docs

---

## 🤝 Contributing

Kontribusi sangat diterima! Jika Anda menemukan bug atau ingin menambahkan fitur:

1. Fork repository ini
2. Buat branch baru: `git checkout -b feature/nama-fitur`
3. Commit changes: `git commit -m 'feat: Add new feature'`
4. Push ke branch: `git push origin feature/nama-fitur`
5. Submit Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Rakhmat Wahyu**
- Website: [rakhmatwh.my.id](https://rakhmatwh.my.id)
- Email: [rakhmatwh@gmail.com](mailto:rakhmatwh@gmail.com)
- GitHub: [@rakhmatwh](https://github.com/rakhmatwh)

---

## 🙏 Acknowledgments

- [Hugo](https://gohugo.io/) - Static site generator yang cepat dan powerful
- [PaperMod](https://github.com/adityatelange/hugo-PaperMod) - Clean and simple Hugo theme
- [Cusdis](https://cusdis.com/) - Privacy-first, lightweight comment system
- [Dracula Theme](https://draculatheme.com/) - Beautiful syntax highlighting

---

<div align="center">
  
**Made with ❤️ and ☕ by Rakhmat**

⭐ Star this repo if you find it helpful!

</div>
