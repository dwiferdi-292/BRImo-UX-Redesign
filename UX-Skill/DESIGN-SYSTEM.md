# DESIGN SYSTEM

## Project: BRImo UX Redesign — Konfirmasi Transfer

**Version:** 1.0
**Referensi:** [PRD_BRImo.md](../PRD/PRD_BRImo.md), [UX-SPEC.md](UX-SPEC.md)
**Status:** Draft

> Nilai di bawah diambil dari prototype Worksheet 12 yang dibuat sebelumnya. Desain ini terinspirasi tampilan aplikasi perbankan seluler dan **bukan desain resmi BRI**. Nilai identitas resmi BRI tidak tersedia **[PERLU DIKONFIRMASI]**.

---

# 1. Design Direction

## 1.1 Design Concept

Tampilan bersih seperti aplikasi mobile banking: kartu putih di atas latar abu muda, satu warna aksi biru, dan hierarki ukuran huruf yang menempatkan nama penerima dan nominal paling menonjol.

## 1.2 Design Principles

1. Informasi penentu kebenaran transaksi paling besar dan paling kontras.
2. Informasi dikelompokkan dalam kartu dengan jarak cukup.
3. Satu aksi utama berwarna solid; aksi perbaikan berwarna garis.
4. Warna semantik dipakai untuk status, tidak untuk dekorasi.

---

# 2. Color System

## 2.1 Primary Colors

| Token | Nilai | Penggunaan |
|---|---|---|
| `--pri` | `#00529C` | Tombol utama, tautan, indikator aktif |
| `--pri-d` | `#003B73` | Nominal besar, teks penekanan |
| `--acc` | `#F58220` | Aksen kecil pada judul beranda |
| `--soft` | `#EAF2FB` | Latar chip, ikon, banner informasi |

## 2.2 Neutral Colors

| Token | Nilai | Penggunaan |
|---|---|---|
| `--bg` | `#F2F5F9` | Latar layar |
| `--card` | `#FFFFFF` | Kartu, bilah atas dan bawah |
| `--tx` | `#1B2430` | Teks utama |
| `--mut` | `#6B7686` | Label dan teks sekunder |
| `--line` | `#E3E8EF` | Garis pemisah |

## 2.3 Semantic Colors

| Token | Nilai | Penggunaan |
|---|---|---|
| `--ok` / `--okbg` | `#12A150` / `#E6F6EC` | Berhasil |
| `--warn` / `--warnbg` | `#B76E00` / `#FFF4E0` | Belum pasti, peringatan |
| `--err` / `--errbg` | `#C62828` / `#FDECEC` | Kesalahan input |

## 2.4 Transaction Status Colors

| Status | Warna | Ikon |
|---|---|---|
| Berhasil | `--ok` | Centang |
| Belum pasti / diproses | `--warn` | Jam |
| Gagal | `--err` | **[PERLU DIKONFIRMASI]** belum ada layar gagal terpisah |

---

# 3. Typography System

## 3.1 Font Family

`Inter`, fallback `Roboto`, `Segoe UI`, `system-ui`, sans-serif.

## 3.2 Typography Scale

| Peran | Ukuran | Bobot |
|---|---|---|
| Nominal konfirmasi | 32 px | 800 |
| Nominal status | 30 px | 800 |
| Nomor rekening (konfirmasi) | 20 px | 800 |
| Nama penerima (konfirmasi) | 19 px | 800 |
| Judul halaman | 17 px | 700 |
| Isi dan baris rincian | 13.5 px | 400 / 700 |
| Label | 12 – 12.5 px | 600 |
| Catatan | 11.5 px | 400 |

Angka memakai `font-variant-numeric: tabular-nums`.

---

# 4. Spacing System

| Token | Nilai |
|---|---|
| Padding halaman | 16 px |
| Padding kartu | 14 px 16 px |
| Jarak antarkartu | 12 px |
| Jarak antarbaris rincian | 9 px (garis tipis pemisah) |

---

# 5. Layout System

## 5.1 Main Layout

Satu kolom. Bilah atas (judul dan tombol kembali), indikator langkah, area gulir, bilah aksi bawah yang tetap sehingga tombol Konfirmasi tidak menutupi isi pemeriksaan.

## 5.2 Responsive Breakpoints

Prototype memakai lebar 390 px × 844 px. Breakpoint lain **[PERLU DIKONFIRMASI]**.

---

# 6. Component Design Specifications

## 6.1 Buttons

| Jenis | Gaya |
|---|---|
| Primary | Latar `--pri`, teks putih, radius 14 px, tinggi sekitar 48 px |
| Secondary | Latar putih, garis 1.5 px `--pri`, teks `--pri` |
| Text | Tanpa latar, teks `--pri` |
| Disabled | Latar abu `#B9C3D0`, tidak dapat ditekan |

Pada layar konfirmasi: Ubah Data (secondary) di kiri, Konfirmasi (primary) di kanan.

## 6.2 Input Fields

Radius 12 px, garis 1.5 px `--line`, fokus `--pri`, kesalahan `--err` dengan pesan di bawah. Nomor rekening dikelompokkan 4 digit; nominal berformat Rp dengan pemisah ribuan.

## 6.3 Cards

Latar putih, radius 16 px, bayangan tipis. Kartu konfirmasi: Penerima, Nominal, Rincian.

## 6.4 Status Badge / Icon

Lingkaran 84 px dengan ikon status berwarna semantik dan latar lembut.

## 6.5 Navigation

Bilah atas dengan tombol kembali bulat; navigasi bawah lima item pada beranda (menu selain Transfer berupa placeholder).

## 6.6 Modal / Bottom Sheet

Lembar bantuan dari bawah dengan sudut atas membulat, berisi penjelasan dan satu tombol.

## 6.7 Toast Notification

Latar gelap, teks putih, tampil sekitar 2 detik, untuk umpan balik ringan.

---

# 7. Komponen Khusus Konfirmasi

| Komponen | Spesifikasi |
|---|---|
| Banner pengingat | Latar `--soft`, ikon info, teks "Transaksi belum diproses sebelum Anda memverifikasi" |
| Blok nama penerima | Avatar inisial + label kecil + nama 19 px tebal |
| Blok rekening | Label kecil + nomor 20 px, spasi huruf lebar |
| Blok nominal | Angka 32 px `--pri-d` + terbilang miring 12 px |
| Baris total | Garis tebal di atas, label dan angka tebal |
| Indikator langkah | Empat segmen; segmen selesai berwarna `--pri` |

---

# 8. Iconography

Ikon garis (stroke 1.8 px, 22 px) bergaya konsisten: transfer, beranda, centang, jam, peringatan, perisai, sidik jari, info.

---

# 9. Design Tokens

Token CSS: `--pri`, `--pri-d`, `--acc`, `--bg`, `--card`, `--tx`, `--mut`, `--line`, `--ok`, `--okbg`, `--warn`, `--warnbg`, `--err`, `--errbg`, `--soft`, `--font`. Nilai pada bagian 2.

---

# 10. Accessibility Guidelines

- Tombol dan area ketuk berukuran nyaman untuk jari.
- Tombol ikon memiliki `aria-label`.
- Pesan kesalahan memakai `role="alert"`.
- Status tidak hanya dibedakan warna, tetapi juga ikon dan teks.
- Kontras warna teks terhadap latar diverifikasi **[PERLU DIKONFIRMASI]**.

---

# 11. Design Consistency Rules

1. Nama penerima dan nominal selalu menjadi elemen paling menonjol pada halaman konfirmasi.
2. Satu tombol primary per layar.
3. Warna semantik hanya untuk status dan kesalahan.
4. Label tombol konsisten: Lanjutkan, Ubah, Konfirmasi, Kembali ke Beranda.
5. Tidak menggunakan logo atau identitas resmi BRI sebagai klaim.
