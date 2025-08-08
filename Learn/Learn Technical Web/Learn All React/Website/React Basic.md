## Apa Itu React?

#React, Terkadang merujuk pada kerangka kerja frontend Javascript, React adalah sebuah leibary yang dibuat oleh Facebook.

React adalah sebuah alat untuk membuat UI #Components.

---
## Bagaimana Cara Kerjanya?

#React mempunyai fitur bernama #VirtualDom di dalam memori.

Alih-alih memanipulasi DOM browser secara langsung, React membuat DOM virtual di memori, tempat ia melakukan semua manipulasi yang diperlukan, sebelum membuat perubahan di DOM browser.

React hanya mengubah apa yang perlu diubah!

React mencari tahu perubahan apa yang telah dibuat, dan mengubah **hanya** apa yang perlu diubah.

---
## React Upgrade

Penjelasan untuk #React Upgrade bisa di lihat dari page ini : [[React Upgrade]]

**Note** : Pembahasan React ini pada versi 18

---
## JSX (JavaScript XML)

#JSX adalah cara menulis kode React yang terlihat seperti HTML di dalam file JavaScript.

Kenapa JSX? Karena membuat kode lebih mudah dibaca dan menulis UI jadi lebih sederhana.

Contoh JSX:

```jsx
const element = <h1>Hello, World!</h1>;
```

---
## Component

#Components  adalah bagian kecil dari aplikasi #React yang memiliki tugas tertentu. Tujuan #Components  untuk memecah aplikasi menjadi bagian-bagian kecil yang bisa digunakan kembali.

> [!WARNING]  
> Sekarang disarankan untuk menggunakan komponen Function bersama dengan Hooks, yang ditambahkan pada React 16.8. Namun Jika ingin tetap belajar #ReactClass kunjungi page [[React Class|React Class]]

Dua Jenis Komponen di React:
### Functional Component

#Components  Fungsi juga mengembalikan HTML, dan berperilaku hampir sama seperti komponen Kelas, tetapi komponen Fungsi dapat ditulis menggunakan kode yang jauh lebih sedikit, lebih mudah dipahami, dan akan lebih disukai dalam tutorial ini.

```jsx
function Car() {
  return <h2>Hi, I am a Car!</h2>;
}
```
### Class Component

#Components kelas harus menyertakan `extends React.Component` pernyataan tersebut. Pernyataan ini membuat pewarisan ke React.Component, dan memberikan komponen Anda akses ke fungsi-fungsi React.Component.

Komponen ini juga memerlukan sebuah `render()` metode, metode ini mengembalikan HTML.

```jsx
class Car extends React.Component {
  render() {
    return <h2>Hi, I am a Car!</h2>;
  }
}
```

---

## React Props 

#ReactProps adalah argumen yang dimasukkan ke dalam komponen React dalam #Props singkatan dari **Properti**. Jadi #ReactProps biasanya di gunakan untuk mengirim properti ke Components lain.

Contoh Components yang mengirimkan properti :

```jsx
const myElement = <Car brand="Ford" />;
```

Contoh Components yang menerima properti :

```jsx
function Car(props) {
  return <h2>I am a { props.brand }!</h2>;
}
```

---
## React Events

React memungkinkan kita untuk menangani berbagai event (peristiwa) seperti di HTML, misalnya: `click`, `change`, `mouseover`, dll.

Peristiwa React ditulis dalam sintaksis camelCase:
`onClick` alih-alih `onclick`.

Penanganan peristiwa React ditulis di dalam kurung kurawal:
`onClick={shoot}`  alih-alih `onclick="shoot()"`.

Contoh:

```jsx
<button onClick={shoot}>Take the Shot!</button> // di dalam React   
<button onclick="shoot()">Take the Shot!</button> // di dalam HTML
```

Contoh Dasar React Event:

```jsx
function Football() {
  const shoot = () => {
    alert("Great Shot!");
  };

  return <button onClick={shoot}>Take the shot!</button>;
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Football />);

```

---

## React Conditionals

React conditionals digunakan untuk menampilkan elemen atau komponen secara **dinamis** berdasarkan kondisi tertentu. Sama seperti if-else dalam JavaScript, kita menggunakan conditional rendering untuk menentukan apa yang harus ditampilkan.

---

### Menggunakan If-Else

Kondisi sederhana menggunakan **if-else** ditulis di dalam fungsi.

Contoh:

```jsx
function App() {
  const isLoggedIn = true;

  if (isLoggedIn) {
    return <h1>Welcome Back!</h1>;
  } else {
    return <h1>Please Sign In</h1>;
  }
}

```

### Menggunakan Ternary Operator

Cara lebih ringkas untuk menulis kondisi adalah menggunakan **ternary operator**.

Contoh:

```jsx
function App() {
  const isLoggedIn = true;

  return (
    <div>
      {isLoggedIn ? <h1>Welcome Back!</h1> : <h1>Please Sign In</h1>}
    </div>
  );
}

```

### Menggunakan Logical && (AND)

Jika hanya ingin menampilkan sesuatu berdasarkan kondisi **true**, gunakan operator `&&`.

Contoh:

```jsx
function App() {
  const isLoggedIn = true;

  return (
    <div>
      {isLoggedIn && <h1>Welcome Back!</h1>}
    </div>
  );
}

```