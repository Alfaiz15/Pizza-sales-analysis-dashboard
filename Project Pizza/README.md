# 🍕 Data-Driven Operations: Analisis Kinerja Penjualan Pizza (2015)

## 📌 Ringkasan Eksekutif (Executive Summary)

Proyek ini mendemonstrasikan kemampuan Data Analysis (Fokus: **Operations**) dalam mengubah data transaksi mentah selama satu tahun menjadi *actionable insights*. Seluruh proses analisis dilakukan secara efisien menggunakan **Microsoft Excel/Google Sheets**, menghasilkan *Interactive Dashboard* yang menjadi panduan utama bagi manajemen untuk **Optimasi Revenue**, **Forecasting**, dan **Efisiensi Inventaris**.

## 🎯 Tujuan Proyek (Business Objectives)

Analisis ini berfokus menjawab empat pertanyaan bisnis krusial:

1.  **KPI Performance:** Berapa Total Revenue, Total Order, dan **Average Order Value (AOV)**?
2.  **Market Trends:** Bagaimana tren pendapatan bulanan (*Seasonality*) sepanjang tahun?
3.  **Product Prioritization:** Apa saja **10 Pizza Terlaris** (*Top Sellers*) berdasarkan kuantitas?
4.  **Pricing Strategy:** Bagaimana kontribusi Revenue berdasarkan **Kategori** dan **Ukuran** pizza?

## 🛠️ Tools dan Data

* **Primary Tool:** Microsoft Excel / Google Sheets
* **Data Source:** `Data Pizza.xlsx - Raw Data Pizza Sales.csv` (Daily Transaction Data)

---

## ⚙️ Workflow Analisis (Excel/Sheets Focused)

### Fase 1: Data Cleansing & Feature Engineering

Menciptakan variabel (`Features`) baru dari data mentah untuk mendukung analisis yang lebih dalam.

| Kolom Baru | Perhitungan | Fungsi Excel Kunci | Tujuan Bisnis |
| :--- | :--- | :--- | :--- |
| **Total Revenue** | Harga x Kuantitas | **`= unit_price * quantity`** | Metrik keuangan dasar. |
| **Nama Bulan** | Ekstraksi Bulan dari tanggal. | **`=TEXT(order_date, "mmmm")`** | Analisis *Seasonality* & *Forecasting*. |
| **Nama Hari** | Ekstraksi Hari dari tanggal. | **`=TEXT(order_date, "dddd")`** | Analisis *Workload* & Jadwal Staf. |
| **Total Order Unik** | Agregasi ID pesanan unik. | **`=COUNTA(UNIQUE(order_id_column))`** | Mengukur *Transaction Volume*. |

### Fase 2: Pivot Table (The Engine Room)

Menggunakan **Pivot Table** sebagai mesin analisis utama untuk merangkum data dan menjawab *Business Questions*.

1.  **KPI Summary:** Digunakan untuk menghitung *Total Revenue*, *Total Order*, dan AOV ($\frac{\text{Total Revenue}}{\text{Total Order}}$).
2.  **Revenue & Quantity:** Dibuat *Pivot* terpisah untuk `Nama Bulan` (untuk *Line Chart*) dan `pizza_name` (untuk *Top 10 List*).
3.  **Segmentasi Kompleks:** Rows: `pizza_category`, Columns: `pizza_size`, Values: `SUM of Total Revenue` (untuk analisis kontribusi **Size**).

### Fase 3: Dashboard dan Interaktivitas

Visualisasi yang *clear* dan *concise* untuk komunikasi wawasan yang efektif.

| Visualisasi | Tipe Chart | Wawasan yang Diperkuat |
| :--- | :--- | :--- |
| **Tren Revenue Bulanan** | Line Chart | Menunjukkan *Seasonality* jelas (**Puncak Juli**, **Lembah September**) untuk *planning*. |
| **Quantity per Category** | Donut Chart | Prioritas *Inventory*: **Classic (30%)** dan **Supreme (24%)** mendominasi volume. |
| **Revenue by Size** | Stacked Bar Chart | Strategi *Upselling*: Ukuran **Large (L)** adalah *Revenue Driver* utama. |
| **Interaktivitas** | Slicer |
