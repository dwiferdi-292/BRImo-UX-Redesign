# ACCEPTANCE CRITERIA

## Project: BRImo UX Redesign — Konfirmasi Transfer

**Version:** 1.0
**Status:** Draft

**References:**

- [PRD_BRImo.md](../PRD/PRD_BRImo.md) v1.0
- [UX-SPEC.md](UX-SPEC.md) v1.0
- [DESIGN-SYSTEM.md](DESIGN-SYSTEM.md) v1.0
- [INTERACTION-SPEC.md](INTERACTION-SPEC.md) v1.0

---

# 1. Purpose

Mendefinisikan kriteria penerimaan agar aplikasi:

1. Memenuhi kebutuhan pengguna di PRD (berasal dari Worksheet 8).
2. Mengikuti alur UX-SPEC.
3. Memakai komponen visual DESIGN-SYSTEM.
4. Berperilaku sesuai INTERACTION-SPEC.
5. Dapat diuji.

# 2. Acceptance Criteria Convention

Setiap kriteria memiliki ID, Requirement, Expected Result, Priority, dan Verification.

| Priority | Arti |
|---|---|
| Must Have | Wajib terpenuhi |
| Should Have | Penting, tidak menghalangi fungsi utama |
| Could Have | Peningkatan jika waktu memungkinkan |

Verification: Manual Test, Automated Test, Visual Inspection.

---

# 3. Functional Acceptance Criteria

## 3.1 Transfer Destination

### AC-001 — Navigasi ke Transfer
**Priority:** Must Have · **Verification:** Manual Test
Given pengguna di Beranda, When menekan Transfer, Then Menu Transfer terbuka.

### AC-002 — Validasi Rekening
**Priority:** Must Have · **Verification:** Manual Test, Automated Test
Given rekening kosong atau kurang dari 10 digit, When menekan Lanjutkan, Then pesan kesalahan tampil dan pengguna tetap di halaman.

## 3.2 Amount Input

### AC-003 — Validasi Nominal
**Priority:** Must Have · **Verification:** Manual Test, Automated Test
Given nominal kosong atau di bawah batas, When pengguna melihat tombol, Then tombol Lanjutkan ke Konfirmasi nonaktif.

### AC-004 — Nama Penerima Tampil
**Priority:** Must Have · **Verification:** Manual Test
Given rekening valid, When Input Detail terbuka, Then nama penerima, nomor rekening, dan bank tampil (FR-02).

## 3.3 Confirmation

### AC-005 — Ringkasan Lengkap
**Priority:** Must Have · **Verification:** Manual Test, Visual Inspection
Given pengguna di halaman Konfirmasi, Then tampil nama penerima, nomor rekening, bank, nominal, biaya, keterangan, sumber dana, dan total (FR-01).

### AC-006 — Penekanan Visual
**Priority:** Must Have · **Verification:** Visual Inspection
Then nama penerima dan nominal berukuran paling besar di halaman dan terbaca jelas (FR-03, NFR-01).

### AC-007 — Perbaikan Data
**Priority:** Must Have · **Verification:** Manual Test, Automated Test
Given pengguna di Konfirmasi, When menekan Ubah atau Ubah Data, Then kembali ke halaman terkait dan data sebelumnya tetap terisi (FR-04).

### AC-008 — Belum Diproses
**Priority:** Must Have · **Verification:** Manual Test
Then banner menyatakan transaksi belum diproses, dan transaksi baru berlanjut setelah Konfirmasi dan verifikasi.

## 3.4 Verification and Status

### AC-009 — Verifikasi Simulasi
**Priority:** Must Have · **Verification:** Manual Test
When Konfirmasi ditekan, Then tahap Verifikasi terbuka tanpa meminta PIN, OTP, atau password.

### AC-010 — Status Berhasil
**Priority:** Must Have · **Verification:** Manual Test
Given verifikasi selesai pada skenario berhasil, Then tampil penerima, nominal, rekening, bank, waktu, dan nomor referensi (FR-05).

### AC-011 — Status Belum Pasti
**Priority:** Must Have · **Verification:** Manual Test
Given skenario belum pasti, Then tampil penjelasan sederhana, peringatan agar tidak mengulang transfer, dan tombol Periksa Status Transaksi (FR-07).

### AC-012 — Tanpa Tombol Ulang
**Priority:** Must Have · **Verification:** Visual Inspection
Then halaman status belum pasti tidak memiliki tombol untuk mengulang transaksi.

### AC-013 — Bukti Transaksi
**Priority:** Must Have · **Verification:** Manual Test
When Lihat Detail ditekan, Then Bukti Transaksi menampilkan rincian lengkap dan nomor referensi.

### AC-014 — Kembali ke Beranda
**Priority:** Must Have · **Verification:** Manual Test
When Kembali ke Beranda ditekan dari halaman status atau bukti, Then Beranda terbuka.

## 3.5 History **[PERLU DIKONFIRMASI]**

### AC-015 — Riwayat Transaksi
**Priority:** Should Have · **Verification:** Manual Test
Then riwayat menampilkan status dan detail transaksi sebelumnya (FR-06). Kriteria bergantung pada keputusan scope.

---

# 4. UX and UI Criteria

### AC-020 — Konsistensi Desain
**Priority:** Must Have · **Verification:** Visual Inspection
Warna, huruf, dan komponen mengikuti DESIGN-SYSTEM.

### AC-021 — Bahasa Sederhana
**Priority:** Must Have · **Verification:** Manual Test
Pesan status dan kesalahan menggunakan bahasa mudah dipahami (NFR-02).

### AC-022 — Mobile
**Priority:** Must Have · **Verification:** Manual Test
Aplikasi dapat digunakan pada layar smartphone (NFR-03).

---

# 5. Non-Functional Criteria

### AC-030 — Tanpa Data Perbankan Asli
**Priority:** Must Have · **Verification:** Manual Test
Aplikasi tidak memproses transaksi nyata, tidak mengakses API bank, dan tidak meminta data rahasia (NFR-04).

---

# 6. Test Scenarios and Verification

| Skenario | Langkah | Hasil yang diharapkan |
|---|---|---|
| Alur berhasil | Beranda → Transfer → isi rekening → nominal → Konfirmasi → Verifikasi | Status Berhasil lalu Bukti |
| Perbaikan | Konfirmasi → Ubah → ubah nominal → kembali | Data baru tampil di Konfirmasi |
| Belum pasti | Pilih skenario belum pasti → ulangi alur | Status Belum Pasti tanpa tombol ulang |
| Validasi | Rekening pendek, nominal kecil | Pesan kesalahan, tombol nonaktif |

---

# 7. Release Acceptance Sign-off

| Item | Status |
|---|---|
| Seluruh kriteria Must Have terpenuhi | **[PERLU DIKONFIRMASI]** |
| Hasil pengujian | **[PERLU DIKONFIRMASI]** belum ada data pengujian |
| Catatan isu | **[PERLU DIKONFIRMASI]** |
