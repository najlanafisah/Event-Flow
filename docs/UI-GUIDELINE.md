# UI Guideline — EventFlow

**Status:** Draft v0.1 · **Gate:** menunggu persetujuan pengguna

## 1. Arah visual

Gaya **modern futuristic SaaS**: permukaan gelap berlapis, garis tipis transparan, ruang lega, data yang dominan, dan aksen energi hijau-kuning. Kesan yang dituju adalah operasi event yang sigap, bukan dekorasi berlebihan.

## 2. Token desain

| Token | Nilai | Pemakaian |
|---|---|---|
| `--bg` | `#08120E` | latar utama |
| `--surface` | `#10211A` | kartu/panel |
| `--surface-raised` | `#163027` | hover/panel fokus |
| `--text` | `#F3FAF5` | teks utama |
| `--muted` | `#99AAA1` | teks pendukung |
| `--green` | `#38E07B` | aksi utama, sukses, presensi |
| `--yellow` | `#F5D547` | perhatian, kapasitas, aksen |
| `--danger` | `#FF6B6B` | error/aksi destruktif |
| `--line` | `rgba(212,255,223,.12)` | batas halus |

Gunakan hijau sebagai warna tindakan dan status positif; kuning hanya sebagai penekanan atau peringatan. Jangan mengandalkan warna saja: setiap status harus memiliki label atau ikon.

## 3. Tipografi dan ruang

- Font: `Inter` untuk antarmuka; fallback `system-ui, sans-serif`.
- Judul halaman 28–32 px / 600; heading bagian 18–20 px / 600; isi 14–16 px / 400–500.
- Skala jarak: 4, 8, 12, 16, 24, 32, 48 px.
- Radius: 14 px untuk kartu, 10 px untuk input/tombol; bayangan lembut, bukan glow berlebih.

## 4. Pola layar dan navigasi

Navigasi desktop berupa sidebar kiri: logo, Dashboard, Event, Pendaftar, Presensi, Laporan, Pengaturan. Pada layar kecil berubah menjadi drawer. Header selalu memuat pemilih event aktif, notifikasi, dan avatar pengguna.

### Dashboard (tampilan target)

```text
┌──────────────────────────────────────────────────────────────────────────────┐
│ EventFlow    Dashboard                         [Tech Summit 2026 ▾]  ◎  AD   │
├───────────────┬──────────────────────────────────────────────────────────────┤
│ ◉ Dashboard   │ Selamat pagi, Adit                         [+ Buat event]     │
│ ◇ Event       │ Pantau event dan presensi Anda secara real-time.              │
│ ◉ Pendaftar   │                                                              │
│ ◇ Presensi    │ [1.248 Terdaftar] [864 Hadir] [69% Presensi] [1.800 Kuota]   │
│ ◇ Laporan     │                                                              │
│               │ Tren pendaftaran                  Aktivitas presensi          │
│ ───────────   │ ▁▃▅▆▇▆▉                         09:41  Nabila — Check-in ✓    │
│ Pengaturan    │                                    09:39  Raka — Check-in ✓   │
│               │ Daftar event terbaru              09:34  Citra — QR tidak    │
└───────────────┴──────────────────────────────────────────────────────────────┘
```

## 5. Komponen

| Komponen | Pedoman |
|---|---|
| Tombol utama | hijau, teks gelap, satu aksi dominan per area |
| Tombol sekunder | transparan/surface, border halus |
| Status | badge berlabel: Confirmed hijau, Pending kuning, Cancelled merah |
| Kartu metrik | label kecil, angka besar, delta singkat bila relevan |
| Tabel | header lengket bila daftar panjang; aksi baris lewat menu; status mudah dipindai |
| Form | label selalu terlihat, bantuan di bawah input, error dekat field |
| Empty state | jelaskan kondisi dan berikan satu aksi berikutnya |
| Toast | sukses/error ringkas, tidak menutupi aksi penting |

## 6. Alur UX utama

1. **Pendaftaran:** pilih event → isi data → validasi langsung → konfirmasi + kode pendaftaran.
2. **Presensi:** pilih event → scan/cari → tampilkan identitas → konfirmasi → status berhasil atau sudah hadir.
3. **Kelola event:** daftar event → buat/ubah → simpan draft atau publish → lihat metrik terkait.

## 7. Aksesibilitas dan responsif

- Kontras teks minimum WCAG AA; jangan gunakan hijau/kuning untuk teks kecil pada latar terang.
- Semua kontrol dapat dipakai keyboard dengan focus ring jelas.
- Target sentuh minimal 44 × 44 px; tabel diberi mode kartu atau scroll horizontal terkontrol pada mobile.
- Jangan menyampaikan status presensi hanya dengan animasi/warna; gunakan teks dan umpan balik yang dapat dibaca pembaca layar.

## 8. Batasan implementasi front-end

Gunakan HTML semantik, CSS custom properties, dan JavaScript vanilla. Tidak ada framework, library UI, atau dependensi eksternal pada baseline. Ikon dapat diganti SVG lokal yang konsisten pada fase implementasi.
