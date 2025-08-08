### **Apa Itu COUNT() di SQL?**

Fungsi **COUNT()** digunakan untuk menghitung jumlah baris dalam sebuah tabel atau kolom yang memenuhi kondisi tertentu. Fungsi ini sangat berguna ketika Anda ingin mengetahui berapa banyak data yang ada dalam tabel atau kolom tertentu.

---

### **Sintaks Dasar COUNT()**

```sql
SELECT COUNT(*)
FROM table;
```

- **COUNT(*)** menghitung jumlah seluruh baris dalam tabel.
- **table** adalah nama tabel yang ingin Anda hitung barisnya.

### **Contoh Penggunaan COUNT()**

#### **a. Menghitung Semua Baris**

```sql
SELECT COUNT(*)
FROM Orders;
```

- **Penjelasan:**
    - Fungsi ini menghitung semua baris yang ada dalam tabel `Orders`.

#### **b. Menghitung Baris Berdasarkan Kolom**

```sql
SELECT COUNT(age)
FROM Customers;
```

- **Penjelasan:**
    - Fungsi ini menghitung baris pada kolom `age` yang memiliki nilai **non-NULL**.
    - **NULL** akan diabaikan dalam penghitungan.

---

### **COUNT() dengan WHERE**

Anda juga bisa mengkombinasikan **COUNT()** dengan klausa **WHERE** untuk menghitung jumlah baris yang memenuhi kondisi tertentu.

```sql
SELECT COUNT(country)
FROM Customers
WHERE country = 'UK';
```

- **Penjelasan:**
    - Menghitung jumlah baris di tabel `Customers` yang kolom `country`-nya bernilai `'UK'`.

---

### **COUNT() dengan DISTINCT**

Jika Anda ingin menghitung jumlah nilai yang **unik**, Anda dapat menggunakan **DISTINCT** di dalam **COUNT()**.

```sql
SELECT COUNT(DISTINCT country)
FROM Customers;
```

- **Penjelasan:**
    - Menghitung jumlah negara yang berbeda (unik) dalam kolom `country` di tabel `Customers`.

---

### **COUNT() dengan GROUP BY**

Fungsi **COUNT()** dapat digunakan bersama dengan **GROUP BY** untuk menghitung jumlah baris berdasarkan grup yang memiliki nilai serupa pada kolom tertentu.

```sql
SELECT country, COUNT(*) AS customers
FROM Customers
GROUP BY country;
```

- **Penjelasan:**
    - Menghitung jumlah pelanggan di setiap negara yang ada dalam tabel `Customers`.
    - **GROUP BY** mengelompokkan data berdasarkan nilai `country`, dan **COUNT()** menghitung jumlah pelanggan di setiap grup tersebut.

---

	### **COUNT() dengan HAVING**

Jika Anda ingin menggunakan **COUNT()** dengan filter lebih lanjut, Anda bisa menggunakan **HAVING**. **HAVING** digunakan untuk memfilter hasil setelah **GROUP BY**.

```sql
SELECT COUNT(customer_id), country
FROM Customers
GROUP BY country
HAVING COUNT(customer_id) > 1;
```

- **Penjelasan:**
    - Mengelompokkan data berdasarkan `country`.
    - Menghitung jumlah pelanggan (`customer_id`) per negara.
	    - Hanya negara yang memiliki lebih dari satu pelanggan yang akan ditampilkan.