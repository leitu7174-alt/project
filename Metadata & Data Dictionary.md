# 📘 Metadata & Data Dictionary  
**Proyek:** Analisis Akreditasi Pendidikan dan Garis Kemiskinan Kabupaten/Kota di Indonesia  
**Tahun:** 2024  
**File:** `Data Akreditasi.csv` & `Garis Kemiskinan Menurut Kabupaten_Kota, 2024.csv`

---

## 🧭 Metadata Umum

| Atribut | Deskripsi |
|----------|------------|
| **Judul Dataset Gabungan** | Analisis Hubungan Akreditasi Pendidikan dan Garis Kemiskinan per Kabupaten/Kota di Indonesia |
| **Sumber Data Utama** | 1️⃣ Kemdikbud — Data Akreditasi Sekolah per Kabupaten/Kota<br>2️⃣ BPS — Garis Kemiskinan per Kabupaten/Kota Tahun 2024 |
| **Cakupan Wilayah** | Kabupaten/Kota di 38 Provinsi di Indonesia |
| **Cakupan Waktu** | Tahun 2024 |
| **Unit Analisis** | Kabupaten/Kota |
| **Format File** | `.csv` |
| **Tujuan Dataset** | Mengukur hubungan antara kinerja pendidikan (akreditasi sekolah) dan kesejahteraan ekonomi (garis kemiskinan) |
| **Frekuensi Pengumpulan Data** | Tahunan |
| **Sumber Resmi** | [https://www.bps.go.id](https://www.bps.go.id) • [https://sekolah.data.kemdikbud.go.id](https://sekolah.data.kemdikbud.go.id) |
| **Lisensi** | Data Publik Pemerintah Indonesia |
| **Tanggal Dibuat** | 15 Oktober 2025 |
| **Versi Dataset** | v1.0 |
| **Penanggung Jawab Dokumentasi** | Sole (Data Lead) |

---

## 📊 Data Dictionary

### 1️⃣ Data: `Garis Kemiskinan Menurut Kabupaten_Kota, 2024.csv`

| No | Nama Kolom | Tipe Data | Skala Pengukuran | Deskripsi | Satuan | Contoh Nilai | Sumber |
|----|-------------|------------|------------------|------------|---------|---------------|--------|
| 1 | `Nama Wilayah` | string | Nominal | Nama provinsi atau kabupaten/kota di Indonesia | - | Aceh Barat Daya | BPS |
| 2 | `Garis Kemiskinan Menurut Kabupaten/Kota (Rupiah/kapita/bulan)` | float | Rasio | Garis kemiskinan rata-rata per kapita per bulan | Rupiah | 583294 | BPS |
| 3 | `Tahun` | integer | Nominal | Tahun pengumpulan data | Tahun | 2024 | BPS |

> **Catatan:** File ini berisi nilai garis kemiskinan (dalam rupiah per kapita per bulan) untuk setiap kabupaten/kota di Indonesia tahun 2024. Beberapa baris berisi nama provinsi sebagai pembatas wilayah administratif.

---

### 2️⃣ Data: `Data Akreditasi.csv`

| No | Nama Kolom | Tipe Data | Skala Pengukuran | Deskripsi | Satuan | Contoh Nilai | Sumber |
|----|-------------|------------|------------------|------------|---------|---------------|--------|
| 1 | `No.` | integer | Nominal | Nomor urut data | - | 1 | Kemdikbud |
| 2 | `Kabupaten` | string | Nominal | Nama kabupaten atau kota | - | Kota Banda Aceh | Kemdikbud |
| 3 | `Rata rata akreditasi` | string | Ordinal | Nilai rata-rata akreditasi dalam huruf (A, B, C) | Kategori | B | BAN-S/M |
| 4 | `Skor` | float | Interval | Skor numerik hasil penilaian akreditasi | Skor | 3.40 | BAN-S/M |
| 5 | `Provinsi` | string | Nominal | Nama provinsi tempat kabupaten/kota berada | - | Aceh | Kemdikbud |

> **Catatan:** Dataset ini memuat nilai rata-rata akreditasi dan skor akreditasi pendidikan per kabupaten/kota di Indonesia.  
> Tipe “Rata rata akreditasi” bersifat **ordinal** karena mewakili urutan kualitas (A > B > C).

---

## 🔗 Rencana Penggabungan (Join/Merge)

| Atribut | Deskripsi |
|----------|------------|
| **Kunci Penggabungan (Join Key)** | `Kabupaten` (dari `Data Akreditasi.csv`) dengan `Nama Wilayah` (dari `Garis Kemiskinan.csv`) |
| **Jenis Merge** | `inner` atau `left` (tergantung fokus analisis — misalnya seluruh kabupaten yang punya data akreditasi) |
| **Tujuan** | Menghasilkan dataset terintegrasi berisi skor akreditasi dan garis kemiskinan per kabupaten/kota |

---
