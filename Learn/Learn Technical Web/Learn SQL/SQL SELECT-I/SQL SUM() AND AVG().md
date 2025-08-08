### **1. SQL SUM() Function**

Fungsi **SUM()** digunakan untuk menghitung jumlah total dari nilai-nilai numerik dalam sebuah kolom.

#### **Sintaks Dasar:**

```sql
SELECT SUM(column_name)
FROM table;
```

- **SUM**: Fungsi yang menghitung jumlah total dari nilai dalam kolom.
- **column_name**: Nama kolom yang ingin dihitung jumlahnya.
- **table**: Nama tabel tempat data diambil.

#### **Contoh Penggunaan SUM():**

##### **a. Menghitung Total Nilai dalam Kolom:**

```sql
SELECT SUM(amount) AS total_sales
FROM Orders;
```

- **Penjelasan:** Menghitung total jumlah dari kolom `amount` di tabel `Orders`. Hasilnya adalah total penjualan semua pesanan.

##### **b. Menghitung Total Berdasarkan Kondisi Tertentu:**

```sql
SELECT SUM(amount) AS total_of_cus4
FROM Orders
WHERE customer_id = 4;
```

- **Penjelasan:** Menghitung total jumlah dari kolom `amount` untuk pesanan yang dilakukan oleh pelanggan dengan `customer_id` = 4.

---

### **2. SQL AVG() Function**

Fungsi **AVG()** digunakan untuk menghitung nilai rata-rata dari data numerik dalam kolom.

#### **Sintaks Dasar:**

```sql
SELECT AVG(column_name)
FROM table;
```

- **AVG**: Fungsi yang menghitung nilai rata-rata dari kolom yang dipilih.
- **column_name**: Nama kolom yang ingin dihitung rata-ratanya.
- **table**: Nama tabel tempat data diambil.

#### **Contoh Penggunaan AVG():**

##### **a. Menghitung Rata-Rata Nilai dari Kolom:**

```sql
SELECT AVG(age) AS average_age
FROM Customers;
```

- **Penjelasan:** Menghitung rata-rata usia semua pelanggan yang ada dalam tabel `Customers`.

##### **b. Menghitung Rata-Rata Berdasarkan Kondisi Tertentu:**

```sql
SELECT customer_id, AVG(amount) AS average_spends
FROM Orders
GROUP BY customer_id;
```

- **Penjelasan:** Menghitung rata-rata jumlah uang yang dibelanjakan oleh setiap pelanggan di tabel `Orders`. Hasilnya akan menunjukkan rata-rata pengeluaran masing-masing pelanggan, dengan `GROUP BY` yang mengelompokkan berdasarkan `customer_id`.

---

