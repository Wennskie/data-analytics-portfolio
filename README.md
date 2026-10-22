<h1 align="center">Owen Elden | Data Portofolio</h1>

<p align="center"><i>Dari tabel mentah menjadi jawaban yang berguna.</i></p>

## Tentang Saya

Halo, saya Owen! Saya mahasiswa Ilmu Komputer di BINUS University dengan jalur Database Technology. Lewat perkuliahan dan belajar mandiri, saya membangun fondasi yang kuat dalam mengolah data, mulai dari menulis query SQL hingga mengubah tabel mentah menjadi insight yang jelas dan bermanfaat.

Saya antusias di bidang data dan ingin menerapkan kemampuan saya di dunia kerja nyata melalui program magang. Repositori ini adalah tempat saya menampilkan proyek sekaligus mencatat perkembangan saya di topik-topik terkait data.

## Daftar Isi

- [Tentang Saya](https://github.com/Wennskie/data-analytics-portfolio/blob/main/README.md#tentang-saya)
- [Proyek Portofolio](https://github.com/Wennskie/data-analytics-portfolio/blob/main/README.md#proyek-portofolio)
  - SQL
    - [Studi Kasus Analitik Rumah Sakit](https://github.com/Wennskie/data-analytics-portfolio#studi-kasus-analitik-rumah-sakit)
    - [Studi Kasus Analitik Platform E-Learning](https://github.com/Wennskie/data-analytics-portfolio#studi-kasus-analitik-platform-e-learning)
    - [Studi Kasus Analitik Marketplace E-Commerce](https://github.com/Wennskie/data-analytics-portfolio#studi-kasus-analitik-marketplace-e-commerce)
    - [Studi Kasus Analitik Bisnis SaaS](https://github.com/Wennskie/data-analytics-portfolio#studi-kasus-analitik-bisnis-saas)
- [Selanjutnya](https://github.com/Wennskie/data-analytics-portfolio/blob/main/README.md#selanjutnya)
- [Pendidikan](https://github.com/Wennskie/data-analytics-portfolio/blob/main/README.md#pendidikan)
- [Sertifikat](https://github.com/Wennskie/data-analytics-portfolio/blob/main/README.md#sertifikat)
- [Kontak](https://github.com/Wennskie/data-analytics-portfolio/blob/main/README.md#kontak)

## Proyek Portofolio

Setiap proyek di sini berawal dari sebuah pertanyaan dan berakhir dengan sesuatu yang benar-benar bisa dipakai untuk mengambil keputusan.

### Studi Kasus Analitik Rumah Sakit

Studi kasus terpandu di mana saya berperan sebagai analis data rumah sakit. Tiga tim mengirimkan brief singkat, lalu saya menjawabnya dengan SQL.

| | |
| --- | --- |
| **Tujuan** | Menjawab pertanyaan bisnis nyata dari data rumah sakit, seperti yang dilakukan seorang analis untuk tim yang berbeda |
| **Data** | Database rumah sakit yang disediakan bersama kasusnya: 30 pasien, 12 dokter, 55 kunjungan, dan 45 diagnosa |
| **Tools** | SQL |
| **Skill** | Logika kondisional (`CASE WHEN`), inner dan left join, agregasi, `HAVING`, penanganan NULL (`COALESCE`, `NULLIF`), scoring dan segmentasi |
| **Kode** | [`hospital-case-study.sql`](https://github.com/Wennskie/Portfolio-Projects/blob/main/hospital-case-study.sql) |

<details>
<summary><b>Skema dataset (klik untuk membuka)</b></summary>

| Tabel | Baris | Kolom |
| --- | --- | --- |
| `pasien` | 30 | `id`, `nama`, `umur`, `jenis_kelamin`, `kota`, `no_asuransi` (NULL berarti bayar mandiri) |
| `dokter` | 12 | `id`, `nama`, `spesialisasi`, `tahun_pengalaman` |
| `kunjungan` | 55 | `id`, `pasien_id`, `dokter_id`, `tanggal_kunjungan` (TEXT, YYYY-MM-DD), `tipe_kunjungan` (Rawat Jalan, Rawat Inap, atau IGD), `biaya` (0 berarti subsidi), `lama_inap_hari`, `triase_level` (1 sampai 5, hanya untuk IGD) |
| `diagnosa` | 45 | `id`, `kunjungan_id`, `kode_icd`, `nama_diagnosa`, `tingkat_keparahan` (Ringan, Sedang, atau Berat) |

Dataset-nya tidak disertakan di repositori ini. Skema di atas menunjukkan struktur tabel yang dipakai oleh query.

</details>

<details>
<summary><b>Tiga skenario (klik untuk membuka)</b></summary>

**1. Dashboard Operasional IGD** (brief dari Manajer Operasional)
- Beban kerja dokter
- Sebaran triase IGD per dokter
- Daftar prioritas follow-up pasien IGD

**2. Laporan Keuangan Bulanan** (brief dari Direktur Keuangan)
- Revenue dan porsi Rawat Inap per dokter
- Tren revenue bulanan per tipe kunjungan
- Tingkat biaya dan tagihan pasien mandiri

**3. Scoring dan Segmentasi Pasien** (brief dari Tim Layanan Pasien)
- Profil pasien dan program yang cocok
- Skor keparahan dan daftar tindak lanjut
- Ringkasan eksekutif per kelompok umur

</details>

### Studi Kasus Analitik Platform E-Learning

Studi kasus terpandu di mana saya berperan sebagai analis baru di sebuah platform e-learning. Tiga pimpinan mengirimkan brief, lalu saya menjawabnya dengan query SQL yang menggabungkan banyak tabel.

| | |
| --- | --- |
| **Tujuan** | Menjawab pertanyaan manajemen platform e-learning, mulai dari laporan pendaftaran, evaluasi instruktur, sampai ringkasan eksekutif |
| **Data** | Database platform e-learning yang disediakan bersama kasusnya: 10 mahasiswa, 5 instruktur, 4 kategori, 8 kursus, 17 pendaftaran, dan 13 review |
| **Tools** | SQL |
| **Skill** | Multi-table JOIN (inner dan left), anti-join, agregasi kondisional, `HAVING`, derived table dan `CROSS JOIN`, CTE, fungsi tanggal (`CAST`, `DATEDIFF`) |
| **Kode** | [`elearning-case-study.sql`](https://github.com/Wennskie/Portfolio-Projects/blob/main/elearning-case-study.sql) |

<details>
<summary><b>Skema dataset (klik untuk membuka)</b></summary>

| Tabel | Baris | Kolom |
| --- | --- | --- |
| `mahasiswa` | 10 | `id`, `nama`, `kota`, `email`, `tanggal_daftar` (TEXT) |
| `instruktur` | 5 | `id`, `nama`, `spesialisasi`, `tahun_bergabung` |
| `kategori_kursus` | 4 | `id`, `nama_kategori` (Data, Programming, Bisnis, Desain), `deskripsi` |
| `kursus` | 8 | `id`, `judul`, `instruktur_id`, `kategori_id`, `harga`, `level` (pemula, menengah, lanjutan), `is_aktif` |
| `pendaftaran` | 17 | `id`, `mahasiswa_id`, `kursus_id`, `tanggal_daftar`, `status` (aktif, selesai, atau batal), `nilai` (NULL jika belum selesai atau batal) |
| `review` | 13 | `id`, `mahasiswa_id`, `kursus_id`, `rating` (1 sampai 5), `komentar`, `tanggal` |

Dataset-nya tidak disertakan di repositori ini. Skema di atas menunjukkan struktur tabel yang dipakai oleh query.

</details>

<details>
<summary><b>Tiga skenario (klik untuk membuka)</b></summary>

**1. Laporan Semester** (brief dari Kepala Akademik)
- Ringkasan pendaftaran per kursus
- Pendaftaran per kategori
- Kursus sepi pendaftaran
- Mahasiswa tanpa aktivitas

**2. Evaluasi Instruktur** (brief dari Head of People)
- Scorecard instruktur
- Completion rate per instruktur
- Perbandingan jumlah mahasiswa per kursus
- Instruktur dengan rating di atas rata-rata

**3. Laporan Eksekutif** (brief dari CEO)
- Revenue per kategori dan level
- Top 3 mahasiswa paling aktif
- Kursus yang perlu perhatian
- Executive summary per kategori

</details>

### Studi Kasus Analitik Marketplace E-Commerce

Studi kasus terpandu di mana saya berperan sebagai data analyst di sebuah marketplace e-commerce. Berbagai tim (CRM, Retention, Finance, Inventory, sampai CEO) mengirimkan permintaan, lalu saya menjawabnya dengan subquery dan CTE.

| | |
| --- | --- |
| **Tujuan** | Menjawab pertanyaan dari berbagai tim di marketplace e-commerce, mulai dari analisis pelanggan dan penjual, produk dan kategori, sampai laporan manajemen |
| **Data** | Database marketplace e-commerce yang disediakan bersama kasusnya, berisi data pelanggan, penjual, produk, kategori, pesanan, detail pesanan, dan review |
| **Tools** | SQL |
| **Skill** | Subquery (di `WHERE`, `SELECT`, dan `FROM`), correlated subquery, CTE, recursive CTE, `EXISTS` dan `NOT EXISTS`, `CROSS JOIN`, running total, fungsi tanggal (`CAST`, `INTERVAL`, `strftime`) |
| **Kode** | [`marketplace-case-study.sql`](https://github.com/Wennskie/Portfolio-Projects/blob/main/marketplace-case-study.sql) |

<details>
<summary><b>Kolom yang dipakai (klik untuk membuka)</b></summary>

| Tabel | Kolom yang dipakai |
| --- | --- |
| `pelanggan` | `id`, `nama`, `kota`, `tanggal_daftar` (TEXT) |
| `penjual` | `id`, `nama`, `kota`, `referrer_id` (NULL berarti penjual root) |
| `produk` | `id`, `nama_produk`, `penjual_id`, `kategori_id`, `harga`, `stok`, `is_aktif` |
| `kategori` | `id`, `nama_kategori`, `parent_id` (NULL berarti kategori root) |
| `pesanan` | `id`, `pelanggan_id`, `tanggal_pesanan` (TEXT), `status`, `total` |
| `detail_pesanan` | `pesanan_id`, `produk_id`, `jumlah`, `harga_satuan` |
| `review` | `id`, `produk_id`, `rating` |

Dataset-nya tidak disertakan di repositori ini. Tabel di atas menunjukkan struktur yang dipakai oleh query.

</details>

<details>
<summary><b>Tiga skenario (klik untuk membuka)</b></summary>

**1. Analisis Pelanggan dan Penjual**
- Segmentasi pelanggan berdasarkan spending
- Ranking penjual berdasarkan revenue
- Pelanggan tidak aktif
- Referral chain penjual

**2. Analisis Produk dan Kategori**
- Produk terlaris per kategori
- Revenue per kategori root
- Produk stok tinggi tapi penjualan rendah
- Rating review dan penjualan

**3. Laporan Manajemen**
- Trend bulanan dengan running total
- Scorecard penjual
- Cohort pelanggan berdasarkan bulan registrasi
- Ringkasan eksekutif marketplace

</details>

### Studi Kasus Analitik Bisnis SaaS

Studi kasus terpandu di mana saya berperan sebagai data analyst di sebuah perusahaan SaaS. Berbagai pimpinan (CEO, CFO, VP Product, dan lainnya) meminta laporan revenue, churn, dan aktivitas pengguna, lalu saya menjawabnya dengan window function.

| | |
| --- | --- |
| **Tujuan** | Menjawab kebutuhan laporan sebuah bisnis SaaS: analisis revenue, deteksi churn, aktivitas dan retensi pengguna, serta laporan manajemen |
| **Data** | Database SaaSKu (platform manajemen proyek fiktif) yang disediakan bersama kasusnya: 15 pengguna, 21 langganan, 35 pembayaran, 60 aktivitas, dan 20 tiket support |
| **Tools** | SQL |
| **Skill** | Window function (`LAG`, `RANK`, `DENSE_RANK`, `ROW_NUMBER`, `FIRST_VALUE`, `LAST_VALUE`), running total, moving average dengan frame clause, `PARTITION BY`, CTE, fungsi tanggal (`SUBSTR`, `DATEDIFF`) |
| **Kode** | [`saas-case-study.sql`](https://github.com/Wennskie/Portfolio-Projects/blob/main/saas-case-study.sql) |

<details>
<summary><b>Skema dataset (klik untuk membuka)</b></summary>

| Tabel | Baris | Kolom |
| --- | --- | --- |
| `pengguna` | 15 | `id`, `nama`, `kota`, `email`, `tanggal_daftar` (TEXT) |
| `langganan` | 21 | `id`, `pengguna_id`, `plan` (free, starter, pro, enterprise), `harga_bulanan`, `tanggal_mulai`, `tanggal_selesai` (NULL jika masih aktif), `status` (aktif, expired, cancelled) |
| `pembayaran` | 35 | `id`, `pengguna_id`, `langganan_id`, `jumlah`, `metode` (transfer, kartu_kredit, ewallet), `tanggal_bayar` (TEXT) |
| `aktivitas` | 60 | `id`, `pengguna_id`, `tipe_aktivitas` (login, buat_proyek, undang_anggota, selesai_tugas, export_laporan), `tanggal_aktivitas` (TEXT) |
| `tiket_support` | 20 | `id`, `pengguna_id`, `kategori` (bug, fitur, billing, umum), `prioritas` (rendah, sedang, tinggi), `status` (baru, diproses, selesai), `tanggal_dibuat` (TEXT), `tanggal_selesai` (NULL jika belum selesai) |

Dataset-nya tidak disertakan di repositori ini. Skema di atas menunjukkan struktur tabel yang dipakai oleh query.

</details>

<details>
<summary><b>Tiga skenario (klik untuk membuka)</b></summary>

**1. Analisis Revenue dan Churn**
- MoM growth dengan trend
- Ranking kontribusi revenue per pengguna
- Gap antar pembayaran sebagai indikator churn risk
- Revenue kumulatif dan target

**2. Analisis Aktivitas dan Retensi**
- Aktivitas bulanan per pengguna dengan ranking
- Trend aktivitas bulanan
- Lifecycle span pengguna
- Top 3 pengguna paling aktif per bulan

**3. Laporan Manajemen**
- Dashboard revenue executive
- Segmentasi plan dengan revenue share
- Tiket support: trend dan moving average
- Pengguna teratas per kota

</details>

## Selanjutnya

Portofolio ini masih terus berkembang. Proyek baru beserta kodenya akan saya tambahkan di sini setelah selesai.

## Pendidikan

**BINUS University**, Jakarta
S1 Ilmu Komputer, Database Technology
*2024 - Sekarang*

## Sertifikat

- [Relational Database V8](https://www.freecodecamp.org/certification/owen602/relational-database-v8) - freeCodeCamp *(Sep 2026)*

## Kontak

- GitHub: [@Wennskie](https://github.com/Wennskie)
- LinkedIn: [@owenelden](https://www.linkedin.com/in/owen-elden)
- Email: owenelden06@gmail.com
