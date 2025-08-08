## React Hooks

React Hooks diperkenalkan pada #React 16.8 untuk memungkinkan penggunaan state dan lifecycle methods seperti hal nya [[React Class]] namun ini di terapkan di functional component. Hooks membuat pengelolaan logika komponen lebih mudah, lebih bersih, dan efisien.

### 1. **`useState()`**

`useState` digunakan untuk menambahkan state lokal ke dalam functional component.

- Menerima satu argumen: nilai awal state.
- Mengembalikan array dengan dua elemen: nilai state saat ini dan fungsi untuk memperbarui nilai state.

**Contoh:**

```jsx
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0); // state awal

  return (
    <div>
      <h1>Count: {count}</h1>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}

export default Counter;
```

**Penjelasan:**

- `count` adalah nilai state saat ini.
- `setCount` adalah fungsi untuk memperbarui state.
- Setiap kali `setCount` dipanggil, komponen akan dirender ulang.

---

### 2. **`useEffect()`**

`useEffect` digunakan untuk menangani side effects seperti fetching data, manipulasi DOM, atau pengaturan timer.

- Dipanggil setelah render pertama kali dan setelah setiap update.

**Contoh:**

```jsx
import React, { useState, useEffect } from "react";

function Timer() {
  const [seconds, setSeconds] = useState(0);

  useEffect(() => {
    const interval = setInterval(() => {
      setSeconds(prevSeconds => prevSeconds + 1);
    }, 1000);

    return () => clearInterval(interval); // Cleanup function
  }, []); // Array kosong sebagai dependency

  return <h1>Seconds: {seconds}</h1>;
}

export default Timer;
```

**Penjelasan:**

- Efek dijalankan setelah render pertama kali.
- Array kosong (`[]`) memastikan efek hanya dijalankan sekali.
- `return` digunakan untuk membersihkan efek sebelumnya.

---

### 3. **`useContext()`**

`useContext` digunakan untuk mengakses nilai dari `React Context` tanpa perlu menggunakan `Context.Consumer`.

**Contoh:**

```jsx
import React, { useContext } from "react";

const UserContext = React.createContext();

function UserProfile() {
  const user = useContext(UserContext);

  return <h1>Hello, {user.name}!</h1>;
}

function App() {
  const user = { name: "Alice" };

  return (
    <UserContext.Provider value={user}>
      <UserProfile />
    </UserContext.Provider>
  );
}

export default App;
```

**Penjelasan:**

- `useContext` digunakan untuk mengakses nilai context langsung dari provider.
### 4. **`useReducer()`**

`useReducer` adalah alternatif untuk `useState` yang cocok digunakan untuk logika state yang lebih kompleks.

- Menerima reducer function dan nilai awal state.
- Mengembalikan array dengan dua elemen: nilai state saat ini dan fungsi dispatch.

**Contoh:**

```jsx
import React, { useReducer } from "react";

function Counter() {
  const reducer = (state, action) => {
    switch (action.type) {
      case "increment":
        return state + 1;
      case "decrement":
        return state - 1;
      default:
        return state;
    }
  };

  const [count, dispatch] = useReducer(reducer, 0); // state awal

  return (
    <div>
      <h1>Count: {count}</h1>
      <button onClick={() => dispatch({ type: "increment" })}>Increment</button>
      <button onClick={() => dispatch({ type: "decrement" })}>Decrement</button>
    </div>
  );
}

export default Counter;

```

**Penjelasan:**

- `dispatch` digunakan untuk mengirim action ke reducer.
- `reducer` menentukan bagaimana state diperbarui berdasarkan action yang diterima.

---

### 5. **`useRef()`**

`useRef` digunakan untuk mengakses elemen DOM langsung atau menyimpan nilai persisten yang tidak memicu render ulang.

**Contoh:**

```jsx
import React, { useRef } from "react";

function InputFocus() {
  const inputRef = useRef(null);

  const focusInput = () => {
    inputRef.current.focus();
  };

  return (
    <div>
      <input ref={inputRef} type="text" />
      <button onClick={focusInput}>Focus Input</button>
    </div>
  );
}

export default InputFocus;
```

**Penjelasan:**

- `ref` digunakan untuk mereferensikan elemen DOM.
- `current` mengacu pada elemen DOM atau nilai yang disimpan di dalam ref.

---

### 6. **`useMemo()`**

`useMemo` digunakan untuk mengoptimalkan performa dengan cara memoization, menghitung ulang nilai hanya jika dependensi berubah.

**Contoh:**

```jsx
import React, { useMemo, useState } from "react";

function ExpensiveCalculation() {
  const [count, setCount] = useState(0);

  const double = useMemo(() => {
    console.log("Calculating...");
    return count * 2;
  }, [count]);

  return (
    <div>
      <h1>Double: {double}</h1>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}

export default ExpensiveCalculation;
```

**Penjelasan:**

- `useMemo` hanya akan menghitung ulang jika `count` berubah.

---

### 7. **`useCallback()`**

`useCallback` digunakan untuk memoize fungsi, agar fungsi tersebut tidak dibuat ulang pada setiap render.

**Contoh:**

```jsx
import React, { useState, useCallback } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  const increment = useCallback(() => {
    setCount((prevCount) => prevCount + 1);
  }, []); // Fungsi hanya dibuat ulang jika dependensi berubah

  return <button onClick={increment}>Count: {count}</button>;
}

export default Counter;
```

**Penjelasan:**

- `useCallback` memastikan fungsi `increment` tidak dibuat ulang kecuali jika dependensinya berubah.