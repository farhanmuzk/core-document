### Apa itu `ORDER BY` dalam SQL?

`ORDER BY` adalah perintah SQL yang digunakan untuk mengurutkan hasil query berdasarkan kolom tertentu. Kamu bisa mengurutkannya dalam urutan **menaik (ascending)** atau **menurun (descending)**.

### Contoh Penggunaan `ORDER BY`

Misalnya, kita memiliki tabel **Customers** dan ingin mengurutkan data berdasarkan kolom **country** secara menaik (default adalah menaik):

```sql
SELECT *
FROM Customers
ORDER BY country;
```

Perintah ini akan menampilkan semua data dari tabel **Customers** dan mengurutkannya berdasarkan kolom **country** secara menaik (A-Z).

### Sintaks Dasar `ORDER BY`

```sql
SELECT column1, column2, ...
FROM table
ORDER BY columnA, columnB, ...;
```

- **column1, column2, ...**: Kolom yang ingin ditampilkan.
- **table**: Nama tabel dari mana data diambil.
- **columnA, columnB, ...**: Kolom yang digunakan untuk mengurutkan data.

### Mengurutkan Secara Ascending (`ASC`)

Kamu bisa secara eksplisit menambahkan kata kunci **ASC** untuk mengurutkan data secara **menaik (dari terkecil ke terbesar)**. Misalnya, untuk mengurutkan berdasarkan kolom **age**:

```sql
SELECT *
FROM Customers
ORDER BY age ASC;
```

Namun, **ASC** sebenarnya adalah nilai default, jadi kamu bisa menulisnya tanpa kata kunci **ASC** dan hasilnya tetap sama:

```sql
SELECT *
FROM Customers
ORDER BY age;
```

### Mengurutkan Secara Descending (`DESC`)

Untuk mengurutkan secara **menurun (dari terbesar ke terkecil)**, kamu menggunakan kata kunci **DESC**. Contohnya, untuk mengurutkan berdasarkan **age** secara menurun:

```sql
SELECT *
FROM Customers
ORDER BY age DESC;
```

### Mengurutkan Berdasarkan Banyak Kolom

Kamu juga bisa mengurutkan berdasarkan lebih dari satu kolom. Misalnya, jika ingin mengurutkan berdasarkan **first_name** dan kemudian berdasarkan **age**:

```sql
SELECT *
FROM Customers
ORDER BY first_name, age;
```

Jika ada beberapa data dengan **first_name** yang sama, maka pengurutan berikutnya akan dilakukan berdasarkan **age**.

### Menggunakan `ORDER BY` dengan `WHERE`

Kamu bisa menggabungkan **WHERE** dan **ORDER BY** untuk memfilter dan mengurutkan data. Misalnya, untuk memilih data pelanggan yang **bukan dari UK**, dan mengurutkannya berdasarkan **last_name** secara menurun:

```sql
SELECT last_name, age
FROM Customers
WHERE NOT country = 'UK'
ORDER BY last_name DESC;
```

Perhatikan bahwa **WHERE** selalu ditempatkan sebelum **ORDER BY**.