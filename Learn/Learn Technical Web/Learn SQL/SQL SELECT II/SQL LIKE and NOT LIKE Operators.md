### Apa itu SQL **LIKE**?

**`LIKE`** adalah operator yang digunakan untuk **mencocokkan pola string** dalam kolom data tertentu. Biasanya digunakan dalam klausa **`WHERE`** untuk mencari nilai yang cocok dengan pola tertentu, seperti nama yang dimulai dengan huruf tertentu atau mengandung kata tertentu.

Misalnya, kamu ingin mencari semua pelanggan yang tinggal di **UK**:

```sql
SELECT first_name
FROM Customers
WHERE country LIKE 'UK';
```

**Penjelasan**:

- Di sini, **`LIKE`** digunakan untuk **mencocokkan** negara **`UK`** dalam kolom **`country`**. Hasilnya adalah daftar nama depan (**`first_name`**) pelanggan yang tinggal di UK.

### **`LIKE`** Dengan Wildcards (Karakter Pengganti)

SQL **`LIKE`** dapat bekerja dengan **wildcards** atau **karakter pengganti** untuk mencocokkan pola yang lebih fleksibel. Dua wildcard yang sering digunakan adalah:

1. **`%` (Persen)**: Digunakan untuk mencocokkan **zero atau lebih karakter**.
2. **`_` (Underscore)**: Digunakan untuk mencocokkan **satu karakter**.

#### Contoh penggunaan **`%`** wildcard:

Misalnya, kita ingin mencari semua pelanggan yang namanya **dimulai dengan "A"**:

sql

Salin kode

`SELECT first_name FROM Customers WHERE first_name LIKE 'A%';`

- **`'A%'`** berarti nama yang **dimulai dengan "A"** dan diikuti oleh **zero atau lebih karakter**. Ini akan mencocokkan nama seperti **Alice**, **Adam**, **Alex**, dan lainnya.

#### Contoh penggunaan **`_`** wildcard:

Misalnya, kita ingin mencari semua nama depan yang **terdiri dari 4 huruf** dan dimulai dengan huruf **"A"**:

sql

Salin kode

`SELECT first_name FROM Customers WHERE first_name LIKE 'A___';`

- **`'A___'`** berarti nama yang **dimulai dengan "A"** dan diikuti oleh **tiga karakter lainnya** (total 4 karakter). Ini akan mencocokkan nama seperti **Anna**, **Aida**, dll.

### Apa itu **SQL NOT LIKE**?

**`NOT LIKE`** adalah kebalikan dari **`LIKE`**. Ini digunakan untuk mencari data yang **tidak sesuai dengan pola tertentu**.

Contoh, jika kita ingin mencari pelanggan yang **tidak tinggal di USA**:

sql

Salin kode

`SELECT * FROM Customers WHERE country NOT LIKE 'USA';`

- **`NOT LIKE 'USA'`** akan mencocokkan **semua negara yang bukan USA**. Hasilnya adalah daftar pelanggan yang tidak tinggal di USA.

### **LIKE** dengan Banyak Pola

Kamu bisa menggunakan **`LIKE`** dengan beberapa pola sekaligus, menggunakan operator **`OR`**. Misalnya, kita ingin mencari pelanggan dengan nama belakang (**`last_name`**) yang:

- **Dimulai dengan "R" dan diakhiri dengan "t"**, atau
- **Diakhiri dengan huruf "e"**.

Query-nya akan seperti ini:

sql

Salin kode

`SELECT * FROM Customers WHERE last_name LIKE 'R%t' OR last_name LIKE '%e';`

**Penjelasan**:

- **`last_name LIKE 'R%t'`** mencari nama belakang yang **dimulai dengan "R" dan diakhiri dengan "t"** (misalnya, **"Roth"**).
- **`last_name LIKE '%e'`** mencari nama belakang yang **diakhiri dengan huruf "e"** (misalnya, **"Jone"**).

Dengan menggunakan **`OR`**, kamu bisa mencocokkan **dua pola yang berbeda** dalam satu query.