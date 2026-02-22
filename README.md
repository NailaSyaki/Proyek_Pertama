# Proyek_Pertama

# Business Understanding

## Latar Belakang Bisnis

Perusahaan Edutech merupakan perusahaan yang bergerak di bidang teknologi pendidikan dengan jumlah karyawan yang terus bertambah seiring dengan pertumbuhan bisnis. Namun, dalam beberapa tahun terakhir, perusahaan menghadapi permasalahan tingginya **attrition rate (tingkat resign karyawan)**.

Tingginya attrition rate dapat menyebabkan:

* Biaya rekrutmen meningkat
* Produktivitas menurun
* Beban kerja karyawan lain bertambah
* Gangguan terhadap stabilitas tim dan proyek

Oleh karena itu, departemen HR membutuhkan analisis berbasis data untuk memahami faktor-faktor yang memengaruhi attrition dan memonitor kondisi karyawan secara berkala melalui business dashboard.

---

# Permasalahan Bisnis

Beberapa permasalahan bisnis yang ingin diselesaikan:

1. Berapa tingkat attrition rate perusahaan saat ini?
2. Faktor apa saja yang memengaruhi tingginya attrition?
3. Apakah overtime berpengaruh terhadap keputusan resign?
4. Apakah level jabatan dan gaji memengaruhi attrition?
5. Departemen atau job role mana yang memiliki tingkat attrition tertinggi?
6. Bagaimana profil karyawan yang cenderung resign?

---

# Cakupan Proyek

Cakupan proyek ini meliputi:

1. Data understanding dan eksplorasi data karyawan
2. Data cleaning dan preprocessing
3. Analisis faktor-faktor yang memengaruhi attrition
4. Pembuatan model machine learning untuk prediksi attrition
5. Evaluasi model
6. Pembuatan business dashboard menggunakan Metabase
7. Penyusunan insight dan rekomendasi untuk HR

---

# Persiapan

## Sumber Data

Dataset yang digunakan merupakan dataset karyawan perusahaan Edutech yang berisi informasi seperti:

* Age
* Department
* JobRole
* JobLevel
* MonthlyIncome
* OverTime
* YearsAtCompany
* Attrition (Target)

Dataset yang digunakan:

```
data_karyawan_bersih.csv
```

---

## Setup Environment

### Install Dependencies

```bash
pip install -r requirements.txt
```

Library utama yang digunakan:

```
pandas
numpy
matplotlib
seaborn
scikit-learn
sqlalchemy
psycopg2-binary
```

---

### Menjalankan Metabase dengan Docker

```bash
docker run -d -p 3001:3000 --name metabase metabase/metabase
```

Akses Metabase melalui:

```
http://localhost:3001
```

Login:

```
Email: root@mail.com
Password: root123
```

---

### Export Dashboard

Setelah dashboard selesai dibuat, jalankan:

```bash
docker cp metabase:/metabase.db/metabase.db.mv.db ./
```

File `metabase.db.mv.db` disertakan dalam submission.

---

# Business Dashboard

Dashboard yang dibuat bernama:

> **HR Attrition Monitoring Dashboard**

Dashboard ini dirancang untuk membantu HR dalam:

* Memantau attrition rate secara real-time
* Mengidentifikasi faktor utama penyebab resign
* Mengambil keputusan berbasis data

---

## Komponen Dashboard

Dashboard terdiri dari:

### KPI

* Total Employee
* Attrition Rate (%)

### Analisis Faktor

* Attrition Rate by Department
* Attrition Rate by Job Role
* Attrition Rate by Job Level
* Attrition Rate by OverTime
* Attrition Rate by Monthly Income
* Attrition Rate by Age

Visualisasi menggunakan:

* Bar Chart
* Line Chart
* KPI Number Card

Dashboard tidak hanya menampilkan tabel, tetapi menyajikan visualisasi yang mudah dipahami untuk mendukung pengambilan keputusan.

---

# Insight Utama

Berdasarkan hasil analisis:

1. Karyawan dengan **OverTime = Yes** memiliki tingkat attrition lebih tinggi.
2. Department tertentu memiliki attrition rate lebih besar dibanding lainnya.
3. JobLevel rendah cenderung memiliki tingkat resign lebih tinggi.
4. Karyawan dengan gaji lebih rendah memiliki kecenderungan attrition lebih tinggi.
5. Kelompok usia muda lebih rentan resign dibanding usia senior.

---

# Modeling & Evaluation

Model machine learning digunakan untuk memprediksi kemungkinan karyawan resign.

Model yang digunakan:

* Logistic Regression

Hasil evaluasi model menunjukkan:

* Accuracy cukup baik
* Recall kelas Attrition (1) menunjukkan model mampu mengidentifikasi karyawan berisiko resign
* Confusion matrix digunakan untuk melihat performa klasifikasi

Model ini dapat membantu HR melakukan tindakan preventif terhadap karyawan yang berpotensi resign.

---

# Conclusion

Berdasarkan analisis data dan dashboard yang dibuat, dapat disimpulkan bahwa:

* Attrition dipengaruhi oleh faktor pekerjaan dan beban kerja.
* Overtime dan level jabatan memiliki pengaruh signifikan.
* Faktor kompensasi juga berkontribusi terhadap keputusan resign.

Business dashboard yang dibuat memungkinkan HR untuk:

* Memantau attrition secara berkala
* Mengidentifikasi faktor risiko
* Mengambil keputusan strategis berbasis data

---

# Rekomendasi Action Items

### Action Item 1
Melakukan evaluasi kebijakan overtime dan workload untuk mengurangi tekanan kerja berlebih.

### Action Item 2
Meningkatkan program retention untuk karyawan dengan JobLevel rendah.

### Action Item 3
Melakukan penyesuaian kompensasi pada kelompok dengan income rendah yang memiliki attrition tinggi.

### Action Item 4
Menyediakan program pengembangan karir dan mentoring bagi karyawan usia muda.
