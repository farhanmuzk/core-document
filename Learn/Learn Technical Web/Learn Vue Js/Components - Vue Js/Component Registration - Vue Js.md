---
tags:
  - Components
  - VueJs
Updated: 2025-01-07
---
# Registrasi Komponen

Komponen pada Vue perlu "didaftarkan" agar Vue tahu di mana file kompnent yang ingin di gunakan. Ada dua cara untuk medaftarkan komponen : [[#Registrasi Global |Global]] dan [[#Registrasi Lokal |Lokal]].

---
## Registrasi Global

Untuk membuat Komponen Global di Vue saat ini menggunakan metode `.component()` :

```js
import { createApp } from 'vue'
import GlobalCOmponents from './components/GlobalComponents.vue'

const app = createApp(App)

app.component('GlobalCOmponents', GlobalCOmponents)

app.mount('#app')
```

Jika mendifinisikan banyak komponent

```js
app
  .component('ComponentA', ComponentA)
  .component('ComponentB', ComponentB)
  .component('ComponentC', ComponentC)
```

Komponen yang terdaftar secara global dapat digunakan dalam templat komponen apa pun dalam aplikasi ini:

```vue
<ComponentA/>
<ComponentB/>
<ComponentC/>
```

Ini bahkan berlaku untuk semua subkomponen, artinya ketiga komponen ini juga akan tersedia _di dalam satu sama lain_ .

---
## Registrasi Lokal

Komponen yang diregistrasi secara lokal hanya tersedia di dalam komponen tempat ia didaftarkan. Anda harus mengimpor dan mendeklarasikan komponen tersebut di bagian #Components setiap kali ingin menggunakannya.

Ada dua macam perbedaan penggunakan Registrasi Lokal di Vue :
###  Options 

Penggunaan Regristrasi Lokal menggunakan options :

```vue
<script>
import ComponentA from './ComponentA.vue'

export default {
  components: {
    ComponentA
  }
}
</script>

<template>
  <ComponentA />
</template>
```

### Composition

Penggunaan Registrasi Lokal menggunakan composition :

```vue
<script setup>
import ComponentA from './ComponentA.vue'
</script>

<template>
  <ComponentA />
</template>
```

---

## Kapan Menggunakan Global atau Lokal?

Penggunaan **Registrasi Global** dan **Registrasi Lokal** perlu diperhatikan dengan baik karena akan berdampak pada pengembangan aplikasi maupun hasil akhirnya. Memilih cara registrasi yang tepat dapat memengaruhi efisiensi, modularitas, dan ukuran bundle aplikasi.

#### Gunakan **Registrasi Global** jika

Komponen digunakan di banyak tempat dan bersifat **reusable**. Beberapa contoh komponen yang cocok untuk registrasi global meliputi:

- **Komponen Button**: Tombol yang sering digunakan dengan gaya atau fungsi yang konsisten.
- **Komponen Sidebar**: Navigasi samping yang tampil di berbagai halaman.
- **Komponen Header**: Bagian atas aplikasi yang umumnya tetap di berbagai halaman.
- **Komponen Footer**: Bagian bawah aplikasi yang sering digunakan secara konsisten.
- **Komponen Icon**: Ikon atau elemen visual kecil yang berulang kali muncul di seluruh aplikasi.

> **Catatan Penting:** Pertimbangkan dengan matang sebelum menggunakan registrasi global, karena komponen yang diregistrasi secara global **akan selalu dimasukkan dalam bundle final** meskipun tidak digunakan di semua tempat.

#### Gunakan **Registrasi Lokal** jika

Komponen hanya digunakan dalam lingkup tertentu atau dalam konteks yang sangat spesifik. Misalnya:

- Komponen yang hanya relevan untuk satu halaman atau fitur tertentu.
- Komponen yang memiliki dependensi atau fungsi unik yang tidak diperlukan di luar lingkup lokal.
- Ketika Anda ingin menjaga aplikasi tetap modular dan meminimalkan ukuran bundle.

Registrasi lokal membantu menjaga struktur kode lebih terorganisir dan menghindari konflik nama antar komponen.
