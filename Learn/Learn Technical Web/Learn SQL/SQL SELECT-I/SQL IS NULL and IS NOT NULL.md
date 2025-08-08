### **1. Apa Itu NULL?**

- **NULL** adalah nilai kosong (tidak ada data).
- Artinya, kolom tidak memiliki nilai sama sekali. NULL bukan angka, teks, spasi, atau nol (**0**).
- Misalnya, jika seseorang belum mengisi email, maka nilai email mereka akan menjadi NULL.

---

### **2. Apa Fungsi IS NULL dan IS NOT NULL?**

- **IS NULL** digunakan untuk mencari baris yang **tidak memiliki data** di kolom tertentu.
- **IS NOT NULL** digunakan untuk mencari baris yang **memiliki data** di kolom tertentu.

---

### **3. Sintaks IS NULL dan IS NOT NULL**

#### **a. IS NULL**

```sql
SELECT column1, column2, ...
FROM table
WHERE column_name IS NULL;
```

- **column_name** adalah kolom yang ingin diperiksa apakah NULL.
- **table** adalah nama tabel tempat kita mengambil data.

#### **b. IS NOT NULL**

```sql
SELECT column1, column2, ...
FROM table
WHERE column_name IS NOT NULL;
```

- Sama seperti IS NULL, tetapi digunakan untuk mencari kolom yang tidak NULL.

---

### **4. Contoh Penggunaan**

#### **a. Menggunakan IS NULL**

```sql
SELECT *
FROM Employee
WHERE email IS NULL;
```

**Penjelasan:**
- Pilih semua kolom (`*`) dari tabel `Employee`.
- Cari baris di mana kolom `email` kosong (NULL).

#### **b. Menggunakan IS NOT NULL**

```sql
SELECT *
FROM Employee
WHERE email IS NOT NULL;
```

**Penjelasan:**
- Pilih semua kolom (`*`) dari tabel `Employee`.
- Cari baris di mana kolom `email` memiliki nilai (tidak kosong).

---

### **5. Menggunakan IS NULL dengan COUNT()**

#### **a. Menghitung Baris NULL**


```sql
SELECT COUNT(*)
FROM Employee
WHERE email IS NULL;
```

**Penjelasan:**
Hitung jumlah baris di tabel `Employee` di mana kolom `email` kosong (NULL).

#### **b. Menghitung Baris yang Tidak NULL**

```sql
SELECT COUNT(*)
FROM Employee
WHERE email IS NOT NULL;
```

**Penjelasan:**
 Hitung jumlah baris di tabel `Employee` di mana kolom `email` memiliki nilai (tidak kosong).