# Input dan Output Dasar Java

## Keluaran Java

Di Java, Anda cukup menggunakan

```java
System.out.println(); or

System.out.print(); or

System.out.printf();
```

untuk mengirim keluaran ke keluaran standar (layar).

Di Sini,

- `System`adalah sebuah kelas
- `out`adalah suatu `public` `static`bidang: ia menerima data keluaran.

Jangan khawatir jika Anda tidak memahaminya. Kita akan membahas `class`, `public`, dan `static`di bab-bab berikutnya.

Mari kita ambil contoh untuk mengeluarkan baris.

```java
class AssignmentOperator {
    public static void main(String[] args) {
    	
        System.out.println("Java programming is interesting.");   
    }
}
```

**Keluaran** :

Pemrograman Java menarik.

Di sini, kami menggunakan `println()`metode untuk menampilkan string.

---

### Perbedaan antara println(), print() dan printf()

- `print()`- Mencetak string di dalam tanda kutip.
- `println()`- Mencetak string di dalam tanda kutip mirip seperti `print()`metode. Kemudian kursor bergerak ke awal baris berikutnya.
- `printf()`- Menyediakan pemformatan string (mirip dengan [printf dalam pemrograman C/C++](https://www.programiz.com/cpp-programming/library-function/cstdio/printf) ).

---

### Contoh: print() dan println()

```
class Output {
    public static void main(String[] args) {
    	
        System.out.println("1. println ");
        System.out.println("2. println ");
    	
        System.out.print("1. print ");
        System.out.print("2. print");
    }
}
```

[Jalankan Kode](https://www.programiz.com/java-programming/online-compiler)

**Keluaran** :

1. cetak
2. cetak
1. cetak 2. cetak

Dalam contoh di atas, kami telah menunjukkan cara kerja metode `print()`dan `println()`. Untuk mempelajari `printf()`metode ini, kunjungi [Java printf()](https://www.cs.colostate.edu/~cs160/.Summer16/resources/Java_printf_method_quick_reference.pdf) .

---

### Contoh: Mencetak Variabel dan Literal

```
class Variables {
    public static void main(String[] args) {
    	
        Double number = -10.6;
    	
        System.out.println(5);
        System.out.println(number);
    }
}
```

[Jalankan Kode](https://www.programiz.com/java-programming/online-compiler)

Ketika Anda menjalankan program tersebut, outputnya akan menjadi:

5
-10.6

Di sini, Anda dapat melihat bahwa kami tidak menggunakan tanda kutip. Hal ini karena untuk menampilkan bilangan bulat, [variabel,](https://www.programiz.com/java-programming/variables-literals) dan sebagainya, kami tidak menggunakan tanda kutip.

---

### Contoh: Cetak String yang Digabungkan

```
class PrintVariables {
    public static void main(String[] args) {
    	
        Double number = -10.6;
    	
        System.out.println("I am " + "awesome.");
        System.out.println("Number = " + number);
    }
}
```

[Jalankan Kode](https://www.programiz.com/java-programming/online-compiler)

**Keluaran** :

Aku mengagumkan.
Angka = -10,6

Pada contoh di atas, perhatikan baris,

```
System.out.println("I am " + "awesome.");
```

Di sini, kita menggunakan `+`operator untuk menggabungkan (menggabungkan) dua string:"Saya "Dan"luar biasa.".

Dan juga, garisnya,

```
System.out.println("Number = " + number);
```

Di sini, pertama nilai variabelnomordievaluasi. Kemudian, nilainya dirangkai ke string:"Nomor = ".

---

## Masukan Java

Java menyediakan berbagai cara untuk mendapatkan input dari pengguna. Namun, dalam tutorial ini, Anda akan belajar cara mendapatkan input dari pengguna menggunakan objek `Scanner`kelas.

Untuk menggunakan objek `Scanner`, kita perlu mengimpor `java.util.Scanner`paket.

```
import java.util.Scanner;
```

Untuk mempelajari lebih lanjut tentang mengimpor paket di Java, kunjungi [Java Import Packages](https://www.programiz.com/java-programming/packages-import) .

Kemudian, kita perlu membuat objek dari `Scanner`kelas tersebut. Kita dapat menggunakan objek tersebut untuk mengambil input dari pengguna.

```
// create an object of Scanner
Scanner input = new Scanner(System.in);

// take input from the user
int number = input.nextInt();
```

---

### Contoh: Mendapatkan Input Integer Dari Pengguna

```java
import java.util.Scanner;

class Input {
    public static void main(String[] args) {
    	
        Scanner input = new Scanner(System.in);
    	
        System.out.print("Enter an integer: ");
        int number = input.nextInt();
        System.out.println("You entered " + number);

        // closing the scanner object
        input.close();
    }
}
```

**Keluaran** :

Masukkan bilangan bulat: 23
Anda memasukkan 23

Dalam contoh di atas, kita telah membuat sebuah objek bernamamasukandari `Scanner`kelas. Kemudian kita memanggil `nextInt()`metode kelas `Scanner`untuk mendapatkan input integer dari pengguna.

Dengan cara yang sama, kita dapat menggunakan metode `nextLong()`, `nextFloat()`, `nextDouble()`, dan `next()`untuk mendapatkan `long`, `float`, `double`, dan `string`input masing-masing dari pengguna.

**Catatan** : Kami telah menggunakan `close()`metode untuk menutup objek. Sebaiknya objek pemindai ditutup setelah input diambil.

---

### Contoh: Dapatkan input float, double dan String

```
import java.util.Scanner;

class Input {
    public static void main(String[] args) {
    	
        Scanner input = new Scanner(System.in);
    	
        // Getting float input
        System.out.print("Enter float: ");
        float myFloat = input.nextFloat();
        System.out.println("Float entered = " + myFloat);
    	
        // Getting double input
        System.out.print("Enter double: ");
        double myDouble = input.nextDouble();
        System.out.println("Double entered = " + myDouble);
    	
        // Getting String input
        System.out.print("Enter text: ");
        String myString = input.next();
        System.out.println("Text entered = " + myString);
    }
}
```

[Jalankan Kode](https://www.programiz.com/java-programming/online-compiler)

**Keluaran** :

Masukkan float: 2.343
Float yang dimasukkan = 2,343
Masukkan dobel: -23.4
Dimasukkan dua kali = -23,4
Masukkan teks: Hei!
Teks yang dimasukkan = Hei!

Seperti yang disebutkan, ada beberapa cara lain untuk mendapatkan masukan dari pengguna. Untuk mempelajari lebih lanjut `Scanner`, kunjungi [Java Scanner](https://www.programiz.com/java-programming/scanner) .