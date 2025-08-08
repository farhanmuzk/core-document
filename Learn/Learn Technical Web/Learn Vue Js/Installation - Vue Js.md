
Vue.js menawarkan beberapa cara untuk memulai sebuah proyek. Berikut ini adalah tiga metode yang paling umum digunakan:

## **Menggunakan CDN (Tanpa Build Tools)**

Metode ini sangat sederhana dan cocok untuk pembelajaran atau prototipe cepat, tetapi memiliki keterbatasan untuk pengembangan proyek yang lebih kompleks. Anda dapat memulai dengan menambahkan tag `<script>` berikut ke dalam file HTML Anda:

```
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
```

Selain itu, Anda juga dapat menggunakan CDN lain seperti [jsdelivr](https://www.jsdelivr.com/package/npm/vue) atau [cdnjs](https://cdnjs.com/libraries/vue).

Metode ini tidak memerlukan instalasi atau konfigurasi tambahan, tetapi tidak mendukung fitur modern seperti modul ES atau pengelolaan dependensi, sehingga tidak cocok untuk proyek berskala besar. Penggunaan CDN lebih cocok untuk pembelajaran atau eksperimen sederhana.

---

## **Menggunakan Vite (Create-Vue)**

Metode ini direkomendasikan untuk memulai proyek modern dengan Vue 3 karena mendukung fitur pengembangan yang cepat dan efisien. Untuk memulai, jalankan perintah berikut di terminal:

```
npm create vue@latest
```

Perintah ini akan berjalan dalam mode interaktif yang memungkinkan Anda memilih fitur yang diinginkan. Jika Anda membutuhkan opsi tambahan, gunakan perintah:

```
npm create vue@latest -- --help
```

Jika Anda perlu mendukung Internet Explorer 11, Anda dapat membuat proyek Vue 2 dengan menjalankan:

```
npm create vue@legacy
```

Namun, perlu diperhatikan bahwa Vue 2 telah mencapai akhir masa dukungan ([End of Life](https://v2.vuejs.org/eol)). Metode ini mendukung fitur modern seperti HMR (Hot Module Replacement) dan waktu build yang lebih cepat dibandingkan Webpack. Akan tetapi, metode ini membutuhkan instalasi Node.js dan npm/yarn.

---

## **Menggunakan Vue CLI**

Vue CLI adalah alat berbasis Webpack yang dirancang untuk proyek dengan kebutuhan kompleks, seperti banyak plugin atau konfigurasi ekosistem yang matang. Anda dapat memulai dengan menginstal Vue CLI secara global menggunakan perintah:

```
npm install -g @vue/cli
```

Kemudian, buat proyek baru dengan perintah:

```
vue create nama-proyek-anda
```

Ikuti langkah interaktif untuk memilih preset dan pengaturan lainnya. Vue CLI menawarkan ekosistem yang stabil dan mendukung berbagai plugin, sehingga cocok untuk proyek skala besar. Namun, waktu build lebih lambat dibandingkan Vite, dan kompleksitasnya lebih tinggi karena menggunakan Webpack.

---