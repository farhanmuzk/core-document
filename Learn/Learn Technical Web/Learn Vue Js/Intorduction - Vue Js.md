# Apa Itu Vue.js?

Vue.js adalah **framework JavaScript** yang digunakan untuk membangun antarmuka pengguna (UI) dan aplikasi satu halaman (SPA). Vue mengadopsi pendekatan deklaratif dan berbasis komponen, yang membuat pengembang bisa fokus pada pembuatan UI dengan cara yang lebih efisien.

> [!TIP]
> [[Installation - Vue Js]] - Jika ingin membuat project Vue JS

# Vue: Framework yang Progresif

Vue adalah framework dan ekosistem yang mencakup sebagian besar fitur umum yang dibutuhkan dalam pengembangan frontend. Web sangat beragam, sehingga Vue dirancang untuk fleksibel dan bisa diadopsi secara bertahap. Tergantung pada kebutuhanmu, Vue dapat digunakan dalam berbagai cara:

- Menambah HTML statis tanpa langkah build
- Menyematkan sebagai Web Component di halaman mana pun
- Aplikasi Single-Page (SPA)
- Rendering di sisi server (SSR)
- Jamstack / Generasi Situs Statis (SSG)
- Menargetkan desktop, mobile, WebGL, bahkan terminal

# Struktur Project

my-vue-project/
├── node_modules/              # Dependencies yang diinstal oleh npm
├── public/                    # Folder untuk file statis (index.html, favicon.ico)
│   └── index.html             # File HTML utama
├── src/                       # Sumber kode aplikasi
│   ├── assets/                # Gambar, font, file statis lainnya
│   ├── components/            # Komponen Vue (untuk UI)
│   │   └── HelloWorld.vue     # Contoh komponen Vue
│   ├── views/                 # Halaman utama aplikasi
│   │   └── Home.vue           # Halaman utama aplikasi
│   ├── App.vue                # Komponen root aplikasi
│   ├── main.js                # File entri JavaScript untuk aplikasi Vue
│   └── router.js              # Konfigurasi rute (jika menggunakan Vue Router)
├── .gitignore                 # Menentukan file yang akan diabaikan oleh git
├── package.json               # Daftar dependencies dan script npm
└── README.md                  # Dokumentasi proyek

## Penjelasan Struktur Project

- **`public/`**: Berisi file-file statis seperti `index.html`, favicon, dan lainnya. Ini adalah file yang tidak akan diproses oleh Vue, tetapi hanya disajikan secara langsung.
    
- **`src/`**: Folder ini berisi semua kode sumber aplikasi. Di sinilah logika dan tampilan aplikasi Vue ditempatkan.
    
    - **`assets/`**: Tempat menyimpan file statis seperti gambar dan font.
    - **`components/`**: Menyimpan komponen-komponen Vue, yang dapat digunakan kembali dalam aplikasi.
    - **`views/`**: Halaman aplikasi yang lebih besar yang menggunakan beberapa komponen di dalamnya.
    - **`App.vue`**: Komponen root aplikasi Vue.
    - **`main.js`**: Titik masuk aplikasi Vue, di mana Vue diinisialisasi dan dijalankan.
    - **`router.js`**: Jika menggunakan Vue Router, file ini mengonfigurasi rute untuk aplikasi.
- **`package.json`**: Berisi informasi tentang proyek, dependensi, dan skrip untuk menjalankan aplikasi, seperti menjalankan server pengembangan atau membangun proyek untuk produksi.
    
- **`README.md`**: Berisi dokumentasi dan informasi dasar tentang cara menggunakan dan mengembangkan proyek.

# Single-File Components (SFC)

Dalam Vue, **Single-File Component (SFC)** adalah format file dengan ekstensi `.vue` yang memungkinkan pengembangan komponen terstruktur dalam satu file. Struktur SFC terbagi menjadi tiga bagian utama:

1. <**template** / >: Berisi HTML yang mendefinisikan tampilan komponen.
2. <**script** />: Berisi logika JavaScript untuk mengatur data dan perilaku komponen.
3. <**style** />: Berisi CSS untuk mengatur gaya dan tampilan komponen.

Berikut adalah contoh SFC:

```vue
<script>
export default {
  data() {
    return { count: 0 }
  }
}
</script>

<template>
  <button @click="count++">Count is: {{ count }}</button>
</template>

<style scoped>
button {
  font-weight: bold;
}
</style>
```

SFC adalah fitur utama Vue dan merupakan cara yang disarankan untuk menulis komponen Vue jika menggunakan alat build. Vue akan mengurus konfigurasi build untuk Anda.

# API Styles di Vue.js

Vue.js mendukung dua gaya API untuk menulis komponen: **Options API** dan **Composition API**.

## Options API

Dengan **Options API**, logika komponen didefinisikan menggunakan objek dengan properti seperti `data`, `methods`, dan `mounted`. Properti yang didefinisikan dalam `data()` akan menjadi **state reaktif** dan dapat diakses menggunakan `this`.

Contoh:

```vue
<script>
export default {
  // Properti dari data() menjadi state reaktif
  data() {
    return { count: 0 }
  },
  
  // Methods adalah fungsi untuk mengubah state
  methods: {
    increment() {
      this.count++
    }
  },
  
  // Lifecycle hook yang dipanggil saat komponen dimuat
  mounted() {
    console.log(`Initial count: ${this.count}`)
  }
}
</script>

<template>
  <button @click="increment">Count: {{ count }}</button>
</template>

```

## Composition API

Dengan **Composition API**, kita menggunakan fungsi API seperti `ref` dan `onMounted` untuk mendefinisikan logika komponen. Biasanya digunakan dengan `<script setup>` untuk mengurangi boilerplate.

Contoh:

```vue
<script setup>
import { ref, onMounted } from 'vue'

// Menentukan state reaktif menggunakan ref()
const count = ref(0)

// Fungsi yang mengubah state dan memicu update
function increment() {
  count.value++
}

// Lifecycle hook yang dipanggil saat komponen dimuat
onMounted(() => {
  console.log(`Initial count: ${count.value}`)
})
</script>

<template>
  <button @click="increment">Count: {{ count }}</button>
</template>
```

---

## Pilihan API: Mana yang Harus Dipilih?

- **Options API** lebih cocok untuk pengembang baru karena lebih mudah dipahami. Mengorganisir kode menggunakan grup opsi seperti `data`, `methods`, dll. Ini cocok untuk aplikasi sederhana atau jika tidak menggunakan alat build.
    
- **Composition API** lebih fleksibel dan lebih kuat untuk aplikasi yang lebih kompleks. Ini memungkinkan pengelolaan logika yang lebih modular dan reusable, namun membutuhkan pemahaman lebih dalam tentang reaktivitas Vue.
# Template Syntax

#VueJs menggunakan sintaks template berbasis HTML, jadi kita hanya perlu menulis HTML biasa. Vue akan menghubungkannya dengan data aplikasi secara otomatis. Di balik layar, Vue mengompilasi template menjadi kode JavaScript dan memperbarui DOM hanya pada bagian yang berubah, membuat aplikasi tetap efisien dan cepat.

## Text Interpolation

Interpolasi teks adalah bentuk data binding paling dasar yang menggunakan sintaks "Mustache" (kurung kurawal ganda). Sintaks ini memungkinkan Anda mengikat data komponen ke elemen HTML.

```html
<span>Message: {{ msg }}</span>
```

## Raw HTML

Untuk menampilkan HTML mentah (bukan hanya teks), Anda harus menggunakan **v-html**. Tanpa v-html, Vue hanya akan menampilkan teks biasa dan tidak mengeksekusi tag HTML.

```html
<p>Using text interpolation: {{ rawHtml }}</p>
<p>Using v-html directive: <span v-html="rawHtml"></span></p>
```

>[!WARNING]
>Menggunakan **v-html** dapat menyebabkan **XSS (Cross-site Scripting)** jika tidak berhati-hati, karena memungkinkan Anda mengeksekusi HTML yang dimasukkan secara dinamis. **Jangan gunakan** `v-html` untuk menampilkan konten dari pengguna tanpa validasi yang tepat.

## Attribute Binding

Mustache syntax tidak dapat digunakan di dalam atribut HTML. Sebagai gantinya, Anda harus menggunakan **v-bind** untuk mengikat nilai ke atribut.

```html
<div v-bind:id="dynamicId"></div>
```

### Shorthand untuk `v-bind`

Vue menyediakan sintaks shorthand untuk **v-bind**. Anda bisa menggunakan tanda titik dua (`:`) untuk menggantikan `v-bind`.

```html
<div :id="dynamicId"></div>
```

**Penjelasan**:

- Sintaks ini setara dengan `v-bind:id="dynamicId"`, tetapi lebih ringkas.
- Tanda titik dua (`:`) digunakan untuk menyatakan bahwa kita sedang mengikat nilai ke atribut.


### Shorthand untuk Atribut dengan Nama yang Sama

Vue 3.4+ memperkenalkan fitur di mana jika nama atribut sama dengan nama properti data, Anda dapat menghilangkan nilai atributnya.

```vue
<!-- same as :id="id" -->
<div :id></div>

<!-- this also works -->
<div v-bind:id></div>
```

## Atribut Boolean

Atribut boolean adalah atribut yang kehadirannya menunjukkan nilai `true` (misalnya, `disabled`, `checked`). Untuk atribut boolean seperti `disabled`, `v-bind` bekerja sedikit berbeda.

```html
<button :disabled="isButtonDisabled">Button</button>
```

## Mengikat Banyak Atribut Secara Dinamis

Jika memiliki objek JavaScript yang berisi beberapa atribut, Anda bisa mengikat objek tersebut ke elemen dengan menggunakan **v-bind** tanpa argumen.

```javascript
data() {
  return {
    objectOfAttrs: {
      id: 'container',
      class: 'wrapper'
    }
  }
}
```
```html
<div v-bind="objectOfAttrs"></div>
```

**Penjelasan**:

- Dengan menggunakan `v-bind="objectOfAttrs"`, Vue akan mengikat setiap atribut dalam `objectOfAttrs` ke elemen `div`. Dalam contoh ini, `id="container"` dan `class="wrapper"` akan ditambahkan ke elemen `div`.