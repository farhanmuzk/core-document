### **1. Apa itu BETWEEN Operator?**

**BETWEEN** adalah operator di SQL yang digunakan dengan klausa **WHERE** untuk memilih data dalam **rentang nilai tertentu** (termasuk batas awal dan akhir).

---

### **2. Sintaks SQL BETWEEN**

```sql
SELECT column1, column2, ...
FROM table
WHERE column BETWEEN value1 AND value2;
```

- **column1, column2, ...**: Kolom yang ingin ditampilkan.
- **table**: Nama tabel tempat data disimpan.
- **column**: Kolom tempat kita ingin menerapkan rentang nilai.
- **BETWEEN**: Operator untuk menentukan rentang.
- **value1** dan **value2**: Batas bawah dan atas dari rentang.

---

### **3. Contoh SQL BETWEEN**

#### **a. Rentang Angka**

```sql
SELECT *
FROM Orders
WHERE amount BETWEEN 200 AND 600;
```
- **Penjelasan:**
    - Pilih semua kolom (`*`) dari tabel `Orders` di mana nilai kolom `amount` berada antara **200** hingga **600**.
    - Termasuk nilai **200** dan **600**.

#### **b. Rentang Teks**

```sql
SELECT item, amount
FROM Orders
WHERE item BETWEEN 'I' AND 'L';
```

- **Penjelasan:**
    - Pilih kolom `item` dan `amount` dari tabel `Orders` di mana nama item dimulai dengan huruf antara **I** hingga **L**.
    - Termasuk huruf **I** dan **L**.

#### **c. Rentang Tanggal**

```sql
SELECT *
FROM Teams
WHERE registered BETWEEN '2021-01-01' AND '2022-11-01';
```

- **Penjelasan:**
    - Pilih semua kolom (`*`) dari tabel `Teams` di mana tanggal pada kolom `registered` berada antara **1 Januari 2021** hingga **1 November 2022**.
    - Termasuk kedua tanggal tersebut.

---

### **4. NOT BETWEEN Operator**

**NOT BETWEEN** digunakan untuk memilih data yang **tidak berada dalam rentang** nilai tertentu.

#### **Contoh:**

```sql
SELECT item, amount
FROM Orders
WHERE amount NOT BETWEEN 300 AND 500;
```

- **Penjelasan:**
    - Pilih semua item dari tabel `Orders` di mana kolom `amount` **tidak berada** antara **300** hingga **500**.
    - Nilai **300** dan **500** juga dikeluarkan.

---

### **5. Menggunakan BETWEEN dengan Teks**

BETWEEN juga bisa digunakan untuk teks, misalnya untuk memilih data berdasarkan huruf awal.

#### **Contoh:**

```sql
SELECT item, amount
FROM Orders
WHERE item BETWEEN 'A' AND 'C';
```

- **Penjelasan:**
    - Pilih item yang namanya dimulai dengan huruf **A**, **B**, atau **C**.

Jika ingin mencakup semua kata yang diawali dengan **L**, gunakan karakter tambahan seperti `~`:

```sql
SELECT item, amount
FROM Orders
WHERE item BETWEEN 'I' AND 'L~';
```

---

### **6. Keuntungan BETWEEN**

1. **Mudah Dibaca:** Lebih singkat dibandingkan menulis beberapa kondisi menggunakan **AND**.

Contoh Tanpa BETWEEN:

```sql
SELECT *
FROM Orders
WHERE amount >= 200 AND amount <= 600;

```

Sama dengan :

```sql
SELECT *
FROM Orders
WHERE amount BETWEEN 200 AND 600;
```

2. **Fleksibel:** Bisa digunakan untuk angka, teks, atau tanggal.

3. **Termasuk Batas:** Secara otomatis memasukkan batas atas dan bawah dalam hasil.