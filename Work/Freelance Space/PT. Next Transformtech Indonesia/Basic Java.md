# Pertanyaan Java Dasar
### 1. **Apa itu Java?**

Java adalah bahasa pemrograman berbasis objek yang dikembangkan oleh Sun Microsystems (sekarang diakuisisi oleh Oracle). Java dirancang agar platform-independent, artinya kode Java dapat dijalankan di berbagai sistem operasi menggunakan prinsip _Write Once, Run Anywhere (WORA)_.

---

### 2. **Apa perbedaan JDK, JRE, dan JVM?**

- **JDK (Java Development Kit):**  
    JDK adalah paket perangkat lunak yang mencakup alat-alat untuk mengembangkan aplikasi Java, seperti compiler, debugger, dan library.
    
- **JRE (Java Runtime Environment):**  
    JRE menyediakan lingkungan untuk menjalankan aplikasi Java. Ini termasuk JVM dan library yang diperlukan untuk eksekusi aplikasi.
    
- **JVM (Java Virtual Machine):**  
    JVM adalah mesin virtual yang bertugas mengeksekusi kode bytecode Java. JVM adalah inti dari prinsip platform-independent Java.
    

---

### 3. **Apa fitur utama Java?**

- **Object-Oriented**: Berbasis objek.
- **Platform-Independent**: Menggunakan JVM untuk menjembatani sistem operasi.
- **Multithreading**: Mendukung proses multitasking.
- **Garbage Collection**: Manajemen memori otomatis.
- **Secure**: Melindungi dari ancaman seperti virus dan manipulasi data.
- **Robust**: Memiliki sistem pengecekan error yang kuat.

---

### 4. **Apa perbedaan Java dan JavaScript?**

- **Java** adalah bahasa pemrograman untuk aplikasi besar, berbasis server, dan berorientasi objek.
- **JavaScript** adalah bahasa scripting yang berjalan di browser, sering digunakan untuk membuat elemen interaktif pada halaman web.

---

### 5. **Apa itu bahasa pemrograman berorientasi objek?**

Bahasa pemrograman berorientasi objek (OOP) adalah paradigma pemrograman yang mengorganisasi kode menjadi objek, yang terdiri dari data (atribut) dan fungsi (metode).

---

### 6. **Apa saja pilar dari pemrograman berorientasi objek?**

- **Inheritance (Pewarisan):** Pewarisan properti dan metode dari kelas lain.
- **Polymorphism (Polimorfisme):** Kemampuan untuk memiliki banyak bentuk.
- **Encapsulation (Enkapsulasi):** Pembungkusan data dan metode dalam satu unit.
- **Abstraction (Abstraksi):** Menyembunyikan detail implementasi dan hanya menunjukkan fungsionalitas.

---

### 7. **Apa itu kelas dalam Java?**

Kelas adalah blueprint atau template untuk membuat objek. Kelas mendefinisikan atribut (data) dan metode (fungsi) dari suatu objek.

---

### 8. **Apa itu objek dalam Java?**

Objek adalah instance dari kelas. Objek merepresentasikan entitas nyata yang memiliki atribut dan perilaku.

---

### 9. **Bagaimana cara membuat objek di Java?**

Objek dibuat menggunakan keyword `new`. Contohnya:

java

Salin kode

`NamaKelas namaObjek = new NamaKelas();`

---

### 10. **Apa perbedaan kelas dan objek di Java?**

- **Kelas:** Template untuk membuat objek.
- **Objek:** Instance dari kelas yang memiliki nilai aktual.

---

### 11. **Jelaskan konsep pewarisan (inheritance) dalam Java.**

Pewarisan adalah mekanisme di mana satu kelas (subclass) dapat mewarisi properti dan metode dari kelas lain (superclass). Ini memungkinkan penggunaan kembali kode.

---

### 12. **Apa tujuan keyword `super` dalam Java?**

Keyword `super` digunakan untuk:

- Mengakses konstruktor atau metode dari superclass.
- Mengacu pada variabel superclass ketika ada konflik dengan subclass.

---

### 13. **Apa itu polimorfisme dalam Java?**

Polimorfisme adalah kemampuan objek untuk mengambil banyak bentuk. Contohnya adalah metode dengan nama yang sama tetapi implementasi berbeda (overloading dan overriding).

---

### 14. **Apa perbedaan method overloading dan method overriding di Java?**

- **Overloading:** Nama metode sama tetapi parameter berbeda (di dalam kelas yang sama).
- **Overriding:** Nama metode sama dengan parameter yang sama, tetapi implementasinya berbeda (antara superclass dan subclass).

---

### 15. **Apa itu enkapsulasi dalam Java?**

Enkapsulasi adalah proses membungkus data (atribut) dan metode dalam satu unit (kelas) dan membatasi akses ke data menggunakan modifier akses.

---

### 16. **Apa tujuan modifier akses dalam Java?**

Modifier akses digunakan untuk mengontrol visibilitas atribut dan metode dalam kelas.

---

### 17. **Apa perbedaan antara public, private, dan protected?**

- **Public:** Dapat diakses dari mana saja.
- **Private:** Hanya dapat diakses dalam kelas itu sendiri.
- **Protected:** Dapat diakses oleh kelas dalam paket yang sama atau subclass.