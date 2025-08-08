---
tags:
  - VueJs
  - Components
Updated: 2025-01-07
---
# Apa Itu Fallthrough Attributes?

Fallthrough Attributes adalah atribut seperti :

- **Class**
- **Id**
- **@Click**

yang secara otomatis diteruskan dari pemanggilan komponent parent ke [[Component Basics - Vue Js#**Elemen Root dalam Komponen?** |Element Root]] di dalam komponen terebut, **tanpa perlu mendeklarasikan dalam props atau emits**.

Contoh ketika mempunyai komponen **MyButton.vue** :  

```vue
<template>
  <button>Click Me</button>
</template>
```

Ketika pemanggilan anda bisa melakukan

```vue
<MyButton class="btn-primary" @click="handleClick" />
```

yang membuat menerik adalah kita tidak perlu menambahkan class atau @click pada child component, kita bisa langsung definisikan pada parent nya.

# Kenapa Fallthrough Attributes Dibuat?

Fallthrough Attributes dibuat karna ada keresahan dimana sebelum konsep ini dibuat developer perlu mendifiniskan prop manual untuk setiap atribut tambahan di komponen child.

Contoh sebelum ada nya Fallthrough Attributes :

```vue
<MyButton class="primary" />
```

Komponen **MyButton.vue** harus mendifiniskan `class` sebagai prop agar bisa menerima atribut tersebut :

```vue
<script>
export default {
  props: {
    class: String, // Harus mendefinisikan prop 'class'
  },
}
</script>

<template>
  <button :class="class">Click Me</button>
</template>
```

> [!WARNING] 
> Harus mendeklarasikan setiap atribut tambahan secara manual sebagai prop, yang **tidak efisien** dan Membuat kode lebih panjang (boilerplate).


# Kapan Fallthrough Attributes Digunakan?

ada beberapa kondisi penggunakan Fallthrough Attributes : 

## Komponen Sederhana (Default Fallthrough):

Komponen dengan satu elemen root secara otomatis menerima atribut. contoh ini sama seperti yang di contohkan di awal.

```vue
<!-- MyButton.vue -->
<template>
  <button>Click Me</button>
</template>
```

```vue
<MyButton class="btn-large" @click="onClick" />
```

## Multi-root Components (Banyak Elemen Root)

Jika komponen memiliki lebih dari satu elemen root, atribut tidak akan otomatis jatuh. Anda harus menentukan secara eksplisit menggunakan `$attrs`.

```vue
<!-- MyButton.vue -->
<template>
  <img src="icon.png" alt="Icon" />
  <button v-bind="$attrs">Click Me</button>
</template>
```

```vue
<MyButton class="btn-secondary" @click="handleClick" />
```

## Komponen dengan Wrapper (Pembungkus Elemen Root)

Jika elemen root adalah pembungkus (misalnya `<div>`), Anda dapat mengontrol atribut jatuh ke elemen tertentu dengan menggunakan `inheritAttrs: false`.

```vue
<script setup>
defineOptions({ inheritAttrs: false })
</script>

<template>
  <div class="btn-wrapper">
    <button v-bind="$attrs">Click Me</button>
  </div>
</template>
```

```vue
<MyButton class="btn-primary" id="main-button" @click="handleClick" />
```
