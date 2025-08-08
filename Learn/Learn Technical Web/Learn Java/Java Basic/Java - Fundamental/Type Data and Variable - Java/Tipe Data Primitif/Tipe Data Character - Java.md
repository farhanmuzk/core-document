---
tags:
  - Java
  - TipeData
Updated: 2025-01-10
---
Tipe data **`char`** di Java digunakan untuk menyimpan **karakter tunggal**. Karakter ini dapat berupa huruf, angka, simbol, atau karakter Unicode lainnya. Dalam Java, tipe data `char` direpresentasikan sebagai **16-bit unsigned integer**, yang berarti dapat menyimpan karakter dengan kode Unicode dari **`\u0000`** hingga **`\uffff`**.

## Karakteristik `char`

1. **Ukuran Memori**: 16 bit (2 byte).
2. **Rentang Nilai**: `\u0000` (0 desimal) hingga `\uffff` (65,535 desimal).
3. **Menyimpan Karakter Tunggal**: Termasuk huruf, angka, simbol, atau karakter Unicode.
4. **Representasi**: Ditulis di antara tanda kutip tunggal `' '`. Contoh: `'A'`, `'9'`, `'#'`.
## Deklarasi dan Inisialisasi

```java
public class Main {
    public static void main(String[] args) {
        char letter = 'A';         // Huruf
        char digit = '5';          // Angka sebagai karakter
        char symbol = '#';         // Simbol
        char unicodeChar = '\u0041'; // Unicode untuk 'A'

        System.out.println("Huruf: " + letter);
        System.out.println("Angka: " + digit);
        System.out.println("Simbol: " + symbol);
        System.out.println("Unicode: " + unicodeChar);
    }
}
```

## Kesimpulan

1. Tipe data `char` digunakan untuk menyimpan karakter tunggal, termasuk huruf, angka, simbol, dan karakter Unicode.
2. `char` memiliki ukuran 16-bit dan mendukung representasi Unicode.
3. Operasi aritmatika dan konversi dapat dilakukan dengan `char`, tetapi harus dilakukan dengan hati-hati.
4. Gunakan tipe data ini untuk karakter tunggal, dan gunakan string (`String`) untuk menyimpan teks lebih panjang.