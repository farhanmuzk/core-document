---
tags:
  - Java
  - TipeData
---
Java menyediakan dua tipe data floating point, yaitu **float** dan **double**, yang keduanya mengikuti standar IEEE 754. Keduanya dirancang untuk merepresentasikan bilangan desimal, namun memiliki perbedaan signifikan dalam hal ukuran, presisi, dan penggunaan.

# Tipe Data Float 

Tipe data **float** adalah tipe data primitif berukuran **32-bit** yang menggunakan presisi tunggal (_single-precision_). Tipe ini mampu merepresentasikan rentang nilai yang luas, baik dalam angka positif maupun negatif, termasuk nilai yang sangat kecil atau sangat besar.

Namun, float memiliki **batas presisi hingga sekitar 6-7 digit desimal signifikan**, sehingga tidak cocok untuk aplikasi yang membutuhkan ketelitian tinggi, seperti perhitungan keuangan atau data sensitif lainnya.

```java
float f1 = 234.5f;
```

Karakter **`f`** pada akhir nilai diperlukan untuk menandai bahwa nilai tersebut adalah tipe data float.

# Tipe Data Double

Tipe data **double** adalah tipe data primitif berukuran **64-bit** dengan presisi ganda (_double-precision_). Tipe ini menawarkan rentang nilai yang lebih besar dibandingkan float dan tingkat presisi yang lebih tinggi, mencapai sekitar **15-16 digit desimal signifikan**.

Double sangat cocok digunakan untuk aplikasi yang memerlukan ketelitian tinggi, seperti:

- Perhitungan ilmiah.
- Perhitungan keuangan yang membutuhkan presisi lebih tinggi.
- Pemrograman grafis dan simulasi fisika.

```java
double d1 = 12.3;
```

Default nilai desimal pada Java adalah tipe **double**, sehingga tidak memerlukan tambahan karakter khusus.

---

# Perbedaan Float dan Double

| **Aspek**     | **Float**                                      | **Double**                                            |
| ------------- | ---------------------------------------------- | ----------------------------------------------------- |
| Ukuran        | 32-bit                                         | 64-bit                                                |
| Presisi       | 6-7 digit desimal signifikan                   | 15-16 digit desimal signifikan                        |
| Rentang Nilai | Lebih kecil                                    | Lebih besar                                           |
| Kinerja       | Lebih cepat (menggunakan lebih sedikit memori) | Lebih lambat (karena ukuran data lebih besar)         |
| Penggunaan    | Grafik, game, simulasi sederhana               | Perhitungan ilmiah, keuangan, aplikasi presisi tinggi |