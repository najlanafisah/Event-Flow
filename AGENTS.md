# Kontrak Agen — EventFlow

## Tujuan
Bangun EventFlow sebagai front-end pengelolaan event berbasis HTML, CSS, dan JavaScript vanilla, mengikuti SOT yang disetujui.

## Sumber kebenaran

1. `../eventflow-sot-v0.1/PRD.md`
2. `../eventflow-sot-v0.1/UI-GUIDELINE.md`
3. `../eventflow-sot-v0.1/IMPLEMENTATION_PLAN.md`

Jika ada konflik, berhenti dan minta keputusan pengguna; jangan membuat asumsi yang memperluas scope.

## Batas fase

- Kerjakan hanya fase yang secara eksplisit disetujui pengguna.
- Setelah hasil fase tersedia, jelaskan ringkas hasil dan tunggu persetujuan tertulis sebelum memasuki fase berikutnya.
- Jangan membangun backend, autentikasi, pembayaran, integrasi eksternal, atau dependensi framework tanpa persetujuan khusus.

## Standar kode

- Gunakan HTML semantik, CSS custom properties, dan JavaScript modular/vanilla.
- Hindari dependensi eksternal pada baseline.
- Pertahankan responsif desktop, tablet, mobile; keyboard, focus state, kontras, label form, dan pesan error harus dapat diakses.
- Gunakan data mock kecil dan terpusat sampai kontrak API diputuskan.
- Jangan mengulang CSS/JS; buat komponen pola yang reusable.

## Cara bekerja hemat token

- Sebelum mengubah kode, baca file yang terkait dan buat perubahan paling kecil yang memenuhi kebutuhan.
- Laporkan ringkasan perubahan dan hasil verifikasi, bukan salinan file penuh.
- Jangan memodifikasi dokumen SOT kecuali pengguna meminta revisi SOT.
- Bila kebutuhan tidak jelas atau berdampak pada data/arsitektur, ajukan satu pertanyaan singkat.

## Checklist sebelum menyerahkan fase

- Navigasi dan aksi yang ada tidak memunculkan error JavaScript.
- Layout diperiksa pada lebar sekitar 360 px, 768 px, dan desktop.
- Tidak ada teks penting bergantung hanya pada warna.
- Semua artefak yang diminta tersedia dalam paket output.
