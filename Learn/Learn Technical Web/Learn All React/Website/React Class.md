## Class Component di React

Sebelumnya kita sudah bahas pada [[React Basic]] tapi kita akan mempahas lebih mendalam di sini. Class Components** adalah cara lama tetapi masih umum digunakan dalam #React  untuk membuat komponen yang memiliki **state** dan fitur lifecycle. Class Components menggunakan sintaks berbasis **class ES6**.

---

## Membuat Class Component

Untuk membuat class component, Anda harus:
- Menggunakan kata kunci `class`.
- Mewarisi (`extends`) `React.Component`.
- Menambahkan metode wajib `render()` untuk mengembalikan elemen JSX.

Contoh Dasar Class Component:

```jsx
import React from "react";

class Greeting extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}

export default Greeting;
```

**Penjelasan:**

- `class Greeting` adalah class component.
- `this.props.name` digunakan untuk menerima **props**.
- Metode `render()` mengembalikan elemen JSX yang akan dirender ke UI.

---

## Props dalam Class Component

**Props** (Properti) adalah data yang dikirim dari komponen induk ke komponen anak. Di class component, props diakses menggunakan `this.props`.

Contoh:

```jsx
class Car extends React.Component {
  render() {
    return <h1>I am a {this.props.brand}!</h1>;
  }
}

function Garage() {
  return <Car brand="Ford" />;
}

export default Garage;
```

**Penjelasan:**

- `brand="Ford"` adalah props yang dikirim ke komponen `Car`.
- Komponen `Car` menerima props dan menampilkannya dengan `this.props.brand`.

---

## State dalam Class Component

**State** adalah data internal komponen yang dapat diubah. Untuk menggunakan state, Anda harus:

- Mendefinisikan state di dalam constructor.
- Menggunakan `this.setState()` untuk mengubah nilai state.

**Contoh:**

```jsx
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 }; // State awal
  }

  increment = () => {
    this.setState({ count: this.state.count + 1 }); // Mengubah state
  };

  render() {
    return (
      <div>
        <h1>Count: {this.state.count}</h1>
        <button onClick={this.increment}>Increment</button>
      </div>
    );
  }
}

export default Counter;
```

**Penjelasan:**

- State didefinisikan dalam `constructor`.
- `this.setState()` digunakan untuk mengubah nilai state.
- Setiap perubahan state akan memicu re-render komponen.

---

## Lifecycle Methods pada Class Component

**Lifecycle Methods** adalah metode khusus dalam React yang berjalan pada titik tertentu dalam siklus hidup komponen.

#### **Lifecycle Utama:**

1. **Mounting** (Ketika komponen pertama kali dirender):
    
    - `constructor()`
    - `componentDidMount()`
2. **Updating** (Ketika props atau state berubah):
    
    - `componentDidUpdate()`
3. **Unmounting** (Ketika komponen dihapus dari DOM):
    
    - `componentWillUnmount()`

**Contoh Lifecycle:**

```jsx
class LifeCycleDemo extends React.Component {
  constructor(props) {
    super(props);
    this.state = { message: "Hello!" };
    console.log("Constructor called");
  }

  componentDidMount() {
    console.log("Component did mount");
  }

  componentDidUpdate() {
    console.log("Component did update");
  }

  componentWillUnmount() {
    console.log("Component will unmount");
  }

  changeMessage = () => {
    this.setState({ message: "Goodbye!" });
  };

  render() {
    return (
      <div>
        <h1>{this.state.message}</h1>
        <button onClick={this.changeMessage}>Change Message</button>
      </div>
    );
  }
}

export default LifeCycleDemo;
```

**Penjelasan:**

- `componentDidMount()`: Dipanggil setelah komponen dirender ke DOM.
- `componentDidUpdate()`: Dipanggil setelah komponen diperbarui.
- `componentWillUnmount()`: Dipanggil sebelum komponen dihapus dari DOM.

---

## Event Handling dalam Class Component

Event handling di class component memerlukan metode tambahan untuk mengikat konteks `this`.

```jsx
class ButtonClick extends React.Component {
  constructor(props) {
    super(props);
    this.state = { clicked: false };
  }

  handleClick = () => {
    this.setState({ clicked: true });
  };

  render() {
    return (
      <button onClick={this.handleClick}>
        {this.state.clicked ? "Clicked!" : "Click Me"}
      </button>
    );
  }
}

export default ButtonClick;
```

**Penjelasan:**

- Arrow function (`handleClick`) otomatis terikat dengan konteks `this`.
- State berubah saat tombol diklik, dan komponen dirender ulang.

---

## Membuat Komponen Class Reusable

Gunakan props dan state untuk membuat komponen yang dapat digunakan kembali.

**Contoh:**

```jsx
class Welcome extends React.Component {
  render() {
    return <h1>Welcome, {this.props.name}!</h1>;
  }
}

function App() {
  return (
    <div>
      <Welcome name="Alice" />
      <Welcome name="Bob" />
    </div>
  );
}

export default App;
```

**Penjelasan:**

- `Welcome` digunakan kembali dengan props yang berbeda (`name="Alice"` dan `name="Bob"`).

---

## Kelebihan dan Kekurangan Class Component

**Kelebihan:**

- Mendukung state dan lifecycle methods.
- Cocok untuk logika kompleks.

**Kekurangan:**

- Syntax lebih panjang dibandingkan functional components.
- Functional components dengan hooks sekarang lebih disarankan.