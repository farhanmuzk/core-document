	### Apa itu `GROUP BY` dalam SQL?

Perintah **`GROUP BY`** dalam SQL digunakan untuk mengelompokkan baris data berdasarkan nilai kolom tertentu. Hal ini sangat berguna ketika kita ingin melakukan operasi agregat seperti **COUNT()**, **SUM()**, **AVG()**, **MIN()**, dan **MAX()**.

### Sintaks Dasar `GROUP BY`

sql

Salin kode

`SELECT column1, column2, ... FROM table GROUP BY columnA, columnB, ...;`

- **column1, column2, ...**: Kolom yang ingin ditampilkan dalam hasil.
- **table**: Nama tabel dari mana data diambil.
- **columnA, columnB, ...**: Kolom-kolom yang akan digunakan untuk mengelompokkan data.

### Contoh Penggunaan `GROUP BY`

#### 1. Menghitung Jumlah Pesanan untuk Setiap Item

Misalnya, kita ingin menghitung berapa banyak pesanan yang ada untuk setiap item dalam tabel **Orders**:

sql

Salin kode

`SELECT COUNT(order_id), item FROM Orders GROUP BY item;`

Di sini, perintah **`COUNT(order_id)`** menghitung jumlah pesanan untuk setiap item, dan **`GROUP BY item`** mengelompokkan data berdasarkan nama item.

#### 2. Menghitung Jumlah Pelanggan per Negara

Untuk menghitung jumlah pelanggan berdasarkan negara:

sql

Salin kode

`SELECT country, COUNT(*) AS number FROM Customers GROUP BY country;`

Perintah ini mengelompokkan data berdasarkan kolom **country** dan menghitung jumlah pelanggan di setiap negara menggunakan fungsi **COUNT()**.

#### 3. Menghitung Total Pengeluaran Setiap Pelanggan

Misalnya, untuk menghitung total jumlah yang dibelanjakan oleh setiap pelanggan:

sql

Salin kode

`SELECT customer_id, SUM(amount) AS total FROM Orders GROUP BY customer_id;`

Perintah ini mengelompokkan data berdasarkan **customer_id** dan menghitung total pengeluaran untuk setiap pelanggan dengan fungsi **SUM()**.

### Menggunakan `GROUP BY` dengan `JOIN`

Kamu juga bisa menggabungkan **`GROUP BY`** dengan perintah **`JOIN`** untuk mengelompokkan data setelah menggabungkan dua tabel. Misalnya, kita ingin mengetahui berapa banyak pesanan yang dilakukan oleh setiap pelanggan:

sql

Salin kode

`SELECT Customers.customer_id, Customers.first_name,        COUNT(Orders.order_id) AS order_count FROM Customers LEFT JOIN Orders ON Customers.customer_id = Orders.customer_id GROUP BY Customers.customer_id;`

Perintah ini menggabungkan tabel **Customers** dan **Orders**, lalu mengelompokkan hasilnya berdasarkan **customer_id** dan menghitung jumlah pesanan untuk setiap pelanggan.

### Menggunakan `GROUP BY` dengan Beberapa Kolom

Kamu dapat mengelompokkan data berdasarkan lebih dari satu kolom. Misalnya, untuk menghitung umur minimum untuk setiap kombinasi negara dan negara bagian:

sql

Salin kode

`SELECT country, state, MIN(age) AS min_age FROM Persons GROUP BY country, state;`

Perintah ini mengelompokkan data berdasarkan **country** dan **state**, lalu menghitung umur minimum di setiap kelompok.

### Menggunakan `GROUP BY` dengan `HAVING`

Kadang-kadang, kita perlu memfilter hasil setelah pengelompokkan dilakukan, yang bisa dilakukan dengan menggunakan **`HAVING`**. **`HAVING`** digunakan untuk memfilter berdasarkan hasil agregat, sedangkan **`WHERE`** digunakan untuk memfilter data sebelum pengelompokkan.

Misalnya, untuk menampilkan negara yang memiliki lebih dari satu pelanggan:

sql

Salin kode

`SELECT COUNT(customer_id), country FROM Customers GROUP BY country HAVING COUNT(customer_id) > 1;`

Perintah ini mengelompokkan data berdasarkan **country** dan menghitung jumlah pelanggan di setiap negara. Hanya negara yang memiliki lebih dari satu pelanggan yang akan ditampilkan dalam hasil karena ada klausa **`HAVING`** yang memfilter berdasarkan hasil agregat **COUNT(customer_id)**.