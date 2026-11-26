# USER EXPERIENCE SPECIFICATION (UX-SPEC)

## Fitur: BRImo UX Redesign — Konfirmasi Transfer

**Versi:** 1.0
**Referensi:** [PRD_BRImo.md](../PRD/PRD_BRImo.md) v1.0
**Status:** Draft

> Konsep akademik, bukan produk resmi BRI. Versi 1.1: informasi yang sebelumnya belum pasti telah diputuskan penulis.

---

# 1. UX Overview

## 1.1 UX Objective

Membantu pengguna merasa yakin sebelum mengonfirmasi transfer melalui halaman konfirmasi yang jelas, terstruktur, dan mudah diperiksa, serta memberi kepastian status setelah transfer.

Pengguna harus dapat:

- Melihat nama penerima, nomor rekening, bank, nominal, biaya, dan total sebelum konfirmasi.
- Memperbaiki rekening atau nominal tanpa kehilangan data.
- Mengetahui status transaksi: berhasil, gagal, atau diproses.
- Melihat bukti dan riwayat transaksi.

## 1.2 UX Design Principles

1. **Clarity:** Informasi yang menentukan kebenaran transaksi paling menonjol.
2. **Verifiability:** Setiap data penting mudah dicocokkan dengan niat pengguna.
3. **User Control:** Pengguna dapat kembali dan mengubah data sebelum konfirmasi.
4. **Reassurance:** Pesan menyatakan kapan transaksi belum diproses dan apa hasilnya.
5. **Safe Recovery:** Saat status belum pasti, pengguna diarahkan memeriksa status, bukan mengulang transaksi.

---

# 2. User Context

## 2.1 Primary Persona

Dimas Pratama, 21 tahun, mahasiswa. Memeriksa ulang penerima dan nominal sebelum konfirmasi; tidak nyaman ketika status transaksi belum jelas (PRD bagian 3, Worksheet 6).

## 2.2 User Goals

- Mengirim uang kepada orang yang benar dengan nominal yang benar.
- Merasa yakin sebelum menekan Konfirmasi.
- Mengetahui hasil transaksi dengan pasti.

## 2.3 Main User Scenario

Pengguna membuka beranda, memilih Transfer, memasukkan rekening tujuan, mengisi nominal, memeriksa halaman konfirmasi, mengonfirmasi, menyelesaikan verifikasi simulasi, lalu melihat status dan bukti transaksi.

---

# 3. Information Architecture (IA)

> Worksheet 9 (IA) dilewati. Struktur di bawah diturunkan dari prototype Worksheet 12 sebelumnya dan disetujui penulis.

## 3.1 Sitemap

```
[BERANDA]
├── Transfer
│   ├── Menu Transfer (pilih tujuan)
│   ├── Input Detail Transfer
│   ├── Konfirmasi Detail Transfer
│   ├── Verifikasi (simulasi)
│   └── Status Transaksi (Berhasil | Belum Pasti)
│       └── Bukti Transaksi
└── Riwayat Transaksi
```

## 3.2 Primary Navigation

- Tombol Transfer di beranda.
- Tombol kembali pada setiap halaman transfer.
- Tombol Ubah pada kartu di halaman konfirmasi.
- Tombol Kembali ke Beranda pada halaman status dan bukti.

---

# 4. Page Specification

## PAGE-01: Beranda

### Purpose
Titik awal aktivitas transfer.

### Information Components
Header aplikasi, sapaan pengguna, kartu saldo, menu utama (Transfer ditonjolkan), pengingat "Periksa sebelum konfirmasi", navigasi bawah.

### User Actions
Membuka Transfer; menyembunyikan atau menampilkan saldo.

### Expected Outcome
Pengguna masuk ke Menu Transfer.

## PAGE-02: Menu Transfer

### Purpose
Menentukan tujuan transfer.

### Information Components
Pilihan Sesama BRI atau Antarbank, pilihan bank (antarbank), input nomor rekening dengan pengelompokan 4 digit, daftar penerima tersimpan, tombol Lanjutkan.

### User Actions
Mengisi rekening atau memilih penerima tersimpan; menekan Lanjutkan.

### Expected Outcome
Pengguna masuk ke Input Detail. Rekening kosong atau kurang dari 10 digit menampilkan pesan kesalahan.

## PAGE-03: Input Detail Transfer

### Purpose
Mengisi nominal dan keterangan.

### Information Components
Kartu rekening penerima (nama, nomor, bank) dengan tombol Ubah, input nominal, nominal cepat, keterangan opsional, biaya administrasi, estimasi total, tombol Lanjutkan ke Konfirmasi.

### User Actions
Mengisi nominal; memilih nominal cepat; mengubah rekening.

### Expected Outcome
Pengguna masuk ke Konfirmasi hanya jika nominal valid.

## PAGE-04: Konfirmasi Detail Transfer (halaman utama)

### Purpose
Memastikan seluruh detail benar sebelum konfirmasi.

### Information Components
Banner "transaksi belum diproses"; kartu Penerima (nama, rekening, bank); kartu Nominal (angka besar dan terbilang); kartu rincian (biaya, keterangan, sumber dana, total); tombol Ubah Data dan Konfirmasi.

### User Actions
Memeriksa informasi; Ubah pada kartu Penerima atau Nominal; Ubah Data; Konfirmasi.

### Expected Outcome
Pengguna yakin lalu menekan Konfirmasi, atau kembali memperbaiki tanpa kehilangan data.

## PAGE-05: Verifikasi (simulasi)

### Purpose
Mensimulasikan tahap akhir transaksi tanpa data perbankan asli.

### Information Components
Ikon keamanan, ringkasan penerima, rekening, dan total, area simulasi verifikasi, catatan mode simulasi, tombol Kembali & Periksa Lagi.

### User Actions
Mengetuk area verifikasi; kembali ke Konfirmasi.

### Expected Outcome
Pengguna masuk ke Status Transaksi.

## PAGE-06: Status Transaksi

### Purpose
Memberi kepastian hasil transaksi.

### Information Components
Varian Berhasil: ikon berhasil, nominal, penerima, rekening, bank, waktu, nomor referensi, tombol Lihat Detail dan Kembali ke Beranda.
Varian Belum Pasti: ikon jam, penjelasan, peringatan "jangan ulangi transfer dulu", tiga langkah, ringkasan, tombol Periksa Status Transaksi, Hubungi Bantuan, Kembali ke Beranda.

### User Actions
Lihat Detail; Periksa Status; Hubungi Bantuan; Kembali ke Beranda.

### Expected Outcome
Pengguna mengetahui hasil dan langkah berikutnya.

## PAGE-07: Bukti Transaksi

### Purpose
Menampilkan ringkasan lengkap transaksi.

### Information Components
Status, nominal, rincian lengkap, nomor referensi, tombol Simpan Bukti dan Kembali ke Beranda.

### User Actions
Menyimpan bukti (simulasi); kembali.

### Expected Outcome
Pengguna memiliki bukti transaksi.

## PAGE-08: Riwayat Transaksi

### Purpose
Melihat kembali status dan detail transaksi sebelumnya (FR-06).

### Information Components
Belum dirancang. Perlu keputusan scope dan desain.

---

# 5. User Flow

## 5.1 Flow: Transfer dengan Konfirmasi

1. Beranda → pilih Transfer.
2. Pilih jenis transfer dan isi rekening tujuan.
3. Sistem menampilkan nama penerima.
4. Isi nominal (dan keterangan).
5. Halaman Konfirmasi: periksa data.
6. Jika ada kesalahan: Ubah → perbaiki → kembali ke Konfirmasi.
7. Jika benar: Konfirmasi → Verifikasi simulasi.
8. Status Transaksi → Lihat Detail (Bukti) atau Kembali ke Beranda.

## 5.2 Flow: Status Belum Pasti

1. Verifikasi selesai dengan status belum pasti.
2. Pengguna membaca penjelasan dan peringatan.
3. Periksa Status Transaksi (dapat diulang).
4. Status terkonfirmasi berhasil → Status Berhasil; atau Hubungi Bantuan.

Tidak ada tombol pengulangan transaksi pada alur ini.

---

# 6. User Interaction Requirements

Detail perilaku ada di [INTERACTION-SPEC.md](INTERACTION-SPEC.md).

---

# 7. Responsive Experience

Fokus pada mobile (lebar 390 px pada prototype). Pada tablet dan desktop, aplikasi tampil di tengah dengan lebar tetap seperti ponsel.

---

# 8. Empty States

- Riwayat Transaksi kosong: tampil pesan bahwa belum ada transaksi.
- Daftar penerima tersimpan kosong: bagian disembunyikan.

---

# 9. UX Error Prevention

- Nama penerima, rekening, bank, dan nominal ditampilkan sebelum konfirmasi.
- Nominal ditampilkan besar beserta terbilang.
- Tombol Lanjutkan nonaktif sampai nominal valid.
- Banner menyatakan transaksi belum diproses sebelum verifikasi.
- Tidak ada tombol ulang pada status belum pasti.

---

# 10. UX Deliverables

- Wireframe dan desain visual semua halaman.
- Prototype interaktif.
- Dokumen UX Skill (UX-SPEC, DESIGN-SYSTEM, INTERACTION-SPEC, ACCEPTANCE-CRITERIA) dan AGENTS.md.

---

# 11. UX Design Constraints

- Tidak mengklaim sebagai desain resmi BRI.
- Tidak meminta PIN, OTP, password, atau data perbankan asli.
- Tidak menambah fitur di luar kebutuhan Worksheet 1–8.
- Hasil usability test belum tersedia; tidak ada Worksheet usability test pada proyek ini.
