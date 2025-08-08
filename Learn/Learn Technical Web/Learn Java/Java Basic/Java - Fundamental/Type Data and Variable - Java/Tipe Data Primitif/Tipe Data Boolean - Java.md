---
tags:
  - Java
  - TipeData
Updated: 2025-01-10
---
boolean adalah tipe data di Java yang hanya dapat menyimpan dua nilai: **`true`** atau **`false`**. Tipe data ini sering digunakan untuk **kontrol alur program**, seperti kondisi pada pernyataan `if-else`, loop, atau operasi logika.

## Karakteristik Tipe Data `boolean`

Operasi logika digunakan untuk mengombinasikan atau membandingkan nilai boolean. Operasi ini menghasilkan nilai `true` atau `false`.

|Operator|Kegunaan|Contoh|Hasil|
|---|---|---|---|
|`&&`|AND (dan)|`true && false`|`false`|
|`||`|OR (atau)|
|`!`|NOT (negasi)|`!true`|`false`|
## Operasi Pembanding 

Operasi pembanding menghasilkan nilai `boolean`. Operasi ini digunakan untuk membandingkan dua nilai.

| Operator | Kegunaan                     | Contoh   | Hasil   |
| -------- | ---------------------------- | -------- | ------- |
| `==`     | Sama dengan                  | `5 == 5` | `true`  |
| `!=`     | Tidak sama dengan            | `5 != 3` | `true`  |
| `>`      | Lebih besar                  | `10 > 5` | `true`  |
| `<`      | Lebih kecil                  | `5 < 3`  | `false` |
| `>=`     | Lebih besar atau sama dengan | `5 >= 5` | `true`  |
| `<=`     | Lebih kecil atau sama dengan | `3 <= 5` | `true`  |
```java
public class Main {
    public static void main(String[] args) {
        int x = 10, y = 20;

        System.out.println("x == y: " + (x == y));
        System.out.println("x != y: " + (x != y));
        System.out.println("x > y: " + (x > y));
        System.out.println("x < y: " + (x < y));
    }
}
```
## Deklarasi dan Inisialisasi

Tipe data `boolean` dideklarasikan seperti tipe data lainnya, dengan kata kunci **`boolean`**.

```java
public class Main {
    public static void main(String[] args) {
        boolean isJavaFun = true;
        boolean isRainyDay = false;

        System.out.println("Is Java Fun? " + isJavaFun);
        System.out.println("Is it a Rainy Day? " + isRainyDay);
    }
}
```

## Kesimpulan

>[!TIP]
>- Tipe data `boolean` di Java digunakan untuk menyimpan nilai **`true`** atau **`false`**.
>- Berguna untuk operasi logika, pembanding, dan kontrol alur program.
>- Membantu membuat kode lebih sederhana dan mudah dipahami.
>- Pahami cara menggunakan operator logika dan pembanding untuk memanfaatkan tipe data ini secara maksimal.

## Contoh Program Lengkap

```java
public class Main {
    public static void main(String[] args) {
        int age = 20;
        boolean hasID = true;

        // Memeriksa apakah seseorang boleh masuk
        if (age >= 18 && hasID) {
            System.out.println("You are allowed to enter.");
        } else {
            System.out.println("Access denied.");
        }

        // Contoh penggunaan boolean
        boolean isEven = (age % 2 == 0); // Mengecek apakah angka genap
        System.out.println("Is age even? " + isEven);
    }
}
```

## Praktik Terbaik 

- **Gunakan tipe `boolean` untuk kondisi:**
    
    - Lebih sederhana dan efisien dibanding menggunakan angka seperti `0` atau `1` untuk merepresentasikan `false` atau `true`.
- **Kombinasikan Operasi dengan Bijak:**
    
    - Gunakan operator logika (`&&`, `||`, `!`) hanya jika diperlukan agar kode tetap mudah dibaca.
- **Hindari Penggunaan Nilai `boolean` Secara Tidak Jelas:**
    
    - Jangan mengganti `true`/`false` dengan nilai lain (seperti angka) untuk menghindari kebingungan.