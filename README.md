# 👩‍💼 HR Attrition Analysis Dashboard

## 📋 Deskripsi Proyek
Proyek ini bertujuan untuk menganalisis **tingkat attrition (karyawan yang keluar)** dalam perusahaan dan mengidentifikasi faktor-faktor yang mempengaruhinya.  
Analisis dilakukan menggunakan **Excel / Power BI** dengan dataset karyawan yang mencakup informasi tentang usia, departemen, tingkat pendidikan, pekerjaan, dan tingkat kepuasan kerja.

Dashboard interaktif ini membantu HR dalam:
- Menilai tingkat retensi karyawan.
- Mengidentifikasi pola attrition berdasarkan demografi dan jabatan.
- Memberikan insight untuk strategi HR yang lebih efektif dalam retensi karyawan.

---

## 🗂️ Dataset
**Nama file:** `HR Data.xlsx`

**Jumlah Data:** ±1.470 baris (karyawan aktif & keluar)  
**Jumlah Kolom:** 35 kolom

**Kolom penting:**
| Kolom | Deskripsi |
|--------|------------|
| `EmployeeNumber` | ID unik setiap karyawan |
| `Age` | Umur karyawan |
| `Gender` | Jenis kelamin |
| `Department` | Departemen tempat bekerja |
| `Education` | Tingkat pendidikan |
| `JobRole` | Jabatan karyawan |
| `JobSatisfaction` | Tingkat kepuasan kerja (1–4) |
| `Attrition` | Status karyawan (Yes = keluar, No = masih aktif) |
| `MonthlyIncome` | Gaji per bulan |
| `TotalWorkingYears` | Total pengalaman kerja |
| `YearsAtCompany` | Lama bekerja di perusahaan |
| `BusinessTravel` | Frekuensi perjalanan dinas |
| `MaritalStatus` | Status pernikahan |

---

## ⚙️ Tools & Teknologi
- **Microsoft Excel / Tableu** untuk analisis dan visualisasi dashboard.
- **DAX (Data Analysis Expressions)** untuk perhitungan KPI seperti Attrition Rate.
- **Data Cleaning & Transformation** dilakukan di Power Query.
- **Visualization Design** dengan warna netral (brown-orange theme) agar mudah dibaca.

---

## 🧼 Data Preparation
Langkah-langkah utama dalam proses pembersihan dan transformasi data:
1. Menghapus duplikasi dan entri kosong.
2. Menstandarkan format kategori (contoh: *Male/Female*, *Department names*).
3. Membuat kolom tambahan:
   - `AttritionRate` = (Attrition Count / Employee Count) * 100
   - `AgeGroup` = pengelompokan umur (20–24, 25–34, 35–44, 45–54, >55)
4. Menghitung KPI utama menggunakan **DAX**:
   ```DAX
   Attrition Rate = DIVIDE(CALCULATE(COUNT(Employee[Attrition]), Employee[Attrition] = "Yes"), COUNT(Employee[EmployeeNumber]), 0)
