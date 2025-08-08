---
tags:
  - Java
  - TipeData
Updated: 2025-01-10
---
**Variabel** adalah tempat untuk menyimpan data sementara di dalam program. Variabel memiliki nama, tipe data, dan nilai. Di Java, variabel harus dideklarasikan sebelum digunakan.

## Jenis Variabel di Java

Ada **tiga jenis variabel utama** di Java berdasarkan lokasi deklarasi dan cakupan penggunaannya:

1. **Lokal**

-  Dideklarasikan di dalam metode/blok.
-  Hanya dapat digunakan di dalam blok tersebut.
-  **Tidak ada nilai default**, harus diinisialisasi sebelum digunakan.

```java
void show() {
    int x = 10; // Variabel lokal
    System.out.println(x);
}
```

2. **Instance**

-  Dideklarasikan di dalam kelas (di luar metode).
-  Terkait dengan objek tertentu.
- Memiliki **nilai default** (contoh: 0 untuk angka, null untuk objek).

```java
class Person {
    String name; // Variabel instance
}
```

3. **Static**

- Dideklarasikan dengan kata kunci `static`.
- Dimiliki bersama oleh semua objek (bersifat global).
- Memiliki **nilai default**.

```java
class Calculator {
    static int counter = 0; // Variabel static
}
```

## Aturan Penamaan Variabel

- Harus dimulai dengan huruf, underscore (`_`), atau dolar (`$`).
- Tidak boleh menggunakan angka sebagai karakter pertama.
- Hindari menggunakan kata kunci Java (seperti `int`, `class`).

>[!Danger]
Contoh Nama Valid: `name`, `_count`, `totalAmount`  
Contoh Nama Tidak Valid: `2name`, `class

## Contoh Program Lengkap

```java
public class Main {
    static String staticVar = "Ini variabel static"; // Static
    String instanceVar = "Ini variabel instance";   // Instance

    public void display() {
        String localVar = "Ini variabel lokal";     // Lokal
        System.out.println(localVar);
        System.out.println(instanceVar);
        System.out.println(staticVar);
    }

    public static void main(String[] args) {
        Main obj = new Main();
        obj.display();
    }
}
```