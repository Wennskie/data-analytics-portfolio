<h1 align="center">Owen Elden | Data Portfolio</h1>

<p align="center"><i>From raw tables to answers people can use.</i></p>

## About

Hi, I'm Owen! I'm a Computer Science student at BINUS University, specializing in Database Technology. My coursework and self-study have given me a solid foundation in working with data, from writing SQL queries to turning raw tables into clear, usable insights.

I'm passionate about data and eager to apply my skills in a real-world setting through an internship. This repository is where I showcase my projects and keep track of my progress in data-related topics.

## Table of Contents

- [About](https://github.com/Wennskie/data-analytics-portfolio/blob/main/README.md#about)
- [Portfolio Projects](https://github.com/Wennskie/data-analytics-portfolio/blob/main/README.md#portfolio-projects)
  - SQL
    - [Hospital Analytics Case Study](https://github.com/Wennskie/data-analytics-portfolio#hospital-analytics-case-study)
- [Next Up](https://github.com/Wennskie/data-analytics-portfolio/blob/main/README.md#next-up)
- [Education](https://github.com/Wennskie/data-analytics-portfolio/blob/main/README.md#education)
- [Certificates](https://github.com/Wennskie/data-analytics-portfolio/blob/main/README.md#certificates)
- [Contact](https://github.com/Wennskie/data-analytics-portfolio/blob/main/README.md#contact)

## Portfolio Projects

Every project here starts with a question and ends with something a decision-maker could actually use.

### Hospital Analytics Case Study

A guided capstone where I played the role of a hospital data analyst. Three teams each sent me a short brief, and I answered them with SQL.

| | |
| --- | --- |
| **Goal** | Answer real business questions from a hospital's data, the way an analyst would for different teams |
| **Data** | A hospital database provided with the case: 30 patients, 12 doctors, 55 visits, and 45 diagnoses |
| **Tools** | SQL (DuckDB) |
| **Skills** | Conditional logic (`CASE WHEN`), inner and left joins, aggregation, `HAVING`, NULL handling (`COALESCE`, `NULLIF`), scoring and segmentation |
| **Code** | [`hospital-case-study.sql`](https://github.com/Wennskie/Portfolio-Projects/blob/main/hospital-case-study.sql) |

<details>
<summary><b>Dataset schema (click to expand)</b></summary>

| Table | Rows | Columns |
| --- | --- | --- |
| `pasien` (patients) | 30 | `id`, `nama`, `umur`, `jenis_kelamin`, `kota`, `no_asuransi` (NULL means self-paying) |
| `dokter` (doctors) | 12 | `id`, `nama`, `spesialisasi`, `tahun_pengalaman` |
| `kunjungan` (visits) | 55 | `id`, `pasien_id`, `dokter_id`, `tanggal_kunjungan` (TEXT, YYYY-MM-DD), `tipe_kunjungan` (Rawat Jalan, Rawat Inap, or IGD), `biaya` (0 means subsidized), `lama_inap_hari`, `triase_level` (1 to 5, ER visits only) |
| `diagnosa` (diagnoses) | 45 | `id`, `kunjungan_id`, `kode_icd`, `nama_diagnosa`, `tingkat_keparahan` (Ringan, Sedang, or Berat) |

The dataset itself is not included in this repository. The schema above shows the structure the queries are written for.

</details>

<details>
<summary><b>The three scenarios (click to expand)</b></summary>

**1. ER Operations Dashboard** (brief from the Operations Manager)
- Doctor workload
- ER triage distribution per doctor
- Follow-up priority list for ER patients

**2. Monthly Financial Report** (brief from the Finance Director)
- Revenue and inpatient share per doctor
- Monthly revenue trend by visit type
- Cost levels and billing for self-paying patients

**3. Patient Scoring and Segmentation** (brief from the Patient Services Team)
- Patient profiles and matching programs
- Severity score and follow-up list
- Executive summary per age group

</details>

## Next Up

This portfolio is a work in progress. New projects, along with their code, will be added here as I complete them.

## Education

**BINUS University**, Jakarta
Bachelor of Computer Science, Database Technology
*2024 - Present*

## Certificates

- [Relational Database V8](https://www.freecodecamp.org/certification/owen602/relational-database-v8) - freeCodeCamp *(Sep 2026)*

## Contact

- GitHub: [@Wennskie](https://github.com/Wennskie)
- LinkedIn: [@owenelden](https://www.linkedin.com/in/owen-elden-662a012b1/)
- Email: owenelden06@gmail.com
