# Executive Dashboard: AI Usage & Impact

## Overview

Sebuah *dashboard* analitik interaktif yang dirancang untuk menganalisis pola penggunaan kecerdasan buatan (*AI Tools*) berdasarkan karakteristik demografi pengguna, durasi penggunaan harian, estimasi penghematan waktu, serta tingkat kepuasan (*Satisfaction Score*). Proyek ini memetakan variabel perilaku adopsi AI menjadi wawasan visual strategis untuk memahami pangsa pasar alat AI, tren penggunaan bulanan, efektivitas produktivitas, serta deviasi tingkat kepuasan pengguna. Dashboard ini dikembangkan menggunakan **Power BI Desktop** dan **Google Colab (Python)**.
<img width="1382" height="768" alt="AI Usage" src="https://github.com/user-attachments/assets/4c1d39d1-086f-4c20-93aa-6af0ef4ac4d3" />


## Business Questions Framework

Tabel berikut menguraikan pertanyaan bisnis dan analitik utama yang dijawab melalui visualisasi pada *dashboard*:

| Dimensi Analisis | Pertanyaan Bisnis Utama |
| :--- | :--- |
| **Pangsa Pasar AI Tools** | Bagaimana distribusi pangsa pasar (*market share*) dari berbagai alat AI yang digunakan oleh responden dalam sampel? |
| **Dampak Produktivitas & Waktu** | Bagaimana korelasi antara skor produktivitas (*Productivity Score*) dan estimasi waktu yang dihemat (*Time Saved*) berdasarkan tipe pengguna (*Student* vs. *Professional*)? |
| **Skor Kepuasan Top 5 AI Tools** | Berapa rata-rata skor kepuasan (*Satisfaction Score*) dari lima alat AI teratas yang dievaluasi oleh pengguna? |
| **Tren Penggunaan Bulanan** | Bagaimana tren total jam penggunaan AI (*Total Usage Hours*) sepanjang tahun berdasarkan tipe pengguna? |
| **Tujuan Penggunaan AI** | Apa saja kategori utama tujuan penggunaan AI oleh responden (*Coding*, *Writing*, *Studying*, *Research*, dan kategori lainnya)? |
| **Distribusi Tipe Pengguna** | Berapa rasio perbandingan proporsi pengguna dari kalangan *Student* dan *Professional*? |
| **Deviasi Kepuasan dari Rata-rata** | Alat AI mana saja yang mencatatkan deviasi skor kepuasan di atas atau di bawah rata-rata global? |

## Data Preparation & Calculated Fields (Power BI DAX)

- **Standardisasi Kategori Tujuan (`Purpose_Clean` / `AI_Purpose`):** Mengelompokkan teks deskripsi tujuan penggunaan AI ke dalam kategori terstruktur seperti *Coding*, *Writing*, *Studying*, *Research*, dan *Lainnya* menggunakan Power Query.
- **Pembuatan Indeks & Urutan Bulan (`Month_Name` & `Month_Num`):** Menyusun urutan kronologis bulan dari Januari hingga Desember agar analisis tren waktu tampil secara akurat dan tidak terurut berdasarkan abjad.
- **Kalkulasi Metrik Utama (DAX Measures):** Membangun *measure* dinamis seperti `Total Usage`, `Student`, `Professional`, `Satisfaction_Score`, dan persentase pangsa pasar untuk mendukung visualisasi multi-seri pada grafik.
- **Standardisasi Format Angka & Desimal:** Mengatur format dan presisi angka pada kartu ringkasan serta sumbu koordinat agar tampilan data seragam dan mudah dibaca.

## Visualizations & Dashboard Layout (Power BI)

- **Market Share of AI Tools (Donut Chart):** Diagram donat dengan metrik pusat total pengguna sebanyak **300 responden** yang memetakan persentase penggunaan berbagai alat AI, seperti ChatGPT (**40.67%**), Google Gemini (**13.67%**), Microsoft Copilot (**12%**), Claude (**10.33%**), Perplexity AI (**8.33%**), Grammarly (**4.67%**), dan DeepSeek (**3.33%**).
- **Impact on Productivity & Time Saved (Scatter Plot):** Diagram pencar (*scatter plot*) yang memetakan hubungan antara skor produktivitas dan estimasi waktu yang dihemat per minggu, dibedakan berdasarkan tipe pengguna (*Professional* vs. *Student*) dengan garis tren regresi.
- **Satisfaction Score of Top 5 AI Tools (Clustered Bar Chart):** Diagram batang horizontal yang mengurutkan lima alat AI teratas berdasarkan skor kepuasan rata-rata, yaitu Microsoft Copilot (**6.31**), ChatGPT (**6.24**), Claude (**6.10**), Perplexity AI (**5.92**), dan Google Gemini (**5.73**).
- **Usage Trend by User Type (Area Chart):** Grafik area multi-seri yang memperlihatkan tren total jam penggunaan AI (*Total Usage*), baik secara keseluruhan maupun berdasarkan kelompok *Student* dan *Professional* sepanjang Januari hingga Desember.
- **AI Usage Purpose (Donut Chart):** Diagram donat yang memetakan tujuan utama penggunaan AI, meliputi *Coding* (**23.33%**), *Writing* (**26%**), *Studying* (**13.67%**), *Research* (**21.67%**), dan *Lainnya* (**15.33%**).
- **User Type Distribution (Donut Chart):** Diagram donat yang menunjukkan komposisi pengguna berdasarkan tipe, yaitu *Student* (**52.67%**) dan *Professional* (**47.33%**).
- **AI Tools Satisfaction Deviation from Average (Diverging Bar Chart):** Diagram batang horizontal bipolar yang menunjukkan deviasi skor kepuasan setiap alat AI terhadap rata-rata global. Microsoft Copilot dan Grammarly berada pada sisi deviasi positif, sedangkan Google Gemini dan Perplexity AI berada pada sisi deviasi negatif.

## Key Business Insights

- **Dominasi Pasar ChatGPT:** ChatGPT memiliki pangsa penggunaan terbesar (**40.67%**) di antara responden, diikuti oleh Google Gemini dan Microsoft Copilot.
- **Korelasi Positif Produktivitas dan Penghematan Waktu:** Peningkatan skor produktivitas menunjukkan hubungan positif dengan estimasi waktu yang dihemat per minggu pada kedua kelompok pengguna, yaitu *Student* dan *Professional*.
- **Kepuasan Tertinggi pada Microsoft Copilot:** Meskipun pangsa penggunaannya lebih rendah dibandingkan ChatGPT, Microsoft Copilot memperoleh skor kepuasan rata-rata tertinggi sebesar **6.31 dari 10**.
- **Fokus Penggunaan Utama:** Aktivitas *Writing* (**26%**) dan *Coding* (**23.33%**) menjadi dua tujuan penggunaan AI dengan proporsi terbesar di antara responden.

## Strategic Recommendations

- **Optimalisasi Fitur Coding dan Writing:** Mengembangkan modul pelatihan atau panduan penggunaan *prompt* khusus untuk mendukung aktivitas *Writing* dan *Coding* yang menjadi dua tujuan penggunaan AI terbesar.
- **Peningkatan Adopsi Alat Alternatif:** Mendorong pemanfaatan fitur-fitur unggulan dari alat AI dengan tingkat kepuasan tinggi, seperti Microsoft Copilot, agar dapat dimanfaatkan secara lebih luas dalam aktivitas sehari-hari.
- **Personalisasi Pengalaman Berdasarkan Segmen:** Menyesuaikan rekomendasi dan fungsionalitas AI berdasarkan kebutuhan masing-masing kelompok pengguna, yaitu *Student* (**52.67%**) dan *Professional* (**47.33%**).

## Tools Used

- **Google Colab (Python / Pandas):** Lingkungan komputasi berbasis *cloud* yang digunakan untuk pembersihan data awal, transformasi kategori *purpose*, serta validasi struktur dataset.
- **Power BI Desktop:** Platform visualisasi utama untuk pemodelan data (*Data Modeling*), pembuatan *calculated measures*, pengaturan tema visual dengan tata letak berbingkai putih bersih, serta penyusunan kartu metrik ringkasan.
- **Dataset:** `AI_Usage_and_Impact_on_Students_and_Professionals` (**N = 300** sampel responden), yang mencakup data demografi pengguna, metrik penggunaan AI, estimasi penghematan waktu, skor produktivitas, tingkat kepuasan, dan preferensi alat AI.

### Dashboard Summary Metrics

| Metric | Value |
| :--- | :--- |
| Total Users | 300 |
| Average Usage Hours/Day | 25.61 hrs |
| Estimated Time Saved | 54.03 hrs/wk |
| Average Satisfaction Score | 6.15 / 10 |
