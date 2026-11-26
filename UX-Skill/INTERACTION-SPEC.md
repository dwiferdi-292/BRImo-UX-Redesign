# INTERACTION SPECIFICATION

## Project: BRImo UX Redesign — Konfirmasi Transfer

**Version:** 1.0
**Status:** Draft
**References:**

- [PRD_BRImo.md](../PRD/PRD_BRImo.md) v1.0
- [UX-SPEC.md](UX-SPEC.md) v1.0
- [DESIGN-SYSTEM.md](DESIGN-SYSTEM.md) v1.0

> Perilaku berasal dari prototype Worksheet 12 yang telah diuji alurnya. Hal yang tidak ada di sumber diputuskan penulis dan ditulis sebagai asumsi.

---

# 1. Interaction Overview

## 1.1 Objective

Mendefinisikan perilaku interaksi alur transfer agar implementasi konsisten, dapat diprediksi, dan membantu pengguna memeriksa detail sebelum konfirmasi.

## 1.2 Interaction Principles

1. Immediate Feedback: setiap tindakan mendapat respons.
2. Predictability: komponen berperilaku konsisten.
3. Error Prevention: kesalahan dicegah sebelum konfirmasi.
4. User Control: pengguna dapat kembali dan memperbaiki data.
5. State Consistency: data yang diisi tetap sama di semua halaman.
6. Safe Recovery: status belum pasti tidak mendorong pengulangan transaksi.

---

# 2. Global Interaction Behavior

## 2.1 Navigation

| Action | Expected Behavior |
|---|---|
| Ketuk Transfer (beranda) | Membuka Menu Transfer |
| Ketuk tombol kembali | Kembali ke halaman sebelumnya |
| Ketuk Ubah (kartu Penerima) | Kembali ke Menu Transfer, data tetap |
| Ketuk Ubah (kartu Nominal) atau Ubah Data | Kembali ke Input Detail, data tetap |
| Ketuk Kembali ke Beranda | Membuka Beranda |
| Ketuk menu lain di beranda | Toast bahwa menu tidak tersedia di prototype |

## 2.2 Global Loading

Proses verifikasi simulasi dan pemeriksaan status menampilkan indikator proses dan menonaktifkan tombol sementara.

## 2.3 Global Error Handling

Pesan kesalahan memakai bahasa sederhana dan menyebut cara memperbaikinya. Kegagalan jaringan nyata tidak dicakup (prototype tidak memakai jaringan).

---

# 3. Transfer Destination Interaction (Menu Transfer)

## 3.1 Flow

1. Pengguna memilih Sesama BRI atau Antarbank.
2. Jika Antarbank, pengguna memilih bank tujuan.
3. Pengguna mengisi nomor rekening atau memilih penerima tersimpan.
4. Pengguna menekan Lanjutkan.

## 3.2 Validasi

| Kondisi | Perilaku |
|---|---|
| Rekening kosong | Pesan "Nomor rekening wajib diisi." |
| Kurang dari 10 digit | Pesan "Nomor rekening terlalu pendek. Minimal 10 digit." |
| Valid | Lanjut ke Input Detail |

Input hanya menerima angka, maksimal 16 digit, dikelompokkan per 4 digit.

---

# 4. Amount Input Interaction (Input Detail)

1. Sistem menampilkan nama penerima berdasarkan rekening (disimulasikan).
2. Pengguna mengisi nominal atau memilih nominal cepat.
3. Input berformat Rp dengan pemisah ribuan.
4. Biaya administrasi dan estimasi total diperbarui.

| Kondisi | Perilaku |
|---|---|
| Nominal kosong atau kurang dari Rp 10.000 | Tombol Lanjutkan nonaktif; pesan batas minimum |
| Nominal + biaya melebihi saldo | Pesan saldo tidak mencukupi; tombol nonaktif |
| Valid | Tombol aktif |

Batas minimum dan biaya pada prototype adalah asumsi proyek akademik.

---

# 5. Confirmation Page Interaction (utama)

## 5.1 Trigger

Pengguna menekan Lanjutkan ke Konfirmasi.

## 5.2 Behavior

1. Halaman menampilkan penerima, rekening, bank, nominal beserta terbilang, biaya, keterangan, sumber dana, total.
2. Banner menyatakan transaksi belum diproses.
3. Ubah pada kartu mengembalikan ke halaman terkait; data tidak hilang.
4. Ubah Data mengembalikan ke Input Detail.
5. Konfirmasi membuka tahap Verifikasi.

## 5.3 Rules

- Tombol Konfirmasi berada di bilah bawah tetap, tidak menutupi isi.
- Tidak ada transaksi diproses pada halaman ini.

---

# 6. Verification Interaction (simulasi)

1. Pengguna mengetuk area verifikasi.
2. Muncul animasi dan indikator progres sekitar 1,5 detik.
3. Hasil menuju Status Berhasil atau Status Belum Pasti sesuai skenario simulasi.
4. Tombol Kembali & Periksa Lagi kembali ke Konfirmasi.

Tidak ada input PIN, OTP, atau password.

---

# 7. Transaction Status Interaction

## 7.1 Berhasil

- Menampilkan penerima, nominal, rekening, bank, waktu, nomor referensi.
- Lihat Detail membuka Bukti Transaksi.
- Kembali ke Beranda membuka Beranda.

## 7.2 Belum Pasti

- Menampilkan penjelasan, peringatan "jangan ulangi transfer dulu", tiga langkah, ringkasan.
- Periksa Status Transaksi: pemeriksaan pertama menampilkan "masih diproses"; pemeriksaan kedua menghasilkan Status Berhasil. (Simulasi.)
- Hubungi Bantuan membuka lembar bantuan simulasi.
- **Tidak ada tombol pengulangan transaksi.**

## 7.3 Gagal

Keputusan penulis: layar status gagal terpisah tidak dibuat pada cakupan ini; kondisi tidak pasti ditangani oleh status Belum Pasti.

---

# 8. Receipt Interaction

- Tombol kembali menuju Status.
- Simpan Bukti hanya menampilkan toast simulasi.
- Kembali ke Beranda membuka Beranda.

---

# 9. History Interaction

Riwayat transaksi (FR-06): daftar transaksi terbaru di atas. Ketuk transaksi berhasil membuka Bukti Transaksi; ketuk transaksi yang masih diproses membuka Status Belum Pasti. Jika kosong, tampil pesan "Belum ada transaksi." Tombol Kembali ke Beranda tersedia.

---

# 10. Feedback and Edge Cases

| Kasus | Perilaku |
|---|---|
| Pengguna kembali dari Konfirmasi | Data rekening dan nominal tetap |
| Pengguna menekan tombol saat proses berjalan | Diabaikan sampai proses selesai |
| Rekening sama dengan penerima tersimpan | Nama diisi otomatis dari data tersimpan |
| Menu yang belum dibuat | Toast informatif |
