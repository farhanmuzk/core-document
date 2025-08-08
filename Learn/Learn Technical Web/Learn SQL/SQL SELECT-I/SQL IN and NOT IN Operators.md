### **1. IN Operator**

**Fungsi:**  
Digunakan dengan klausa **WHERE** untuk mencocokkan nilai dalam daftar tertentu.

#### **Contoh Dasar:**

```sql
SELECT first_name, country
FROM Customers
WHERE country IN ('USA', 'UK');
```

- **Penjelasan:**
    - Kolom `country` diperiksa apakah nilainya ada di dalam daftar `('USA', 'UK')`.
    - Baris dengan `country = 'USA'` atau `country = 'UK'` akan dipilih.

---

### **2. NOT IN Operator**

**Fungsi:**  
Kebalikan dari **IN**. Digunakan untuk mengecualikan baris yang cocok dengan nilai dalam daftar.

#### **Contoh:**

```sql
SELECT first_name, country
FROM Customers
WHERE country NOT IN ('UK', 'UAE');
```

- **Penjelasan:**
    - Baris dengan `country = 'UK'` atau `country = 'UAE'` akan **dikeluarkan**.
    - Baris lainnya tetap diambil.

---

### **3. IN Operator dengan Nilai Unik (Ignoring Duplicates)**

- Jika ada nilai duplikat dalam daftar, SQL akan mengabaikannya.  
    Contoh:
    
```sql
SELECT first_name, country
FROM Customers
WHERE country IN ('USA', 'UK', 'USA');
```

Setara dengan :

```sql
SELECT first_name, country
FROM Customers
WHERE country IN ('USA', 'UK');
```
---

### **4. IN Operator dengan Subquery**

**Fungsi:**  
**IN** bisa digunakan dengan subquery untuk memeriksa apakah nilai di kolom tertentu ada dalam hasil subquery.

#### **Contoh:**

```sql
SELECT customer_id, first_name
FROM Customers 
WHERE customer_id IN (
  SELECT customer_id
  FROM Orders
);
```

- **Penjelasan:**
    - Subquery: `SELECT customer_id FROM Orders` memilih semua `customer_id` dari tabel `Orders`.
    - Query Utama: Memilih data dari tabel `Customers` di mana `customer_id` juga muncul dalam hasil subquery.

---

### **5. Contoh Sederhana untuk Memahami**

#### **IN**:

- **Pertanyaan**: "Cari pelanggan yang tinggal di USA atau UK."
```sql
SELECT first_name
FROM Customers
WHERE country IN ('USA', 'UK');
```
#### **NOT IN**:

- **Pertanyaan**: "Cari pelanggan yang **tidak** tinggal di UK atau UAE."
```sql
SELECT first_name
FROM Customers
WHERE country NOT IN ('UK', 'UAE');
```
#### **IN dengan Subquery**:

- **Pertanyaan**: "Cari pelanggan yang telah melakukan pemesanan."
```sql
SELECT first_name
FROM Customers
WHERE customer_id IN (
  SELECT customer_id
  FROM Orders
);
```

---
