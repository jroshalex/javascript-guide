
## 🧱 What Indexed Collections Are

* **Indexed collections** are ordered lists of values accessed by numeric indices (0, 1, 2, …).
* The main built-in indexed collection in JavaScript is the **Array**, but similar concepts apply to **typed arrays** and array-like objects. ([MDN Web Docs][1])

---

## 📌 Creating Arrays

You can create arrays in several equivalent ways:

```js
const arr1 = new Array(1, 2, 3);
const arr2 = Array(1, 2, 3);
const arr3 = [1, 2, 3];
```

* The bracket (`[]`) literal form is most common.
* To create an empty array of a certain length (with no values), you can use `Array(n)` or set `.length` manually. ([MDN Web Docs][1])

---

## 🔢 Accessing and Populating Arrays

* Array elements are accessed with square brackets: `arr[0]`, `arr[1]`, etc.
* You can assign elements later:

```js
const arr = [];
arr[0] = "first";
```

* Array indices are always integers. Non-integer “indexes” become normal object properties, not array elements. ([MDN Web Docs][1])

---

## 📊 The `length` Property

* `array.length` returns one more than the highest index used.
* Changing `.length` can truncate or expand the array: setting it smaller removes elements; setting it larger creates **empty slots**. ([MDN Web Docs][1])

---

## 🔁 Iterating Over Arrays

Common ways to loop through arrays:

* Classic `for` loop (with an index)
* `forEach()` method — calls a function for each element

Note: `forEach()` skips **empty slots** in sparse arrays. ([MDN Web Docs][1])

---

## 🛠️ Array Methods

JavaScript arrays have many built-in methods:

| Method                        | What it does                    |                     |
| ----------------------------- | ------------------------------- | ------------------- |
| `concat()`                    | Combines arrays                 |                     |
| `join()`                      | Converts to string              |                     |
| `push()` / `pop()`            | Add/remove end element          |                     |
| `shift()` / `unshift()`       | Remove/add front element        |                     |
| `slice()`                     | Extracts part of array          |                     |
| `splice()`                    | Adds/removes elements anywhere  |                     |
| `reverse()`                   | Reverses in place               |                     |
| `sort()`                      | Sorts array (can take callback) |                     |
| `flat()`                      | Flattens nested arrays          |                     |
| `indexOf()` / `lastIndexOf()` | Find positions of values        | ([MDN Web Docs][1]) |

---

## 🧠 Sparse Arrays

* Arrays can have “missing items” (empty slots) when you skip indices or set `.length` manually.
* These empty slots behave differently from slots explicitly set to `undefined`: some methods skip them, others treat them as `undefined`. ([MDN Web Docs][1])

---

## 🧱 Multi-Dimensional Arrays

You can nest arrays to make multi-dimensional structures:

```js
let grid = [
  [0, 1],
  [2, 3]
];
```

This lets you, for example, represent matrices or grids. ([MDN Web Docs][1])

---

## 🧠 Arrays as Objects

* Arrays are objects at heart, so you can attach custom properties:

```js
arr.myProperty = "value";
```

These don’t affect numeric indexing. ([MDN Web Docs][1])

---

## 🔍 Array-Like Objects

* Some objects behave *like* arrays (e.g., `arguments`, `NodeList`), with `.length` and indexed elements, but they **don’t have array methods** like `forEach`.
* You can borrow array methods using `Array.prototype.method.call()`. ([MDN Web Docs][1])

---

## 🧠 Key Takeaways

* Arrays are ordered collections where elements are accessed by numeric indices.
* JavaScript arrays are flexible objects with many built-in methods for manipulation.
* Sparse arrays and array-like objects behave similarly in some ways but differ in method support. ([MDN Web Docs][1])

---
