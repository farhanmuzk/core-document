---
tags:
  - Java
  - Operators
Updated: 2025-01-13
---
Operator Java simbol untuk melkukan operasi pada variabel dan nilai, contoh simbol `+` di gunakan pada operasi penjumlahan.

Di dalam Java Operator di bagi menjadi 6 seperti :

1. Arithmetic Operators
2. Assignment Operators
3. Relational Operators
4. Logical Operators
5. Unary Operators
6. Bitwise Operators

---

# Operator Aritmatika

Operator Aritmetic adalah operator untuk melakukan matematika dasar. contoh operator artimatika dalam pemograman :

|          |                                         |
| -------- | --------------------------------------- |
| Operator | Operasi                                 |
| `+`      | Tambahan                                |
| `-`      | Pengurangan                             |
| `*`      | Perkalian                               |
| `/`      | Divisi                                  |
| `%`      | Operasi Modulo (Sisa setelah pembagian) |
|          |                                         |
## Contoh : Operator Artimatika

```java
class Main {
  public static void main(String[] args) {
    
    // declare variables
    int a = 12, b = 5;

    // addition operator
    System.out.println("a + b = " + (a + b));

    // subtraction operator
    System.out.println("a - b = " + (a - b));

    // multiplication operator
    System.out.println("a * b = " + (a * b));

    // division operator
    System.out.println("a / b = " + (a / b));

    // modulo operator
    System.out.println("a % b = " + (a % b));
  }
}
```

```java
a + b = 17
a - b = 7 
a * b = 60
a / b = 2 
a % b = 2
```
# Operator Penugasan

Operator penugasan digunakan untuk memberikan nilai pada variabel. Operator penugasan yang umum digunakan adalah:

|Operator|Contoh|Setara dengan|
|---|---|---|
|`=`|`a = b;`|`a = b;`|
|`+=`|`a += b;`|`a = a + b;`|
|`-=`|`a -= b;`|`a = a - b;`|
|`*=`|`a *= b;`|`a = a * b;`|
|`/=`|`a /= b;`|`a = a / b;`|
|`%=`|`a %= b;`|`a = a % b;`|

### Contoh : Operator Penugasan

```java
class Main {
  public static void main(String[] args) {
    
    // create variables
    int a = 4;
    int var;

    // assign value using =
    var = a;
    System.out.println("var using =: " + var);

    // assign value using =+
    var += a;
    System.out.println("var using +=: " + var);

    // assign value using =*
    var *= a;
    System.out.println("var using *=: " + var);
  }
}
```


```
var menggunakan =: 4 
var menggunakan +=: 8 
var menggunakan *=: 32
```

# Operator Relasional

Operator relasional digunakan untuk membandingkan dua nilai atau variabel. Hasil dari operator ini adalah `True` atau `False`. Operator relasional yang umum adalah:

|Operator|Keterangan|Contoh|
|---|---|---|
|`==`|Sama Dengan|`3 == 5`mengembalikan **false**|
|`!=`|Tidak sama dengan|`3 != 5`mengembalikan **true**|
|`>`|Lebih Besar Dari|`3 > 5`mengembalikan **false**|
|`<`|Kurang Dari|`3 < 5`mengembalikan **true**|
|`>=`|Lebih besar dari atau sama dengan|`3 >= 5`mengembalikan **false**|
|`<=`|Kurang Dari atau Sama Dengan|`3 <= 5`mengembalikan **true**|

	### Contoh : Operator Relasional

```java
class Main {
  public static void main(String[] args) {
    
    // create variables
    int a = 7, b = 11;

    // value of a and b
    System.out.println("a is " + a + " and b is " + b);

    // == operator
    System.out.println(a == b);  // false

    // != operator
    System.out.println(a != b);  // true

    // > operator
    System.out.println(a > b);  // false

    // < operator
    System.out.println(a < b);  // true

    // >= operator
    System.out.println(a >= b);  // false

    // <= operator
    System.out.println(a <= b);  // true
  }
}
```

>[!TIP]
>**Catatan** : Operator relasional digunakan dalam pengambilan keputusan dan perulangan.

---

# 4. Operator Logika Java

Operator logika digunakan untuk memeriksa apakah suatu ekspresi adalah `true`atau `false`. Operator ini digunakan dalam pengambilan keputusan.

|Operator|Contoh|Arti|
|---|---|---|
|`&&`(Logika DAN)|ekspresi1 **&&** ekspresi2|`true`hanya jika keduanyaekspresi1Danekspresi2adalah`true`|
|`\|`(Logika ATAU)|ekspresi1 **\|** ekspresi2|`true`jika salah satuekspresi1atauekspresi2adalah`true`|
|`!`(Logika TIDAK)|**!** ekspresi|`true`jikaekspresiadalah `false`dan sebaliknya|

### Contoh 4: Operator Logika

```
class Main {
  public static void main(String[] args) {

    // && operator
    System.out.println((5 > 3) && (8 > 5));  // true
    System.out.println((5 > 3) && (8 < 5));  // false

    // || operator
    System.out.println((5 < 3) || (8 > 5));  // true
    System.out.println((5 > 3) || (8 < 5));  // true
    System.out.println((5 < 3) || (8 < 5));  // false

    // ! operator
    System.out.println(!(5 == 3));  // true
    System.out.println(!(5 > 3));  // false
  }
}
```

**Cara Kerja Program**

- `(5 > 3) && (8 > 5)`kembali `true`karena keduanya `(5 > 3)`dan .`(8 > 5)``true`
- `(5 > 3) && (8 < 5)`kembali `false`karena ekspresinya `(8 < 5)`adalah `false`.
- `(5 < 3) || (8 > 5)`kembali `true`karena ekspresinya `(8 > 5)`adalah `true`.
- `(5 > 3) || (8 < 5)`kembali `true`karena ekspresinya `(5 > 3)`adalah `true`.
- `(5 < 3) || (8 < 5)`kembali `false`karena keduanya `(5 < 3)`dan .`(8 < 5)``false`
- `!(5 == 3)`mengembalikan true karena `5 == 3`adalah `false`.
- `!(5 > 3)`mengembalikan false karena `5 > 3`adalah `true`.

# 5. Operator Unary pada Java

Operator unary digunakan hanya dengan satu operan. Misalnya, `++`adalah operator unary yang menaikkan nilai variabel sebesar **1.** Artinya, `++5`akan menghasilkan **6** .

Berbagai jenis operator unary adalah:

|Operator|Arti|
|---|---|
|`+`|**Unary plus** : tidak perlu digunakan karena angkanya positif tanpa menggunakannya|
|`-`|**Unary minus** : membalikkan tanda suatu ekspresi|
|`++`|**Operator kenaikan** : menambah nilai sebesar 1|
|`--`|**Operator penurunan** : mengurangi nilai sebesar 1|
|`!`|**Operator pelengkap logika** : membalikkan nilai boolean|

## Operator Increment dan Decrement

Java juga menyediakan operator increment dan decrement: `++`dan `--`masing-masing `++`meningkatkan nilai operan sebesar **1** , sementara `--`menguranginya sebesar **1.** Misalnya,

```
int num = 5;

// increase num by 1
++num;
```

Di sini, nilai darinomormeningkat menjadi **6** dari nilai awalnya **5** .

# 6. Operator Bitwise Java

Operator bitwise di Java digunakan untuk melakukan operasi pada bit individual. Misalnya,

```
Bitwise complement Operation of 35

35 = 00100011 (In Binary)

~ 00100011 
  ________
   11011100  = 220 (In decimal)
```

Di sini, `~`adalah operator bitwise. Operator ini membalikkan nilai setiap bit ( **0** ke **1** dan **1** ke **0** ).

Berbagai operator bitwise yang ada di Java adalah:

|Operator|Keterangan|
|---|---|
|`~`|Pelengkap Bitwise|
|`<<`|Shift Kiri|
|`>>`|Shift Kanan|
|`>>>`|Shift Kanan Tanpa Tanda|
|`&`|Bitwise DAN|
|`^`|Eksklusif Bitwise ATAU|

Operator-operator ini umumnya tidak digunakan di Java. Untuk mempelajari lebih lanjut, kunjungi [Operator Bitwise dan Bit Shift di Java](https://www.programiz.com/java-programming/bitwise-operators) .

---

## Operator lainnya

Selain operator-operator tersebut, masih ada operator-operator tambahan lainnya di Java.

### Operator Java instanceof

Operator `instanceof`memeriksa apakah suatu objek merupakan instance dari kelas tertentu. Misalnya,

```
class Main {
  public static void main(String[] args) {

    String str = "Programiz";
    boolean result;

    // checks if str is an instance of
    // the String class
    result = str instanceof String;
    System.out.println("Is str an object of String? " + result);
  }
}
```

[Jalankan Kode](https://www.programiz.com/java-programming/online-compiler)

**Keluaran**

Apakah str merupakan objek dari String? benar

Di Sini,kuatadalah contoh dari `String`kelas. Oleh karena itu, `instanceof`operator mengembalikan `true`. Untuk mempelajari lebih lanjut, kunjungi [Java instanceof](https://www.programiz.com/java-programming/instanceof) .

---

### Operator Terner Java

Operator ternary (operator kondisional) adalah singkatan dari `if-then-else`pernyataan. Misalnya,

variabel = Ekspresi ? ekspresi1 : ekspresi2

Begini cara kerjanya.

- Jika `Expression`adalah `true`, `expression1`ditugaskan kevariabel.
- Jika `Expression`adalah `false`, `expression2`ditugaskan kevariabel.

Mari kita lihat contoh operator terner.

```
class Java {
  public static void main(String[] args) {

    int februaryDays = 29;
    String result;

    // ternary operator
    result = (februaryDays == 28) ? "Not a leap year" : "Leap year";
    System.out.println(result);
  }
}
```

[Jalankan Kode](https://www.programiz.com/java-programming/online-compiler)

**Keluaran**

Tahun kabisat

Dalam contoh di atas, kami telah menggunakan operator ternary untuk memeriksa apakah tahun tersebut merupakan tahun kabisat atau bukan. Untuk mempelajari lebih lanjut, kunjungi [operator ternary Java](https://www.programiz.com/java-programming/ternary-operator) .