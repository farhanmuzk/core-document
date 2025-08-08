---
tags:
  - VueJs
  - Components
Updated: 2025-01-07
---
# **Component Basics**

Konsep yang sama seperti dalam [[React Basic#Component|React]] untuk membagi UI menjadi beberapa bagian dan dapa digunakan kembali. dan biasanya aplikasi nya akan disusun menjadi pohon komponen bertingkat.
![[Pasted image 20250107040204.png]]
## **Defining a Component**

Walaupun Komponen pada Vue mempunyai kesamaan dengan konsep Komponen React, pada pembuatan nya Vue menggunakan extensi file `.vue` dan di sebut juga dengan [[Intorduction - Vue Js#Single-File Components (SFC) |Single-File Components (SFC)]]

```vue
<script>
export default {
  data() {
    return {
      count: 0
    }
  }
}
</script>

<template>
  <button @click="count++">You clicked me {{ count }} times.</button>
</template>
```

## **Elemen Root dalam Komponen?**

Element Root adalah Element DOM paling luar dalam komponen Vue, setiap komponen Vue harus memiliki satu element root dalam komponen.

**Single Root Element**:
<template>
  <button>Click Me</button> <!-- <button> adalah elemen root -->
</template>
```vue
<template>
  <button>Click Me</button> <!-- <button> adalah elemen root -->
</template>
```

**Multi Root Elements (Banyak Elemen Root):**
```vue
<template>
  <header>Header</header> <!-- Elemen root pertama -->
  <main>Main Content</main> <!-- Elemen root kedua -->
  <footer>Footer</footer> <!-- Elemen root ketiga -->
</template>
```

## **Using a Component**

Untuk menggunakan komponen anak, kita perlu mengimpornya ke dalam komponen induk. Contoh, jika kita memiliki file **ButtonCounter.vue** sebagai komponen anak, file tersebut diekspor sebagai default:

**ButtonCounter.vue** 

```vue
<script>
import ButtonCounter from './ButtonCounter.vue'

export default {
  components: {
    ButtonCounter
  }
}
</script>

<template>
  <h1>Ini adalah komponen anak!</h1>
  <ButtonCounter />
</template>
```

> [!NOTE]  
> Pada contoh code ini component menggunakan Local Registration kunjungi halaman ini untuk tahu GLobal Registration [[Component Registration - Vue Js]]

Jika kita ingin menggunakan  **ButtonCounter.vue**  lebih dari sekali, cukup tambahkan tag komponen di template:

```vue
<template>
  <h1>Ini adalah komponen anak!</h1>
  <ButtonCounter />
  <ButtonCounter />
  <ButtonCounter />
</template>
```

## **Passing Props**

Properti atau #Props adalah atribut khusus yang dapat di daftarkan pada komponen untuk mengirimkan data dari parent ke child

```vue
<!-- BlogPost.vue -->
<script setup>
defineProps(['title'])
</script>

<template>
	  <h4>{{ title }}</h4>
</template>
```

`dedefineProps` hanya tersedia di dalam **Composition** jika ingin menggunakan **Option**, props harus dideklarasikan menggunakna `props` dan objek akan diterukan ke `setup()` sebagai argumen pertama :

```vue
<!-- BlogPost.vue -->
<script>
export default {
  props: ['title']
}
</script>

<template>
  <h4>{{ title }}</h4>
</template>
```

Suatu komponen dapat memiliki properti sebanyak-banyaknya yang Anda suka dan, secara default, nilai apa pun dapat diteruskan ke properti apa pun.

```vue
<BlogPost title="My journey with Vue" />
<BlogPost title="Blogging with Vue" />
<BlogPost title="Why Vue is so fun" />
```

Penjelasan Lebih Detail : [[Component Props - Vue Js|Component Props]].


