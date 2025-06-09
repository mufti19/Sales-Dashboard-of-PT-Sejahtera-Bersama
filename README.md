# Case Study: Data Penjualan PT Sejahtera Bersama

## Pendahuluan
Sebagai seorang BI Analyst di PT Sejahtera Bersama, tugas utama adalah menganalisis data penjualan untuk memberikan wawasan yang dapat membantu perusahaan meningkatkan kinerja penjualan. Studi kasus ini mencakup identifikasi struktur data, pembuatan tabel master, dan visualisasi data menggunakan Looker Studio.

---

## 1. Identifikasi Primary Key dan Foreign Key
### Primary Key (PK) dan Foreign Key (FK)
Berdasarkan dataset yang diberikan, berikut adalah identifikasi primary key dan foreign key untuk setiap tabel:

- **Tabel `Order`**:
  - **Primary Key**: `OrderID`
  - **Foreign Key**: 
    - `CustomerID` (menghubungkan ke tabel `Customer`)
    - `ProdNumber` (menghubungkan ke tabel `Products`)

- **Tabel `Products`**:
  - **Primary Key**: `ProdNumber`
  - **Foreign Key**: 
    - `Category` (menghubungkan ke tabel `ProductCategory`)

- **Tabel `Customer`**:
  - **Primary Key**: `CustomerID`

- **Tabel `ProductCategory`**:
  - **Primary Key**: `CategoryID`

---

## 2. Relasi Antar Tabel
### Hubungan Antar Tabel
- **Customer ke Order**:
  - **Relasi**: One-to-Many
  - **Penjelasan**: Satu pelanggan (`CustomerID`) dapat memiliki banyak pesanan (`OrderID`).

- **Order ke Products**:
  - **Relasi**: Many-to-One
  - **Penjelasan**: Banyak pesanan (`OrderID`) dapat berisi produk yang sama (`ProdNumber`).

- **Products ke ProductCategory**:
  - **Relasi**: Many-to-One
  - **Penjelasan**: Banyak produk (`ProdNumber`) dapat termasuk dalam satu kategori produk (`CategoryID`).

---

## 3. Pembuatan Tabel Master
### Tugas
Membuat tabel master yang berisi informasi berikut:
- **CustomerEmail**, **CustomerCity**, **OrderDate**, **OrderQty**, **ProductName**, **ProductPrice**, **ProductCategoryName**, dan **TotalSales**.
- Data diurutkan berdasarkan tanggal transaksi dari yang paling awal hingga yang paling akhir.

### Langkah-Langkah
1. **Gabungkan Tabel**:
   - Gunakan relasi antar tabel untuk menggabungkan data dari tabel `Order`, `Products`, `Customer`, dan `ProductCategory`.
2. **Hitung Total Sales**:
   - Rumus: `TotalSales = OrderQty * ProductPrice`.
3. **Urutkan Data**:
   - Urutkan berdasarkan kolom `OrderDate` secara ascending.

---

## 4. Visualisasi Data Penjualan
### Tugas
Membuat visualisasi menggunakan Looker Studio berdasarkan tabel master. Visualisasi yang dibuat mencakup:
1. **Total Keseluruhan Sales**.
2. **Total Sales Berdasarkan Kategori Produk**.
3. **Total Kuantitas Berdasarkan Kategori Produk**.
4. **Total Sales Berdasarkan Kota**.
5. **Total Kuantitas Berdasarkan Kota**.
6. **Top 5 Kategori Produk dengan Penjualan Tertinggi**.
7. **Top 5 Kategori Produk dengan Kuantitas Tertinggi**.

### Contoh Visualisasi
- **Bar Chart**: Total sales berdasarkan kategori produk.
- **Pie Chart**: Distribusi sales berdasarkan kota pelanggan.
- **Line Chart**: Tren total sales dari waktu ke waktu.
- **Table**: Top 5 kategori produk berdasarkan sales dan kuantitas.

---

## 5. Rekomendasi untuk Meningkatkan Penjualan
### Analisis dan Rekomendasi
1. **Fokus pada Kategori dengan Penjualan Tertinggi**:
   - Tingkatkan promosi untuk kategori seperti "Robots" dan "Drones".
2. **Optimalkan Penjualan di Kota dengan Potensi Tinggi**:
   - Perkuat strategi pemasaran di kota seperti Washington dan Houston.
3. **Analisis Produk dengan Penjualan Rendah**:
   - Evaluasi kategori dengan kontribusi kecil untuk menentukan apakah perlu ditingkatkan atau dihentikan.
4. **Penawaran Khusus Berdasarkan Pola Musiman**:
   - Gunakan tren penjualan berdasarkan waktu untuk merancang promosi musiman.

---
