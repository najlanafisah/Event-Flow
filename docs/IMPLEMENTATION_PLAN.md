# Implementation Plan — EventFlow

**Prinsip eksekusi:** fase berikutnya hanya dimulai setelah persetujuan eksplisit pengguna. Tidak ada pekerjaan implementasi yang berjalan otomatis.

## Peta fase dan gerbang keputusan

| Fase | Hasil | Persetujuan sebelum lanjut |
|---|---|---|
| 1. SOT | PRD, UI Guideline, Implementation Plan | **Persetujuan SOT v0.1** |
| 2. Fondasi UI | struktur HTML, token CSS, shell responsif, data mock | Persetujuan tampilan fondasi |
| 3. Modul inti | Event, Pendaftar, Presensi, Dashboard | Persetujuan modul inti |
| 4. Pendaftaran & laporan | formulir, validasi, ekspor mock/CSV, laporan | Persetujuan alur end-to-end |
| 5. Penguatan | aksesibilitas, responsif, QA, dokumentasi | Persetujuan rilis front-end |

## Fase 2 — Fondasi UI (setelah disetujui)

**Tujuan:** membangun kerangka aplikasi statis yang konsisten.

- Susun folder `index.html`, `assets/css/`, `assets/js/`, dan `assets/icons/`.
- Buat token warna, tipografi, grid, sidebar, header, tombol, form, badge, dan tabel.
- Siapkan data mock lokal serta navigasi antar layar tanpa backend.
- Uji desktop 1440 px, tablet 768 px, mobile 360 px.

**Selesai bila:** shell bisa dinavigasi, dashboard tampak sesuai guideline, dan tidak ada overflow/kontras utama bermasalah.

## Fase 3 — Modul inti (setelah disetujui)

Urutan: Data Event → Data Pendaftar → Presensi → Dashboard terhubung data mock.

- CRUD front-end berbasis state lokal/mocked data.
- Filter, pencarian, status, detail peserta, dan pencegahan check-in ganda di sisi antarmuka.
- Konfirmasi untuk tindakan yang mengubah status penting.

**Selesai bila:** skenario demo admin dan petugas presensi dapat dilakukan tanpa jalan buntu.

## Fase 4 — Pendaftaran & laporan (setelah disetujui)

- Form pendaftaran publik, validasi field, dan layar sukses dengan kode demo.
- Ringkasan laporan dan ekspor CSV dari data lokal.
- Empty/loading/error states untuk alur penting.

**Selesai bila:** alur daftar → muncul di pendaftar → check-in → dashboard/laporan dapat didemokan.

## Fase 5 — Penguatan & serah-terima (setelah disetujui)

- Audit keyboard, fokus, label form, kontras, dan responsive layout.
- Pemeriksaan manual pada browser modern serta perapian kode.
- Dokumentasi cara menjalankan dan batasan data mock.

## Aturan kerja hemat token

- Satu artefak per langkah; tampilkan ringkasan/diff, bukan mengulang file penuh kecuali diminta.
- Gunakan data contoh kecil dan reusable CSS/JS, hindari boilerplate berulang.
- Catat hanya keputusan, asumsi, dan perubahan pada dokumen SOT.
- Jika sebuah keputusan memengaruhi scope, keamanan, atau arsitektur, berhenti dan minta persetujuan lebih dahulu.

## Risiko dan mitigasi awal

| Risiko | Mitigasi |
|---|---|
| Kebutuhan backend belum dipilih | pastikan UI memakai adapter data/mock yang mudah diganti |
| Aturan presensi berubah | isolasi status dan validasi dalam fungsi JS sederhana |
| Dashboard menjadi terlalu padat | utamakan empat metrik dan aktivitas terakhir |
| Desain futuristik mengurangi keterbacaan | jaga kontras, teks jelas, dan dekorasi minimal |

## Keputusan yang diperlukan sebelum Fase 2

1. Setujui atau revisi SOT v0.1.
2. Tentukan apakah fase UI tetap memakai data mock lokal (rekomendasi) atau perlu kontrak API sejak awal.
3. Beri nama produk final bila bukan **EventFlow**.
