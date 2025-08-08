---
tags:
  - Java
  - TipeData
Updated: 2025-01-10
---
Tipe data **`String`** di Java digunakan untuk menyimpan **sekumpulan karakter** (teks). `String` bukan tipe data primitif, tetapi merupakan **kelas bawaan Java** yang sering digunakan untuk manipulasi teks.

---
## Karakteristik Tipe Data `String`

1. **Bukan Tipe Data Primitif**: `String` adalah objek dari kelas **`java.lang.String`**.
2. **Immutable**: Objek `String` tidak dapat diubah setelah dibuat. Operasi yang mengubah `String` sebenarnya membuat objek baru.
3. **Representasi Literal**: Ditulis di dalam tanda kutip ganda (`" "`). Contoh: `"Hello, World!"`.
4. **Mendukung Unicode**: `String` dapat menyimpan teks dalam berbagai bahasa dan simbol.

---

## Deklarasi dan Inisialisasi

```java
public class Main {
    public static void main(String[] args) {
        // Deklarasi dan inisialisasi
        String greeting = "Hello, World!";
        String emptyString = ""; // String kosong

        System.out.println("Greeting: " + greeting);
        System.out.println("Empty String: " + emptyString);
    }
}
```


## Operasi Dasar dengan String

|         |                                         |                                                                                        |
| ------- | --------------------------------------- | -------------------------------------------------------------------------------------- |
| **No.** | **Nama**                                | **Deskripsi**                                                                          |
| 1       | **length()**                            | Digunakan untuk mengetahui panjang atau jumlah karakter dalam string.                  |
| 2       | **charAt(int index)**                   | Digunakan untuk mengambil sebuah karakter berdasarkan indeks tertentu.                 |
| 3       | **format(String format, Object… args)** | Digunakan untuk memformat sebuah string.                                               |
| 4       | **substring(int beginIndex)**           | Mengembalikan/menghasilkan substring berdasarkan indeks yang diberikan.                |
| 5       | **contains(CharSequence s)**            | Mengembalikan/menghasilkan nilai **true** atau **false** setelah mencocokkan karakter. |
| 6       | **equals(Object object)**               | Memeriksa apakah nilai objek sama dengan nilai string.                                 |
| 7       | **isEmpty()**                           | Memeriksa apakah sebuah string itu kosong atau tidak.                                  |
| 8       | **concat(String s)**                    | Mengkonsolidasikan sebuah string.                                                      |
| 9       | **replace(char a, char b)**             | Mengganti suatu karakter di dalam string.                                              |
| 10      | **indexOf(String a)**                   | Mengetahui indeks dari sebuah substring.                                               |
| 11      | **toLowerCase()**                       | Mengubah format string menjadi huruf kecil semua.                                      |
| 12      | **toUpperCase()**                       | Mengubah format string menjadi huruf kapital semua.                                    |
| 13      | **trim()**                              | Menghapus spasi awal dan akhir dari string.                                            |
| 14      | **valueOf(int value)**                  | Mengkonversi tipe yang diberikan menjadi sebuah string.                                |
| 15      | **compareTo()**                         | Membandingkan dua nilai                                                                |
## Kesimpulan

>[!TIP]
>Tipe data `String` digunakan untuk menyimpan teks.
>- `String` adalah immutable, sehingga setiap perubahan menghasilkan objek baru
>- Java menyediakan berbagai metode bawaan untuk manipulasi teks, seperti penggabungan, pemotongan, penggantian, dan pemeriksaan.
>- Hindari kebingungan antara `""` (string kosong) dan `null` (tidak ada referensi).
>
