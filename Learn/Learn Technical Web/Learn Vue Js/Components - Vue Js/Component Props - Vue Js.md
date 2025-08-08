---
tags:
  - VueJs
  - Components
Updated: 2025-01-07
---
# Component Props 

Sebelumnya props sudah di bahas pada [[Component Basics - Vue Js |Component Basics]] Props adalah cara untuk meneruskan data dari komponen induk ke komponen anak.

## Props Declaration

 Props dideklarasikan secara expilist agar vue dapat memahami atribut apa yang di anggap sebagai Props dan yang mena menjadi atribut [[Atribut Interhance- Vue Js|Atribut Fallthrough]].

### Penggunaan Props pada Array

Dalam konsep #Composition deklarasi menggunakan `defineProps()` :

```vue
<script setup>
const props = defineProps(['foo']);

console.log(props.foo); // Akses prop bernama 'foo'
</script>
```

jika anda menggunakan #Options deklasari mmenggunakan `props` :

```vue
<script>
	export default {
	  props: ['foo'],
	  setup(props) {
	    // setup() receives props as the first argument.
	    console.log(props.foo)
	  }
	}; // Akses prop bernama 'foo'
</script>
```
### Penggunaan Props pada Object

Selain mendeklarasikan properti menggunakan array string, kita juga dapat menggunakan sintaksis objek:

```vue
// in <script setup>
defineProps({
  title: String,
  likes: Number
})
```

```vue
// in non-<script setup>
export default {
  props: {
    title: String,
    likes: Number
  }
}
```

Untuk setiap properti dalam sintaksis deklarasi objek, kuncinya adalah nama properti, sedangkan nilainya harus berupa fungsi konstruktor dengan tipe yang diharapkan.

Jika project menggunaka Typescript dengan konsep #Composition saat pendeklarasian properti dapat menggunakan anotasi tipe murni: 

```vue
<script setup lang="ts">
	defineProps<{
	  title?: string
	  likes?: number
	}>()
</script>
```

Pembahasan Lebih Lanjut : [[Typing Component Props - Vue JS | Typing Component Props]].

## Reactive Props Destructure

di Vue dapat menggunakan **destructuring** untuk mengambil properti tersebut langsung. Namun, ada hal penting yang perlu diperhatikan: jika kita mendestructure props, kita perlu memastikan bahwa **reaktivitasnya tetap berfungsi**. Artinya, jika nilai prop berubah, Vue harus tahu dan merender ulang komponen jika diperlukan.

Contoh ketika ada komponen **TodoItem.vue**, komponen ini menerima prop `todo` dan menampilkan nya.

```vue
<template>
  <div>{{ todo }}</div>
</template>

<script setup>
// Menerima prop todo dari komponen induk
const { todo } = defineProps();
</script>
```

>[!Warning]
>Di **Vue 3.4 ke bawah**, ada masalah saat kita menggunakan destructuring untuk prop yang tidak akan tetap reaktif. Vue hanya melacak **`props.todo`**, bukan `todo` yang didestructuring.

Misalnya kita ingin menggunakan nilai default untuk prop `todo` penggunaan nya speerti ini :

```vue
<template>
  <div>{{ todo }}</div>
</template>

<script setup>
// Destructuring prop dengan default value
const { todo = 'Belajar Vue 3 default' } = defineProps();
</script>

```

Kadang kita perlu mengamati perubahan prop dengan **watch**. Berikut adalah contoh bagaimana menggunakan **getter** untuk tetap menjaga reaktivitas saat menggunakan **destructured props**.

```vue
<script>
	watch(() => todo, (newVal) => { console.log('Todo berubah:', newVal); });
</script>
```

**Vue akan menjalankan `watch` setiap kali nilai `todo` berubah**, dan kita akan melihat perubahan di konsol. Namun jika anda menggunakan code seperti ini

```vue
<script>
	watch(todo,(newVal) => { console.log('Todo berubah:', newVal); });
</script>
```

Ini tidak akan berfungsi sebagaimana mestinya karena ini setara dengan `watch(props.foo, ...)`- kita meneruskan nilai alih-alih sumber data reaktif ke `watch`. Faktanya, kompiler Vue akan menangkap kasus seperti itu dan memberikan peringatan.

## Passing Props Details

### Props Name Casing 

Kita mendeklarasikan nama properti yang panjang menggunakan #camelCase.

```js
defineProps({
  greetingMessage: String
})
```

```html
<span>{{ greetingMessage }}</span>
```

dan menggunakan #kebab-case saat meneruskan props di template : 

```vue
<MyComponent greeting-message="hello" />
```

### Static vs. Dynamic Props

Penggunaan props jika data nya statis maka akan seperti ini :

```vue
<BlogPost title="My journey with Vue" />
```

sedangkan untuk data dinamis menggunakan `v-bind` atau `:` untuk pembuatan lebih praktis :

```vue
<!-- Dynamically assign the value of a variable -->
<BlogPost :title="post.title" />

<!-- Dynamically assign the value of a complex expression -->
<BlogPost :title="post.title + ' by ' + post.author.name" />
```

>[!Note]
>Penjelasan lebih lanjut untuk mengetahui props bisa menerima tipe nilai apa saja. 
>
>[Dokumentasi Resmi Vue Js](https://vuejs.org/guide/components/props.html#prop-passing-details).

### Binding Multiple Properties Using an Object

Jika properti berbentuk objek dapat menggunakan `v-bind` sebagai cara praktik di banding menggunakan `prop-name`.

```js
const post = { id: 1, title: 'My Journey with Vue' }
```

untuk menentukan props nya akan seperti ini.

```vue
<BlogPost v-bind="post" />
```

Akan setara dengan 

```vue
<BlogPost :id="post.id" :title="post.title" />
```

## One-Way Data Flow
Dalam Vue, data dari induk ke anak mengalir satu arah. Artinya, jika data di induk berubah, anak akan otomatis mendapat nilai terbaru, tetapi anak tidak bisa langsung mengubah data induk.

Jangan ubah properti langsung di anak, karena ini akan memunculkan peringatan dari Vue. Tetap gunakan alur data ini untuk menjaga kode lebih jelas dan mudah dipahami.

### Solution to Avoid Direct Changes to Props

#### Local data property

Jika prop hanya digunakan untuk memberi nilai awal, salin ke data lokal menggunakan `ref`:

```js
const props = defineProps(['initialCounter']);
const counter = ref(props.initialCounter); // Salin nilai awal dari prop
```

**Penjelasan** :
-  `counter` adalah data lokal yang dapat Anda ubah.
-  Prop `initialCounter` tetap tidak diubah, meskipun `counter` berubah.

#### Computed Property

Jika Anda perlu memodifikasi prop untuk penggunaan tertentu, gunakan **computed property**:

```js 
const props = defineProps(['size']);
const normalizedSize = computed(() => props.size.trim().toLowerCase());
```

**Penjelasan** : 
- `normalizedSize` akan selalu diperbarui secara otomatis ketika prop `size` berubah.
- Tidak ada perubahan langsung pada prop `size`.

## Prop Validation

Validasi props memastikan bahwa data yang dikirimkan ke komponen sesuai dengan aturan tertentu, seperti tipe data, keharusan, atau nilai default. Jika aturan tidak terpenuhi, Vue akan memberikan peringatan di konsol saat pengembangan.

### How to Determine Props Validation

Gunakan objek di dalam `defineProps()` untuk menentukan aturan validasi:

```js
defineProps({
  // Basic type check
  //  (`null` and `undefined` values will allow any type)
  propA: Number,
  // Multiple possible types
  propB: [String, Number],
  // Required string
  propC: {
    type: String,
    required: true
  },
  // Required but nullable string
  propD: {
    type: [String, null],
    required: true
  },
  // Number with a default value
  propE: {
    type: Number,
    default: 100
  },
  // Object with a default value
  propF: {
    type: Object,
    // Object or array defaults must be returned from
    // a factory function. The function receives the raw
    // props received by the component as the argument.
    default(rawProps) {
      return { message: 'hello' }
    }
  },
  // Custom validator function
  // full props passed as 2nd argument in 3.4+
  propG: {
    validator(value, props) {
      // The value must match one of these strings
      return ['success', 'warning', 'danger'].includes(value)
    }
  },
  // Function with a default value
  propH: {
    type: Function,
    // Unlike object or array default, this is not a factory
    // function - this is a function to serve as a default value
    default() {
      return 'Default function'
    }
  }
})
```

Penjelasan Tambahan : 
- Props bersifat opsional secara default, kecuali diberi `required: true`.
- Jika props opsional tidak diberikan, nilainya `undefined`, kecuali ada nilai default.

### Boolean Props

Jika properti hanya bertipe `Boolean`, penggunaannya otomatis mengikuti aturan.

```js
defineProps({
  disabled: Boolean
});
```

Komponen ini dapat digunakan seperti ini:

```vue
<!-- equivalent of passing :disabled="true" -->
<MyComponent disabled />

<!-- equivalent of passing :disabled="false" -->
<MyComponent />
```

Jika properti mendukung beberapa tipe, aturan khusus berlaku:

```js
// disabled will be casted to true
defineProps({
  disabled: [Boolean, Number]
})

// disabled will be casted to true
defineProps({
  disabled: [Boolean, String]
})

// disabled will be casted to true
defineProps({
  disabled: [Number, Boolean]
})

// disabled will be parsed as an empty string (disabled="")
defineProps({
  disabled: [String, Boolean]
})
```

>[!Warning]
>Boolean props memiliki aturan khusus:
    - Jika dideklarasikan sebagai `[Boolean, String]`, dan `Boolean` disebut lebih dulu, props akan dianggap `true` jika digunakan tanpa nilai.
    - Jika `[String, Boolean]`, maka props dianggap sebagai string kosong (`""`) jika digunakan tanpa nilai.

### Supported Types for Validation

Vue mendukung tipe seperti:

- **String**, **Number**, **Boolean**, **Array**, **Object**, **Date**, **Function**, **Symbol**, **Error**
- **Custom Class**: Anda juga bisa memvalidasi dengan class khusus menggunakan `instanceof`.

```js
class Person {
  constructor(firstName, lastName) {
    this.firstName = firstName
    this.lastName = lastName
  }
}
```

```js
defineProps({
  author: Person, // author harus instance dari class Person
});
```

Dengan validasi props, Anda bisa menjaga agar data yang masuk ke komponen lebih konsisten dan mudah dikelola.