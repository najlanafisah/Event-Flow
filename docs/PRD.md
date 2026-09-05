# PRD — EventFlow

**Status:** Draft v0.1 · **Gate:** menunggu persetujuan pengguna

## 1. Ringkasan produk

EventFlow adalah aplikasi web SaaS untuk panitia mengelola event dari pendaftaran sampai presensi. Fokus MVP: satu sumber data peserta, check-in cepat, dan ringkasan operasional yang mudah dibaca.

## 2. Tujuan dan ukuran keberhasilan

| Tujuan | Indikator MVP |
|---|---|
| Pendaftaran terkelola | pendaftar baru masuk ke data event tanpa entri ulang |
| Presensi cepat | operator dapat menemukan atau memindai peserta lalu check-in |
| Panitia mendapat gambaran | dashboard menampilkan pendaftar, hadir, dan kapasitas |

## 3. Pengguna dan hak akses

| Peran | Kebutuhan | Akses |
|---|---|---|
| Admin | menyiapkan event dan tim | seluruh modul |
| Event manager | memantau dan mengelola peserta | dashboard, event, pendaftar, laporan |
| Petugas presensi | check-in tanpa mengubah event | presensi, pencarian peserta |
| Pendaftar | mendaftar dan menerima bukti | formulir publik (fase lanjutan) |

## 4. Ruang lingkup MVP

1. **Dashboard:** metrik pendaftaran, hadir, kapasitas, dan daftar aktivitas presensi terakhir.
2. **Data event:** buat, lihat, ubah, arsipkan event; status Draft/Published/Closed; tanggal, lokasi, kuota, dan deskripsi.
3. **Pendaftaran:** formulir konfigurabel minimal (nama, email, telepon, instansi); validasi dan pesan berhasil.
4. **Data pendaftar:** daftar peserta, pencarian, filter event/status, detail, ekspor CSV.
5. **Presensi:** pencarian nama/kode pendaftaran, input/scan QR (antarmuka dahulu), konfirmasi check-in, pencegahan check-in ganda.
6. **Laporan ringan:** ringkasan jumlah daftar vs hadir per event dan ekspor.

## 5. Di luar MVP

Pembayaran, tiket berjenjang, email/SMS otomatis, integrasi QR scanner perangkat nyata, multi-tenant billing, SSO, aplikasi mobile, dan analitik lanjutan. Semua memerlukan keputusan serta fase terpisah.

## 6. Aturan bisnis inti

- Satu email hanya dapat terdaftar sekali untuk event yang sama.
- Pendaftar dapat berstatus `Pending`, `Confirmed`, `Cancelled`, atau `Checked-in`.
- Check-in hanya tersedia untuk event berstatus Published dan pada rentang waktu yang ditetapkan admin (parameter dapat diputuskan kemudian).
- Kode pendaftaran bersifat unik per peserta/event.
- Perubahan dan check-in mencatat waktu serta pelaku untuk audit dasar.

## 7. Data minimum

| Entitas | Atribut minimum |
|---|---|
| Event | id, nama, tanggal, lokasi, kuota, status, deskripsi |
| Pendaftar | id, event_id, kode, nama, email, telepon, instansi, status, created_at |
| Presensi | id, pendaftar_id, check_in_at, operator_id, metode |
| Pengguna | id, nama, email, peran |

## 8. Kriteria penerimaan MVP

- Admin dapat membuat event dan melihatnya pada daftar event.
- Pengunjung dapat mengirim formulir pendaftaran dengan validasi wajib dan duplikasi email.
- Panitia dapat mencari pendaftar dan mengubah/meninjau statusnya.
- Petugas dapat check-in peserta sekali; percobaan ulang memberi informasi yang jelas.
- Dashboard memperbarui ringkasan dari data yang sama.
- Seluruh layar utama tetap nyaman digunakan pada desktop dan mobile.

## 9. Keputusan yang masih ditunda

Metode autentikasi, penyimpanan data/backend, aturan kapasitas penuh, kanal notifikasi, dan format QR final akan diputuskan sebelum fase implementasi terkait.
