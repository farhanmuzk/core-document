### **Apa itu SQL HAVING Clause?**

**HAVING Clause** digunakan untuk **menyaring hasil dari data yang sudah dikelompokkan** (grouped data), biasanya berdasarkan fungsi agregat seperti:

- **COUNT()**: Menghitung jumlah baris.
- **SUM()**: Menjumlahkan nilai.
- **AVG()**: Menghitung rata-rata.
- **MAX()**: Menemukan nilai maksimum.
- **MIN()**: Menemukan nilai minimum.

### **Kenapa Tidak Pakai WHERE?**

- **WHERE** hanya bisa digunakan untuk menyaring baris individu sebelum data dikelompokkan.
- **HAVING** digunakan untuk menyaring **kelompok data (groups)** setelah data dikelompokkan menggunakan `GROUP BY`.

---

### **Cara Kerja HAVING Clause**

Format:

sql

Salin kode

`SELECT AggFunc(column), extra_columns FROM table GROUP BY target_column HAVING condition;`

**Penjelasan**:

1. **AggFunc(column)**: Fungsi agregat yang digunakan (misalnya, `SUM()`, `COUNT()`).
2. **extra_columns**: Kolom tambahan yang ingin ditampilkan.
3. **GROUP BY target_column**: Mengelompokkan data berdasarkan kolom tertentu.
4. **HAVING condition**: Menyaring hasil dari kelompok data.

---

### **Contoh Sederhana**

#### **1. Menggunakan HAVING dengan COUNT()**

**Soal**: Tampilkan nama depan pelanggan yang memiliki lebih dari 1 usia yang tercatat di tabel.

sql

Salin kode

`SELECT COUNT(age) AS Count, first_name FROM Customers GROUP BY first_name HAVING COUNT(age) > 1;`

**Penjelasan**:

1. **COUNT(age)**: Menghitung jumlah baris untuk setiap **first_name**.
2. **GROUP BY first_name**: Mengelompokkan data berdasarkan nama depan pelanggan.
3. **HAVING COUNT(age) > 1**: Menyaring kelompok yang jumlah usianya lebih dari 1.

---

#### **2. Menggunakan HAVING dengan SUM()**

**Soal**: Tampilkan jumlah total pesanan per pelanggan yang totalnya kurang dari 500.

sql

Salin kode

`SELECT customer_id, SUM(amount) AS total FROM Orders GROUP BY customer_id HAVING SUM(amount) < 500;`

**Penjelasan**:

1. **SUM(amount)**: Menjumlahkan nilai pesanan untuk setiap pelanggan (**customer_id**).
2. **GROUP BY customer_id**: Mengelompokkan data berdasarkan ID pelanggan.
3. **HAVING SUM(amount) < 500**: Menampilkan kelompok pelanggan yang total pesanannya kurang dari 500.

---

### **Perbedaan WHERE dan HAVING**

|**HAVING Clause**|**WHERE Clause**|
|---|---|
|Digunakan untuk menyaring hasil **kelompok data**.|Digunakan untuk menyaring **baris individu**.|
|Bisa digunakan dengan fungsi agregat seperti `SUM()`, `COUNT()`.|Tidak bisa digunakan dengan fungsi agregat.|
|Dieksekusi setelah `GROUP BY`.|Dieksekusi sebelum `GROUP BY`.|

#### **Contoh Perbedaan**

1. **WHERE** untuk menyaring baris:
    
    sql
    
    Salin kode
    
    `SELECT customer_id, amount FROM Orders WHERE amount < 500;`
    
    **Artinya**: Hanya menampilkan pesanan dengan jumlah kurang dari 500 **sebelum dikelompokkan**.
    
2. **HAVING** untuk menyaring kelompok:
    
    sql
    
    Salin kode
    
    `SELECT customer_id, SUM(amount) AS total FROM Orders GROUP BY customer_id HAVING SUM(amount) < 500;`
    
    **Artinya**: Menampilkan pelanggan dengan total pesanan kurang dari 500 **setelah dikelompokkan**.