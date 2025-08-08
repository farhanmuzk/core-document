---
tags:
  - Java
  - TipeData
---
![[Pasted image 20250111015106.png]]

---
# Tipe Data Tidak Primitif (Referensi)

Tipe data **tidak primitif** adalah tipe data yang dibuat berdasarkan objek atau referensi ke lokasi memori. Contohnya adalah string, array, dan kelas.

## Karakteristik Tipe Data Tidak Primitif

- **Objek**, sehingga memiliki metode dan atribut.
- Menunjuk ke lokasi memori (referensi) alih-alih menyimpan nilai langsung.
- Dapat menyimpan nilai `null` (artinya tidak merujuk ke objek mana pun).
- Dibuat menggunakan kelas.

## Jenis Tipe Data Tidak Primitif

Jenis tipe data nya sudah di jelasakan pada halaman : [[Tipe Data String - Java]], 

| **Jenis Tipe Data** | **Deskripsi**                                                                     |
| ------------------- | --------------------------------------------------------------------------------- |
| String              | Digunakan untuk menyimpan teks.                                                   |
| Array               | Digunakan untuk menyimpan kumpulan nilai dengan tipe data yang sama.              |
| Class               | Digunakan untuk mendefinisikan objek yang memiliki atribut dan perilaku tertentu. |
| Interface           | Digunakan untuk mendefinisikan perilaku (method) yang harus diimplementasikan.    |
## Contoh Tipe Data Tidak Primitif

```java
// Contoh penggunaan semua tipe data bukan primitif
class Person {
    String name; // Variabel instance
    int age;

    // Method untuk menampilkan informasi
    void displayInfo() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
}

public class NonPrimitiveDataExample {
    public static void main(String[] args) {
        // 1. Tipe data String
        String greeting = "Hello, Non-Primitive Data!"; // String untuk menyimpan teks
        System.out.println("Greeting: " + greeting);

        // 2. Tipe data Array
        int[] numbers = {10, 20, 30, 40, 50}; // Array untuk menyimpan kumpulan nilai
        System.out.println("First number in array: " + numbers[0]);

        // 3. Tipe data Class
        Person person = new Person(); // Membuat objek Person
        person.name = "Alice";
        person.age = 30;
        person.displayInfo(); // Memanggil method pada objek

        // 4. Tipe data Interface (implementasi sederhana)
        Animal dog = new Dog(); // Menggunakan interface
        dog.makeSound();

        // 5. Null reference
        String nullExample = null; // Contoh referensi null
        System.out.println("Null Example: " + nullExample);
    }
}

// 4. Contoh penggunaan interface
interface Animal {
    void makeSound(); // Method abstrak
}

class Dog implements Animal {
    @Override
    public void makeSound() {
        System.out.println("Dog says: Woof Woof!");
    }
}
```