# AGENTS.md

# AI Coding Agent Instructions

## Project: BRImo UX Redesign — Konfirmasi Transfer

**Version:** 1.0

---

# 1. Project Context

Proyek ini adalah konsep akademik (mata kuliah Rekayasa Interaksi) yang merancang ulang halaman konfirmasi transfer pada pengalaman mobile banking terinspirasi BRImo. Masalah UX: pengguna ragu saat memeriksa nama penerima, nomor rekening, nominal, dan biaya sebelum menekan konfirmasi.

Hal yang harus dipahami:

- Ini **bukan** produk resmi BRI dan tidak terhubung ke layanan bank.
- Jangan memproses transaksi sungguhan, memanggil API bank, atau meminta PIN, OTP, password, atau data perbankan asli.
- Data pada aplikasi adalah data contoh buatan di sisi klien.

# 2. Mandatory Documentation

Baca seluruh dokumen sebelum menulis kode:

1. [PRD/PRD_BRImo.md](PRD/PRD_BRImo.md)
2. [UX-Skill/UX-SPEC.md](UX-Skill/UX-SPEC.md)
3. [UX-Skill/DESIGN-SYSTEM.md](UX-Skill/DESIGN-SYSTEM.md)
4. [UX-Skill/INTERACTION-SPEC.md](UX-Skill/INTERACTION-SPEC.md)
5. [UX-Skill/ACCEPTANCE-CRITERIA.md](UX-Skill/ACCEPTANCE-CRITERIA.md)

Jika dokumen bertentangan, urutan prioritas: PRD → UX-SPEC → INTERACTION-SPEC → DESIGN-SYSTEM → ACCEPTANCE-CRITERIA.

# 3. Core Development Principles

## 3.1 Specification-Driven Development
Implementasikan hanya yang tertulis di dokumen. Jangan menambah fitur.

## 3.2 UX-First Implementation
Halaman Konfirmasi adalah pusat. Nama penerima dan nominal harus paling menonjol; pengguna dapat memperbaiki data tanpa kehilangan input.

## 3.3 Design Consistency
Gunakan token dan komponen pada DESIGN-SYSTEM.md. Jangan membuat gaya baru.

## 3.4 Functional Completeness
Semua tombol pada alur utama harus berfungsi. Jangan menyisakan tombol mati pada alur yang didokumentasikan.

# 4. Development Workflow

## Phase 1 — Analyze
Baca dokumen wajib. Daftar bagian bertanda **[PERLU DIKONFIRMASI]** dan catat sebagai asumsi.

## Phase 2 — Project Setup
Siapkan proyek web mobile (HTML/CSS/JS atau framework ringan). Catat pilihan teknologi di README.

## Phase 3 — Design Implementation
Implementasikan token, komponen, dan layout sesuai DESIGN-SYSTEM.

## Phase 4 — Functional Implementation
Implementasikan alur: Beranda → Menu Transfer → Input Detail → Konfirmasi → Verifikasi simulasi → Status → Bukti. Tambahkan skenario status belum pasti.

## Phase 5 — Validation
Jalankan seluruh skenario ACCEPTANCE-CRITERIA dan catat hasilnya.

# 5. Feature Implementation Rules

## 5.1 Transfer Destination
Validasi rekening minimal 10 digit; kelompokkan per 4 digit; hanya angka.

## 5.2 Amount Input
Format Rp dengan pemisah ribuan; tombol lanjut nonaktif jika nominal tidak valid.

## 5.3 Confirmation Page
Tampilkan semua komponen FR-01. Sediakan Ubah pada kartu Penerima dan Nominal serta tombol Ubah Data. Data harus tetap tersimpan saat kembali.

## 5.4 Transaction Status
Sediakan status Berhasil dan Belum Pasti. **Jangan menyediakan tombol pengulangan transaksi** pada status Belum Pasti.

## 5.5 Data Persistence
Data alur disimpan di state sisi klien selama sesi. Persistensi lintas sesi **[PERLU DIKONFIRMASI]**.

# 6. Component Architecture

Pisahkan: layar (Beranda, Menu Transfer, Input Detail, Konfirmasi, Verifikasi, Status, Bukti), komponen bersama (kartu, tombol, input, baris rincian, banner, toast, bottom sheet), dan state alur. Struktur folder rinci mengikuti pilihan teknologi dan dicatat di README.

# 7. Code Quality Rules

- Kode terbaca, bernama jelas, tanpa duplikasi berlebihan.
- Tidak ada rahasia atau kredensial di repository.
- Tidak ada pemanggilan jaringan ke layanan bank.
- Pesan antarmuka berbahasa Indonesia sederhana.

# 8. Responsive Design Rules

Prioritas layar smartphone (acuan 390 px). Perilaku tablet dan desktop **[PERLU DIKONFIRMASI]**.

# 9. Testing Requirements

## Functional Testing
Seluruh alur dan tombol pada alur utama.

## Validation Testing
Rekening kosong atau pendek, nominal kosong atau kecil, nominal melebihi saldo contoh.

## Status Testing
Skenario Berhasil dan Belum Pasti, termasuk tidak adanya tombol ulang.

## Navigation / State Testing
Ubah dari Konfirmasi mempertahankan data; kembali ke Beranda mereset alur.

## Responsive Testing
Tampilan pada lebar smartphone.

# 10. Visual Validation

Bandingkan layar dengan DESIGN-SYSTEM: token warna, ukuran huruf nominal dan nama penerima, spasi kartu, bilah aksi bawah.

# 11. Scope Control

Dilarang: fitur di luar PRD, integrasi bank, autentikasi sungguhan, penyimpanan data pribadi nyata, dan pengerjaan Worksheet 9–11.

# 12. Decision and Assumption Management

Catat setiap keputusan teknis dan asumsi di README atau CHANGELOG. Jangan menyatakan asumsi sebagai fakta. Bagian **[PERLU DIKONFIRMASI]** tidak boleh diputuskan sendiri tanpa dicatat.

# 13. Completion Report

Setelah selesai, laporkan:

## Implementation Summary
Apa yang dibangun dan teknologi yang dipakai.

## Acceptance Criteria Status
Status setiap AC (lulus, gagal, belum diuji).

## Known Issues
Masalah yang diketahui.

## Next Steps
Langkah lanjutan yang disarankan.

# 14. Final Instruction

Ikuti dokumen, jaga kejujuran status pekerjaan, dan jangan mengklaim sesuatu selesai sebelum diuji.
