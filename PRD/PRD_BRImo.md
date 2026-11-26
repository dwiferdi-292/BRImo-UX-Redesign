# PRODUCT REQUIREMENTS DOCUMENT (PRD) — BRImo UX Redesign

**Versi:** 1.1
**Status:** Draft
**Mata kuliah:** Rekayasa Interaksi (UX)
**Penulis:** Muchammad Dwi Ferdi Ilham Arifin (NIM 202310370311292)
**Produk:** BRImo (konsep akademik, bukan produk resmi BRI)
**Platform:** Mobile

> Versi 1.1 (27 November 2026): seluruh tanda yang sebelumnya menandai informasi belum pasti telah diputuskan oleh penulis dan diisi pada tempatnya. Keputusan yang bukan berasal dari Worksheet 1–8 ditulis sebagai asumsi proyek akademik. Sumber utama: Worksheet 1–8 (khususnya Worksheet 8 untuk User Need).

---

## 1. Product Overview

### 1.1 Latar Belakang

BRImo adalah aplikasi perbankan seluler milik BRI yang digunakan nasabah untuk memeriksa saldo dan mutasi, melakukan transfer, pembayaran, dan aktivitas perbankan lain melalui smartphone (Worksheet 1).

Pada proses transfer, pengguna perlu memastikan bahwa nama penerima, nomor rekening tujuan, nominal, dan biaya transaksi sudah benar sebelum menekan tombol konfirmasi. Karena transaksi berkaitan dengan uang, pengguna cenderung memeriksa ulang informasi tersebut dan dapat merasa ragu atau khawatir salah transfer (Worksheet 1, 2, 5, 6).

Proyek **BRImo UX Redesign** merancang ulang pengalaman memeriksa detail transfer sebelum konfirmasi, serta kejelasan status transaksi setelah transfer.

> Catatan: proyek ini adalah konsep akademik (mata kuliah Rekayasa Interaksi). Proyek ini bukan produk resmi BRI dan tidak terhubung ke layanan perbankan.

### 1.2 Product Vision

Membantu pengguna merasa yakin sebelum mengonfirmasi transfer, dengan menyajikan detail transaksi yang jelas, terstruktur, dan mudah diperiksa. Tujuannya bukan sekadar mempercepat transfer, tetapi memberi kepastian sebelum dan sesudah konfirmasi.

### 1.3 Target Pengguna

Nasabah BRImo yang menggunakan smartphone dan melakukan transfer, khususnya mahasiswa dan pekerja yang terbiasa bertransaksi digital (Worksheet 1 dan 3).

Pihak terkait:

| Kategori | Pihak |
|---|---|
| Core user | Nasabah BRImo yang melakukan transfer |
| Secondary user | Penerima transfer |
| Stakeholder | BRI sebagai penyedia layanan BRImo |
| System / organisasi | Sistem perbankan BRI dan layanan BRImo |

---

## 2. User Problem

Masalah UX yang dipilih (Worksheet 1): **kurangnya kepastian dan kejelasan informasi sebelum konfirmasi transaksi** (*Transaction Confirmation Uncertainty*) pada alur transfer.

Temuan utama dari Worksheet 5–7:

1. Pengguna merasa khawatir salah transfer sehingga memeriksa ulang nama penerima dan nominal sebelum konfirmasi.
2. Pengguna kadang ragu apakah nama dan nomor rekening penerima sudah benar.
3. Pengguna yang terburu-buru khawatir ada detail yang terlewat.
4. Pengguna membutuhkan kepastian status setelah transfer, dan merasa tidak nyaman ketika status belum jelas.

> Keputusan penulis: kutipan pengguna U1–U5 pada Worksheet 5 berlabel "contoh" dan berasal dari "simulasi jawaban pengguna". Temuan di atas diperlakukan sebagai hipotesis awal dan tidak dinyatakan sebagai hasil wawancara pengguna nyata.

### Problem Statement

Nasabah BRImo membutuhkan kepastian terhadap detail transaksi sebelum melakukan konfirmasi karena kesulitan memastikan bahwa tujuan transfer, nominal, dan detail transaksi sudah benar, sehingga timbul keraguan dan risiko kesalahan transfer (Worksheet 2).

### Design Challenge (HMW)

*How might we* membantu pengguna memastikan detail transaksi dengan mudah *so that* pengguna lebih yakin sebelum melakukan konfirmasi?

---

## 3. User Persona

**Nama:** Dimas Pratama
**Usia:** 21 tahun
**Pekerjaan:** Mahasiswa

### Karakteristik dan Perilaku

- Menggunakan BRImo untuk memeriksa saldo, transfer ke teman atau keluarga, dan melihat mutasi.
- Memeriksa ulang detail penerima dan nominal sebelum konfirmasi.
- Memeriksa bukti transaksi setelah transfer.

### Goals

- Transfer melalui BRImo dengan cepat tanpa perlu ke ATM.
- Memastikan nama penerima, nomor rekening, dan nominal benar sebelum menyelesaikan transaksi.

### Pain Points

- Khawatir salah memasukkan nomor rekening atau nominal.
- Butuh waktu tambahan untuk memeriksa ulang detail.
- Tidak nyaman ketika status transaksi belum jelas.

### Needs

- Ringkasan transaksi yang jelas, terstruktur, dan mudah diperiksa sebelum konfirmasi.
- Status transaksi yang transparan: berhasil, gagal, atau masih diproses.

> Sumber persona: sintesis Worksheet 1–5. Menurut Worksheet 6, persona ini berbasis wawancara yang direncanakan atau disimulasikan. Keputusan penulis: persona diperlakukan sebagai hipotesis kerja dan belum divalidasi dengan pengguna nyata.

---

## 4. Product Goals

Produk memiliki tujuan sebagai berikut:

1. Menampilkan ringkasan detail transfer yang jelas sebelum konfirmasi.
2. Membantu pengguna memastikan nama penerima, nomor rekening tujuan, nominal, dan biaya.
3. Memberi pengguna jalur yang mudah untuk memperbaiki informasi sebelum konfirmasi.
4. Memberi kepastian status transaksi (berhasil, gagal, atau diproses) setelah transfer.
5. Menyediakan akses ke riwayat dan bukti transaksi.

### Success Metrics

| Indikator | Target Awal |
|---|---|
| Halaman konfirmasi menampilkan nama penerima, rekening, bank, nominal, biaya, dan total | 100% transaksi |
| Pengguna dapat kembali memperbaiki data dari halaman konfirmasi tanpa kehilangan data | 100% |
| Status transaksi ditampilkan setelah proses konfirmasi | 100% transaksi |
| Tingkat keyakinan pengguna sebelum konfirmasi | Belum diukur pada tahap ini (tidak ada usability test pada Worksheet 1–12); diukur pada pengujian pengguna berikutnya |
| Kesalahan transfer akibat salah input | Belum diukur; tidak ada data dasar pada sumber |

Catatan: target adalah hipotesis awal dan perlu divalidasi melalui pengujian pengguna. Hasil usability test belum tersedia (Worksheet 13 kosong).

---

## 5. Functional Requirements

### FR-01: Ringkasan Transaksi Sebelum Konfirmasi

Sistem harus menampilkan ringkasan transaksi sebelum pengguna mengonfirmasi (Worksheet 8, baris 1).

Ringkasan memuat:

- Nama penerima.
- Nomor rekening tujuan.
- Bank tujuan.
- Nominal transfer.
- Biaya administrasi.
- Total transaksi.
- Keterangan (jika diisi pengguna).

### FR-02: Nama Penerima Berdasarkan Nomor Rekening

Sistem harus menampilkan nama penerima berdasarkan nomor rekening yang dimasukkan sebelum transaksi dikonfirmasi (Worksheet 8, baris 2).

### FR-03: Tampilan Nominal Transfer

Sistem harus menampilkan nominal transfer secara jelas pada halaman ringkasan sebelum konfirmasi (Worksheet 8, baris 3).

### FR-04: Perbaikan Informasi Sebelum Konfirmasi

Pengguna dapat kembali dari halaman konfirmasi untuk mengubah rekening tujuan atau nominal, dan data yang sudah diisi tetap tersimpan.

> Dasar: User Story 2 dan alur perbaikan pada pekerjaan Worksheet 12 sebelumnya. Tidak tercantum eksplisit sebagai baris Worksheet 8. Keputusan penulis: dimasukkan sebagai requirement turunan karena mendukung tujuan pengguna memastikan detail sebelum konfirmasi.

### FR-05: Status Transaksi

Sistem harus menampilkan status transaksi berhasil, gagal, atau sedang diproses setelah konfirmasi, serta menyediakan bukti transaksi (Worksheet 8, baris 4).

### FR-06: Riwayat dan Bukti Transaksi

Sistem harus menyediakan halaman riwayat transaksi yang memungkinkan pengguna melihat status dan detail transaksi sebelumnya (Worksheet 8, baris 5).

> Keputusan penulis: riwayat transaksi masuk scope karena merupakan User Story 5 pada Worksheet 8. Riwayat berisi contoh transaksi sebelumnya ditambah transaksi yang dibuat pada sesi berjalan.

### FR-07: Penanganan Transaksi Bermasalah

Jika status transaksi belum pasti atau gagal, sistem menampilkan penjelasan sederhana dan langkah berikutnya. Sistem tidak menyediakan tombol pengulangan transaksi sebelum pengguna memeriksa status transaksi sebelumnya.

> Dasar: User Story 4, 5 dan opportunity "petunjuk aman jika status belum pasti" pada User Journey (Worksheet 7). Detail perilakunya berasal dari pekerjaan Worksheet 12 sebelumnya.

---

## 6. Non-Functional Requirements

> Keputusan penulis: Worksheet 1–8 tidak memuat kebutuhan non-fungsional. Poin berikut adalah turunan langsung dari UX Requirement Worksheet 8 dan batasan proyek akademik, dan disetujui penulis.

### NFR-01: Keterbacaan

Informasi transaksi harus terstruktur, mudah dibaca, dan mudah diperiksa; nama penerima dan nominal memiliki penekanan visual (Worksheet 8).

### NFR-02: Bahasa

Pesan status dan kesalahan menggunakan bahasa sederhana dan mudah dipahami (Worksheet 8).

### NFR-03: Platform

Mobile web yang berfungsi pada layar smartphone.

### NFR-04: Keamanan Data Proyek

Prototype tidak memproses transaksi sungguhan, tidak terhubung ke API bank, dan tidak meminta PIN, OTP, password, atau data perbankan asli.

---

## 7. Business Rules

> Keputusan penulis: aturan bisnis BRImo yang sebenarnya (batas transfer, biaya, jam layanan) tidak tersedia pada sumber dan tidak dibuat sendiri. Aturan berikut hanya yang mendukung alur konfirmasi.

1. Transaksi tidak diproses sebelum pengguna melewati halaman konfirmasi dan tahap verifikasi.
2. Nama penerima, nomor rekening, bank, nominal, biaya, dan total ditampilkan sebelum konfirmasi.
3. Pengguna dapat mengubah rekening atau nominal dari halaman konfirmasi tanpa kehilangan data.
4. Setiap transaksi memiliki satu status: berhasil, gagal, atau diproses.
5. Tombol pengulangan transaksi tidak ditampilkan sebelum status transaksi sebelumnya diperiksa.
6. Asumsi proyek akademik (bukan aturan BRI): biaya administrasi Rp 0 ke Bank BRI dan Rp 2.500 ke bank lain; nominal minimum Rp 10.000; saldo contoh Rp 12.450.000.

---

## 8. User Stories

Sumber: Worksheet 8 bagian B.

1. Sebagai pengguna BRImo, saya ingin melihat ringkasan detail transaksi sebelum melakukan konfirmasi, agar saya dapat memastikan nama penerima, nomor rekening, dan nominal transfer sudah benar.
2. Sebagai pengguna BRImo, saya ingin melihat nama penerima secara jelas setelah memasukkan nomor rekening, agar saya dapat memastikan rekening tujuan sesuai dengan orang yang ingin saya kirimi uang.
3. Sebagai pengguna BRImo, saya ingin melihat nominal transfer dengan tampilan yang mudah dibaca pada halaman konfirmasi, agar saya dapat menghindari kesalahan dalam memasukkan jumlah uang.
4. Sebagai pengguna BRImo, saya ingin mendapatkan informasi status transaksi setelah melakukan transfer, agar saya mengetahui apakah transaksi berhasil, gagal, atau masih diproses.
5. Sebagai pengguna BRImo, saya ingin melihat kembali riwayat dan bukti transaksi, agar saya dapat memastikan transaksi yang telah dilakukan tanpa merasa khawatir.

### Pemetaan Insight → Need → Requirement

| Research Insight | User Need | Functional Requirement | UX Requirement |
|---|---|---|---|
| Pengguna khawatir salah transfer sehingga memeriksa ulang nama penerima dan nominal | Detail penerima dan nominal yang jelas sebelum menyelesaikan transaksi | FR-01 | Informasi terstruktur, mudah dibaca, mudah diperiksa |
| Pengguna ragu ketika informasi rekening penerima sulit diperiksa | Kepastian bahwa rekening tujuan sesuai | FR-02 | Nama penerima jelas dan mudah ditemukan di halaman konfirmasi |
| Pengguna membaca ulang detail karena takut salah nominal | Nominal yang mudah dikenali dan diverifikasi | FR-03 | Nominal memiliki penekanan visual |
| Pengguna butuh kepastian transaksi berhasil | Status transaksi yang jelas | FR-05 | Bahasa sederhana dan indikator visual yang jelas |
| Pengguna khawatir ketika status tidak langsung diketahui | Akses mudah ke status dan bukti transaksi | FR-06 | Riwayat mudah ditemukan, status konsisten |

---

## 9. Scope

### In Scope

- Halaman konfirmasi transfer yang dirancang ulang.
- Alur transfer menuju konfirmasi: beranda, pilih tujuan, isi nominal.
- Perbaikan data dari halaman konfirmasi.
- Tahap verifikasi simulasi.
- Status transaksi (berhasil dan belum pasti) serta bukti transaksi.
- Riwayat transaksi (sesuai Worksheet 8).
- Tampilan mobile web.

### Out of Scope

- Koneksi ke layanan atau API bank sungguhan.
- Transaksi uang sungguhan.
- Penggunaan PIN, OTP, password, atau data perbankan asli.
- Menu BRImo lain (pembayaran, QRIS, e-wallet, dan sebagainya) selain placeholder navigasi.
- Fitur baru yang tidak berasal dari Worksheet 1–8.
- Worksheet 9–11 (dilewati sesuai arahan dosen).

---

## 10. Assumptions & Dependencies

### Assumptions

- Pengguna sudah memiliki akun BRImo dan sudah masuk.
- Pengguna memasukkan rekening tujuan dan nominal secara manual.
- Pencarian nama penerima dan verifikasi autentikasi disimulasikan pada prototype.
- Wawancara pengguna nyata belum dilakukan; Worksheet 5 berisi simulasi jawaban pengguna.

### Dependencies

- Data penerima dan nama pemilik rekening (disimulasikan pada prototype).
- Layanan autentikasi dan status transaksi (disimulasikan).
- Platform AI coding agent yang konsisten untuk kedua eksperimen (Claude, Antigravity, atau sejenisnya).
- GitHub untuk kontrol versi dan pencatatan perubahan.

---

## 11. Expected Deliverables

1. Halaman beranda dan menu transfer.
2. Halaman input detail transfer.
3. Halaman konfirmasi detail transfer (halaman utama).
4. Tahap verifikasi simulasi.
5. Halaman status transaksi (berhasil dan belum pasti).
6. Halaman bukti transaksi.
7. Halaman riwayat transaksi.
8. Aplikasi yang dapat dijalankan dan diuji, dengan instruksi menjalankan.

---

## 12. Product Acceptance Criteria

Fitur dinyatakan memenuhi kebutuhan produk apabila:

1. Halaman konfirmasi menampilkan nama penerima, nomor rekening, bank, nominal, biaya, dan total.
2. Nama penerima dan nominal memiliki penekanan visual dibanding informasi lain.
3. Pengguna dapat kembali mengubah rekening atau nominal tanpa kehilangan data.
4. Transaksi tidak diproses sebelum pengguna menekan Konfirmasi dan menyelesaikan verifikasi simulasi.
5. Status transaksi berhasil dan belum pasti ditampilkan dengan bahasa sederhana.
6. Tidak ada tombol pengulangan transaksi pada status belum pasti sebelum status diperiksa.
7. Pengguna dapat melihat bukti transaksi.
8. Pengguna dapat melihat riwayat transaksi.
9. Aplikasi dapat digunakan pada layar smartphone dan tidak meminta data perbankan asli.


**End of PRD v1.0**
