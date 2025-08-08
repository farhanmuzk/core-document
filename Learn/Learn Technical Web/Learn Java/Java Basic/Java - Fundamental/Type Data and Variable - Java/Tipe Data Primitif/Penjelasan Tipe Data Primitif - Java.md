---
tags:
  - Java
  - TipeData
---
![[Pasted image 20250111015126.png]]

---
# Tipe Data Primitif

Tipe data primitif adalah **tipe data dasar** yang sudah ada di dalam Java. Tipe ini digunakan untuk menyimpan nilai sederhana seperti angka, karakter, atau nilai logika .

## Karakteristik Tipe Data Primitif

- **Bukan objek**, sehingga hemat memori.
- Tidak memiliki metode bawaan (seperti operasi string).
- Nilainya langsung disimpan di memori.

## Jenis Tipe Data Primitif

Jenis tipe data nya sudah di jelasakan pada halaman : [[Tipe Data Integer - Java]] , [[Tipe Data Boolean - Java]], [[Tipe Data Character - Java]]

|**Tipe Data**|**Ukuran**|**Nilai Default**|**Contoh Nilai**|
|---|---|---|---|
|`byte`|1 byte (8 bit)|`0`|`-128` hingga `127`|
|`short`|2 byte (16 bit)|`0`|`-32,768` hingga `32,767`|
|`int`|4 byte (32 bit)|`0`|`-2,147,483,648` hingga `2,147,483,647`|
|`long`|8 byte (64 bit)|`0L`|`-9,223,372,036,854,775,808` hingga `9,223,372,036,854,775,807`|
|`float`|4 byte (32 bit)|`0.0f`|`3.4e-038` hingga `3.4e+038`|
|`double`|8 byte (64 bit)|`0.0d`|`1.7e-308` hingga `1.7e+308`|
|`char`|2 byte (16 bit)|`'\u0000'`|Karakter Unicode (misal: `'A'`, `'1'`)|
|`boolean`|1 bit (teoritis)|`false`|`true` atau `false`|
## Contoh Penggunaan Tipe Data Primitif

```java
public class PrimitiveExample {
    public static void main(String[] args) {
        int number = 25;          // Tipe data int
        char letter = 'A';        // Tipe data char
        boolean isJavaFun = true; // Tipe data boolean
        double price = 99.99;     // Tipe data double

        System.out.println("Number: " + number);
        System.out.println("Letter: " + letter);
        System.out.println("Is Java fun? " + isJavaFun);
        System.out.println("Price: " + price);
    }
}
```

---

# Data Primitif Di Jadikan Tidak Primitif

Java menyediakan **wrapper class** untuk setiap tipe data primitif. Wrapper class adalah kelas bawaan Java yang memungkinkan tipe data primitif digunakan sebagai **objek**.

| **Tipe Primitif** | **Wrapper Class** |
| ----------------- | ----------------- |
| `int`             | `Integer`         |
| `long`            | `Long`            |
| `double`          | `Double`          |
| `float`           | `Float`           |
| `char`            | `Character`       |
| `boolean`         | `Boolean`         |
| `byte`            | `Byte`            |
| `short`           | `Short`           |
## Autoboxing dan Unboxing

### 1. Autoboxing

**Autoboxing** adalah proses otomatis di mana tipe data primitif diubah menjadi objek wrapper class. Ini dilakukan oleh Java secara otomatis saat diperlukan.

```java
public class AutoboxingExample {
    public static void main(String[] args) {
        int num = 5;            // Tipe primitif
        Integer obj = num;      // Autoboxing ke Integer (wrapper class)

        System.out.println("Primitive: " + num);
        System.out.println("Wrapper Object: " + obj);
    }
}
```

---

### 2. Unboxing

**Unboxing** adalah kebalikan dari autoboxing, yaitu proses otomatis mengubah objek wrapper class kembali menjadi tipe data primitif.

```java
public class UnboxingExample {
    public static void main(String[] args) {
        Integer obj = 10;       // Wrapper class
        int num = obj;          // Unboxing ke tipe primitif

        System.out.println("Wrapper Object: " + obj);
        System.out.println("Primitive: " + num);
    }
}
```

## Perbedaan Tipe Primitif dan Wrapper Class

| **Aspek**     | **Tipe Primitif**        | **Wrapper Class**                 |
| ------------- | ------------------------ | --------------------------------- |
| Sifat         | Nilai langsung           | Referensi ke objek                |
| Ukuran Memori | Lebih kecil dan efisien  | Lebih besar (karena objek)        |
| Operasi       | Tidak memiliki metode    | Memiliki metode tambahan          |
| Contoh :      | `int`, `char`, `boolean` | `Integer`, `Character`, `Boolean`