---
tags:
  - "#Java"
  - "#TipeData"
Updated: 2025-01-10
---
**Integer Numbers** di Java mengacu pada bilangan bulat tanpa desimal. Java menyediakan berbagai tipe data untuk menyimpan bilangan bulat dengan berbagai rentang nilai dan ukuran.
## Perbedaan Tipe Data Number

Java memiliki empat tipe data utama untuk bilangan bulat:

|Tipe Data|Ukuran (bits)|Rentang Nilai|Contoh Penggunaan|
|---|---|---|---|
|`byte`|8|-128 hingga 127|Penghematan memori|
|`short`|16|-32,768 hingga 32,767|Operasi spesifik|
|`int`|32|-2,147,483,648 hingga 2,147,483,647|Default untuk bilangan bulat|
|`long`|64|-9,223,372,036,854,775,808 hingga 9,223,372,036,854,775,807|Angka sangat besar|

## Deklarasi dan Inisialisasi

Menunjukan batasan nilai semua tipe dan cara deklarasi di code.

```java
public class Main {
    public static void main(String[] args) {
        byte myByte = 100;
        short myShort = 30000;
        int myInt = 100_000_0; //Penggunaan '_' untuk mudah di baca
        long myLong = 10000000000L; // Tambahkan 'L' untuk tipe long
    }
}
```

## Operasi Dasar

Integer numbers dapat digunakan dalam berbagai operasi matematika:

```java
public class Main {
    public static void main(String[] args) {
        int a = 10, b = 5;

        int sum = a + b;       // Penjumlahan
        int difference = a - b; // Pengurangan
        int product = a * b;    // Perkalian
        int quotient = a / b;   // Pembagian
        int remainder = a % b;  // Sisa bagi

        System.out.println("Sum: " + sum);
        System.out.println("Difference: " + difference);
        System.out.println("Product: " + product);
        System.out.println("Quotient: " + quotient);
        System.out.println("Remainder: " + remainder);
    }
}
```


## Konversi Tipe Data Number 

Java memungkinkan konversi antara tipe data integer dengan aturan :
- **widening** (konversi ke tipe yang lebih besar) 
- **narrowing** (konversi ke tipe yang lebih kecil).

### 1. Widening Conversion

Tidak memerlukan casting eksplisit:

```java
int myInt = 100;
long myLong = myInt; // Widening
System.out.println("Long: " + myLong);
```

### 2. Narrowing Conversion

Memerlukan casting eksplisit:

```java
long myLong = 1000L;
int myInt = (int) myLong; // Narrowing
System.out.println("Int: " + myInt);
```

**Catatan:** Narrowing bisa menyebabkan **data loss** jika nilai tidak muat dalam rentang tipe data tujuan.

## Kesimpulan 

>[!TIP]
>Kesimpulan
>1. Java menyediakan empat tipe data untuk integer: `byte`, `short`, `int`, dan `long`.
>2. Pilih tipe data berdasarkan kebutuhan memori dan rentang nilai.
>3. Pahami cara melakukan konversi antara tipe data dan potensi risiko terkait.
>4. Gunakan tipe data integer dengan efisien untuk meningkatkan performa aplikasi.

## Contoh Program Lengkap

```java
public class Main {
    public static void main(String[] args) {
        // Deklarasi dan Inisialisasi
        byte myByte = 127;
        short myShort = 30000;
        int myInt = 1000000;
        long myLong = 9223372036854775807L;

        // Operasi
        int a = 15, b = 4;
        System.out.println("Sum: " + (a + b));
        System.out.println("Difference: " + (a - b));
        System.out.println("Product: " + (a * b));
        System.out.println("Quotient: " + (a / b));
        System.out.println("Remainder: " + (a % b));

        // Konversi
        long bigNumber = myInt; // Widening
        int smallNumber = (int) myLong; // Narrowing dengan kemungkinan data loss

        System.out.println("Widening Conversion: " + bigNumber);
        System.out.println("Narrowing Conversion: " + smallNumber);
    }
}
```

## Praktik Terbaik

1. **Gunakan `int` untuk kebanyakan kasus:** Tipe `int` cukup untuk menangani sebagian besar kebutuhan operasi integer.
2. **Gunakan `long` untuk angka besar:** Jika nilai melebihi rentang `int`, gunakan `long`. 
3. **Hindari Narrowing jika memungkinkan:** Narrowing bisa menyebabkan data hilang atau hasil yang tidak diharapkan.  
4. **Gunakan Konstanta `MIN_VALUE` dan `MAX_VALUE`:** Untuk mengetahui batas dari tipe data:

```java
System.out.println("Int Min: " + Integer.MIN_VALUE);
System.out.println("Int Max: " + Integer.MAX_VALUE);
```