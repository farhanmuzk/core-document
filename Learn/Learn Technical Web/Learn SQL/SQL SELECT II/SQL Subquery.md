### 1. **Apa itu Subquery?**

Subquery adalah sebuah query (pertanyaan SQL) yang digunakan **di dalam query lain**. Subquery bisa memberikan nilai atau hasil yang digunakan oleh query utama untuk memfilter atau menghitung data.

### 2. **Contoh Subquery**

Misalnya, kita ingin mencari **nama depan** pelanggan yang memiliki **usia tertinggi**:

```sql
SELECT first_name
FROM Customers
WHERE age = (
    -- subquery: mencari usia tertinggi
    SELECT MAX(age)
    FROM Customers
);
```

**Penjelasan:**

- **Subquery pertama** (`SELECT MAX(age) FROM Customers`): Mencari **usia tertinggi** di tabel **Customers**.
- **Query utama** (`SELECT first_name FROM Customers WHERE age = (...)`): Mencari pelanggan dengan **usia tertinggi**.

### 3. **Sintaks Subquery**

Struktur dasar dari subquery:

```sql
SELECT column
FROM table
WHERE column OPERATOR (
  SELECT column
  FROM table
);
```

- **`column`**: Kolom yang ingin dipilih (baik di query utama atau subquery).
- **`OPERATOR`**: Operator SQL seperti `=`, `<`, `IN` yang menghubungkan query utama dengan subquery.
- **`table`**: Nama tabel yang digunakan dalam query.

### 4. **Contoh Penggunaan Subquery**

#### 4.1 Subquery untuk Mencari Pelanggan dengan Usia Minimum

```sql
SELECT *
FROM Customers
WHERE age = (
  SELECT MIN(age)
  FROM Customers
);
```

Penjelasan:

- **Subquery** mencari usia **terendah** di tabel **Customers**.
- Query utama mengambil pelanggan dengan usia **terendah** tersebut.

#### 4.2 Subquery dengan **IN** Operator

Misalnya, kita ingin menemukan semua pelanggan yang telah membuat pesanan. Gunakan subquery seperti ini:

```sql
SELECT customer_id, first_name
FROM Customers
WHERE customer_id IN (
  SELECT customer_id
  FROM Orders
);
```

Penjelasan:

- Subquery (`SELECT customer_id FROM Orders`) menghasilkan daftar **`customer_id`** yang telah memesan.
- Query utama memilih **`customer_id`** dan **`first_name`** pelanggan yang ada dalam daftar tersebut.

### 5. **Subquery vs JOIN**

Kadang-kadang, kita bisa mendapatkan hasil yang sama baik dengan **subquery** atau **JOIN**. Misalnya, untuk mendapatkan **pelanggan** yang sudah melakukan **pesanan**, bisa menggunakan **JOIN** seperti ini:

```sql
SELECT DISTINCT Customers.customer_id, Customers.first_name
FROM Customers
INNER JOIN Orders
ON Customers.customer_id = Orders.customer_id;
```

Ini akan memberikan hasil yang sama dengan query menggunakan **subquery**:

```sql
SELECT customer_id, first_name
FROM Customers 
WHERE customer_id IN (
  SELECT customer_id
  FROM Orders
);
```

**Catatan:** **JOIN** biasanya lebih efisien daripada **subquery**.