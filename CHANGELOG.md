# CHANGELOG — BRImo-UX-Redesign

Format mengikuti Keep a Changelog. Hanya mencatat perubahan yang benar-benar terjadi.

## [Belum dirilis]

### Ditambahkan
- 2026-11-26: PRD BRImo UX Redesign v1.0 (draft) pada PRD/PRD_BRImo.md dan README.md, isi sama dengan Eksperimen A.
- 2026-11-26: UX-SPEC.md, DESIGN-SYSTEM.md, INTERACTION-SPEC.md, ACCEPTANCE-CRITERIA.md v1.0 (draft) pada UX-Skill/.
- 2026-11-26: AGENTS.md v1.0 (instruksi AI coding agent).
- 2026-11-26: Struktur repository awal (folder src/).

### Catatan sumber
- Nilai desain, alur, dan perilaku interaksi diturunkan dari prototype Worksheet 12 yang dibuat sebelumnya.

### Ditambahkan (implementasi, 2026-11-26)
- Aplikasi statis `src/index.html` (HTML/CSS/JS satu berkas) mengikuti AGENTS.md, UX-SPEC, DESIGN-SYSTEM, INTERACTION-SPEC: 8 layar sesuai spesifikasi ditambah Riwayat Transaksi, mode Wireframe/Visual dan panel simulasi untuk demo.
- Halaman Riwayat Transaksi (PAGE-08) ditambahkan; perilakunya belum didefinisikan di INTERACTION-SPEC (baris 158), jadi memakai asumsi sederhana di bawah.
- `index.html` di root dan `.nojekyll` untuk GitHub Pages; `docs/screenshots/` (visual) dan `docs/wireframe/` (mode wireframe).
- Perbaikan teks: nama persona pada beranda diselaraskan menjadi "Dimas Pratama" sesuai PRD.
- Prompt iterasi ke agent: 1 (pembuatan awal, dari prototype Worksheet 12) + 1 (penambahan Riwayat). Perbaikan setelah hasil pertama: 0.

### Asumsi yang diambil pada bagian yang belum pasti
- Biaya admin Rp 0 ke Bank BRI, Rp 2.500 ke bank lain; minimum Rp 10.000 (sesuai UX-SPEC/prototype).
- Riwayat: 3 transaksi contoh + transaksi baru; ketuk transaksi berhasil membuka Bukti, transaksi diproses membuka Status Belum Pasti.

### Temuan inkonsistensi dokumen (tidak diubah, perlu keputusan penulis)
- DESIGN-SYSTEM menetapkan nomor rekening 20 px dan nama penerima 19 px, sedangkan AC-006 menyatakan nama dan nominal berukuran paling besar. Aplikasi mengikuti DESIGN-SYSTEM; AC-006 terpenuhi untuk nominal (32 px) tetapi nama (19 px) lebih kecil dari nomor rekening (20 px).
- AC-005 mensyaratkan "sumber dana"; PRD FR-01 tidak mencantumkannya.

### Pengujian (Playwright + Chrome, lokal)
- Lulus otomatis: AC-001, 002, 003, 004, 005, 007, 008, 009, 010, 011, 012, 013, 014, 015, 022 (lebar 390 px tanpa scroll horizontal), dan tidak ada input password pada kode (AC-030). Tanpa error JavaScript.
- AC-006: lulus untuk nominal, tidak sepenuhnya untuk nama (lihat temuan).
- AC-020, AC-021 (konsistensi desain, bahasa sederhana): hanya ditinjau visual manual, belum diukur.
- Belum diuji: perangkat nyata, browser selain Chrome, deployment.

### Keterbatasan eksperimen
- Aplikasi B berasal dari prototype Worksheet 12 yang sama dengan sumber UX Skill, sehingga kesesuaiannya dengan dokumen tinggi secara alami. Waktu pengembangan: sesi 2026-11-26 hingga 2026-11-27 (jam mulai/selesai tidak dicatat).

### Diperbarui (dokumen v1.1, 2026-11-27)
- Seluruh tanda yang sebelumnya menandai informasi belum pasti telah diputuskan penulis dan diisi di PRD, README, dan (pada repo B) AGENTS.md serta UX-Skill. Keputusan mengikuti Worksheet 1–8: wawancara tetap berstatus simulasi, riwayat masuk scope (User Story 5), biaya dan batas nominal ditulis sebagai asumsi proyek akademik.
- Catatan: aplikasi pada src/ dibangun dari dokumen v1.0. Perubahan v1.1 menyelaraskan teks dengan keputusan yang sudah dipakai aplikasi dan tidak mengubah kodenya.
- Tanggal unggah ke GitHub: 2026-11-27. Demo GitHub Pages aktif pada hari yang sama.

### Belum dikerjakan
- Deployment.
- Pengujian pada pengguna nyata dan usability test.
