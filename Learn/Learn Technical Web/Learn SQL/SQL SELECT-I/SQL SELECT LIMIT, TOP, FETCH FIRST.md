### **LIMIT dengan OFFSET** (Digunakan di MySQL, PostgreSQL, SQLite)

- **LIMIT** digunakan untuk membatasi jumlah baris yang dipilih.
- **OFFSET** digunakan untuk melewati sejumlah baris awal.

#### Contoh:
```sql
SELECT first_name, last_name
FROM Customers
LIMIT 2 OFFSET 3;
```
- **LIMIT 2**: Ambil 2 baris data.
- **OFFSET 3**: Lewati 3 baris pertama, mulai dari baris keempat.

**Hasilnya:** Baris ke-4 dan ke-5 dari tabel akan diambil.

---

### **TOP** (Digunakan di SQL Server, MS Access)

- **TOP** berfungsi mirip dengan **LIMIT**, tetapi digunakan di sistem basis data seperti SQL Server.

#### Contoh:

```sql
SELECT TOP 2 first_name, last_name
FROM Customers;
```

- **TOP 2**: Ambil 2 baris pertama dari tabel.

Jika ingin memilih semua kolom, gunakan tanda bintang (*):

```sql
SELECT TOP 2 *
FROM Customers;
```

**Hasilnya:** 2 baris pertama dari semua kolom diambil.

---

### **FETCH FIRST** (Digunakan di Oracle, PostgreSQL, DB2)

- Digunakan untuk mengambil sejumlah baris pertama dari tabel.

#### Contoh:

```sql
SELECT *
FROM Customers
FETCH FIRST 2 ROWS ONLY;
```

- **FETCH FIRST 2 ROWS ONLY**: Ambil 2 baris pertama dari tabel.

**Hasilnya:** Baris pertama dan kedua dari tabel akan diambil.

---

### Perbandingan Sintaks di Berbagai DBMS:

|**Keyword**|**Sistem Basis Data**|
|---|---|
|**LIMIT**|MySQL, PostgreSQL, SQLite|
|**TOP**|SQL Server, MS Access|
|**FETCH FIRST**|Oracle, PostgreSQL (SQL:2008), DB2|

---

