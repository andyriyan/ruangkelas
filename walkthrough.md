# 🟢 Kelas Digital — Walkthrough & Panduan Penggunaan

Seluruh file telah dibuat. Berikut ringkasan struktur, cara pakai, dan fitur-fitur yang tersedia.

---

## 📁 Struktur File

```
ruangkelas-main/
├── index.html                ← Landing page utama
├── css/
│   └── style.css             ← NU Aswaja design system (SATU file CSS untuk semua)
└── materi/
    ├── template.html         ← ✏️ Template untuk materi baru (copy dari sini!)
    ├── logika-dasar.html     ← Dummy: Logika & Proposisi (Kelas X)
    ├── persamaan-kuadrat.html← Dummy: Persamaan Kuadrat (Kelas IX)
    └── trigonometri.html     ← Dummy: Trigonometri (Kelas X)
```

---

## 🚀 Cara Menambah Materi Baru

### Langkah 1 — Duplikat template
Copy file `materi/template.html` → rename sesuai topik, misal: `materi/integral.html`

### Langkah 2 — Edit konten di template
Cari komentar `✏️` di dalam file dan ubah:
- `<title>` → judul materi
- `<h1>` → judul halaman
- `.subtitle` → deskripsi singkat
- `.meta-badge` → kategori & kelas
- Isi bab-bab dengan teks + rumus LaTeX

### Langkah 3 — Tambah card di `index.html`
Copy blok berikut lalu paste di dalam `<div class="grid-container">`:

```html
<article class="card" data-tags="KATEGORI">
  <div class="card-thumb" style="background:linear-gradient(135deg,#f0fdf4,#dcfce7);">
    <i class="fas fa-ICON" style="font-size:2.8rem;color:#14532d;"></i>
  </div>
  <div class="card-body">
    <div class="card-meta">
      <span class="category">KATEGORI</span>
      <span class="card-level">Kelas X</span>
    </div>
    <h3>JUDUL MATERI</h3>
    <p>Deskripsi singkat materi.</p>
    <a href="materi/NAMAFILE.html" class="btn-main">
      <i class="fas fa-book-open"></i> Buka Materi
    </a>
  </div>
</article>
```

> [!TIP]
> Filter chip di landing page bekerja otomatis via `data-tags`. Isi dengan nama kategori lowercase tanpa spasi, contoh: `data-tags="aljabar"` atau `data-tags="geometri statistika"` (bisa lebih dari satu).

---

## 📐 Komponen CSS yang Tersedia

### Box / Alert
| Class | Warna | Kegunaan |
|---|---|---|
| `.box-formula` | Kuning emas | Rumus / formula utama |
| `.box-info` | Hijau mint | Definisi / catatan penting |
| `.box-example` | Abu-abu | Soal latihan / contoh |
| `.box-tip` | Biru muda | Tips & trik cepat |
| `.box-warning` | Oranye | Peringatan / jebakan umum |

### Elemen Lain
- `.step-list` + `.step-num` → daftar langkah bernomor dengan lingkaran hijau
- `.table-wrap > table` → tabel responsif
- `.toc` → kotak daftar isi
- `.math-display` → area display mode LaTeX (center + scroll x)

---

## 🔢 Menulis Rumus LaTeX / MathJax

| Mode | Sintaks | Contoh |
|---|---|---|
| Inline | `\( ... \)` atau `$ ... $` | `\(x^2 + 1\)` |
| Display block | `\[ ... \]` atau `$$ ... $$` | `\[\frac{-b \pm \sqrt{D}}{2a}\]` |

> [!IMPORTANT]
> MathJax 3 dimuat dari CDN. Pastikan ada koneksi internet saat membuka halaman pertama kali (untuk GitHub Pages ini selalu ada).

---

## 🌙 Fitur Dark Mode

Dark mode otomatis mengikuti preferensi sistem (via `prefers-color-scheme: dark`).
Tombol 🌙/☀️ di pojok kanan navbar juga bisa diklik manual — preferensi disimpan di `localStorage`.

---

## 📱 Mobile / Android Friendly

- Semua layout menggunakan CSS Grid `auto-fill` → kolom otomatis menyesuaikan lebar layar
- Font size menggunakan `clamp()` untuk skala otomatis
- Touch area tombol minimal 44×44px
- `-webkit-tap-highlight-color: transparent` untuk feel native
- `viewport-fit=cover` untuk support notch/safe area

---

## 📌 Icon FontAwesome

Beberapa icon yang cocok untuk materi matematika:

| Icon | Class |
|---|---|
| ➕ Aljabar | `fa-superscript` |
| 📐 Geometri | `fa-drafting-compass` |
| 📊 Statistika | `fa-chart-bar` |
| 🔢 Aritmetika | `fa-calculator` |
| 🧠 Logika | `fa-brain` |
| 📈 Fungsi | `fa-wave-square` |
| 🔄 Trigonometri | `fa-circle-notch` |
| ∫ Kalkulus | `fa-infinity` |

Ganti `fa-ICON` di template dengan nama class di atas.

---

## 🌐 Deploy ke GitHub Pages

1. Push semua file ke repo GitHub Anda
2. Buka **Settings → Pages → Source → main / (root)**
3. Akses via `https://NAMAUSER.github.io/NAMAREPO/`

