#### Apa itu SQL JOIN?

SQL `JOIN` digunakan untuk menggabungkan data dari dua atau lebih tabel berdasarkan kolom yang memiliki nilai yang sama. Ini membantu kita mendapatkan data yang saling berkaitan dari tabel-tabel tersebut.

---

### **Contoh JOIN Sederhana**

Kita memiliki dua tabel:

1. **Customers** (Kolom: `customer_id`, `first_name`)
2. **Orders** (Kolom: `customer_id`, `item`)

**Contoh Kode:**

sql

Salin kode

`SELECT Customers.customer_id, Customers.first_name, Orders.item FROM Customers JOIN Orders ON Customers.customer_id = Orders.customer_id;`

**Penjelasan:**

1. `JOIN Orders`: Gabungkan tabel `Customers` dan `Orders`.
2. `ON Customers.customer_id = Orders.customer_id`: Hubungkan kedua tabel berdasarkan kolom `customer_id` yang nilainya sama.
3. Data yang diambil:
    - `customer_id` dan `first_name` dari tabel `Customers`
    - `item` dari tabel `Orders`.

Hasilnya: Data pelanggan yang melakukan pesanan dan barang yang dipesan.

---

### **Jenis-Jenis SQL JOIN**

1. **INNER JOIN**: Mengambil data yang cocok di kedua tabel.
2. **LEFT JOIN**: Mengambil semua data dari tabel kiri, meskipun tidak ada kecocokan di tabel kanan.
3. **RIGHT JOIN**: Mengambil semua data dari tabel kanan, meskipun tidak ada kecocokan di tabel kiri.
4. **FULL OUTER JOIN**: Mengambil semua data, baik yang cocok maupun tidak.

---

### **JOIN dengan Alias**

Alias digunakan untuk membuat query lebih singkat dan mudah dibaca.

**Contoh Kode:**

sql

Salin kode

`SELECT C.customer_id AS ID, C.first_name AS Name, O.item FROM Customers AS C JOIN Orders AS O ON C.customer_id = O.customer_id;`

**Penjelasan:**

- Alias:
    - `Customers` diberi nama `C`
    - `Orders` diberi nama `O`
- Kolom `customer_id` diberi alias `ID`
- Kolom `first_name` diberi alias `Name`

Hasilnya sama, tapi kode lebih bersih.

---

### **JOIN dengan Kondisi (WHERE)**

Kita juga bisa menambahkan kondisi dengan `WHERE`.

**Contoh Kode:**

sql

Salin kode

`SELECT Customers.customer_id, Customers.first_name, Orders.amount FROM Customers JOIN Orders ON Customers.customer_id = Orders.customer_id WHERE Orders.amount >= 500;`

**Penjelasan:**

- Menggabungkan data dari `Customers` dan `Orders`.
- Hanya menampilkan data pesanan dengan jumlah (`amount`) ≥ 500.

---

### **Self JOIN**

`Self JOIN` menghubungkan tabel dengan dirinya sendiri.

**Contoh Kode:**

sql

Salin kode

`SELECT     C1.first_name AS FirstPerson,     C2.first_name AS SecondPerson,     C1.country FROM Customers C1, Customers C2 WHERE C1.country = C2.country AND C1.first_name != C2.first_name;`

**Penjelasan:**

- `C1` dan `C2` adalah alias untuk tabel `Customers`.
- Menampilkan pasangan pelanggan yang berasal dari negara yang sama tetapi memiliki nama berbeda.