
## JavaScript Loops — Big Picture

A **loop** repeats code multiple times.
Sometimes it runs **zero times**, sometimes **at least once**, sometimes **until a condition changes**.

Different loop types exist because some situations are easier to express with one style than another.

---

## Core Loop Types

### `for`

**Best when you know how many times you want to loop**

```js
for (let i = 0; i < 5; i++) {
  // runs 5 times
}
```

How it works:

1. Initialize (`let i = 0`)
2. Check condition (`i < 5`)
3. Run loop body
4. Update (`i++`)
5. Repeat

👉 Most common loop for counting and arrays.

---

### `while`

**Runs as long as a condition is true**

```js
while (condition) {
  // runs while condition is true
}
```

* Condition checked **before** each iteration
* Might run **zero times**
* Easy to create infinite loops if the condition never becomes false

---

### `do...while`

**Runs at least once, no matter what**

```js
do {
  // runs first
} while (condition);
```

* Condition checked **after** the loop body
* Guaranteed to execute once

---

## Loop Control

### `break`

**Stops the loop completely**

```js
break;
```

* Exits the nearest loop or `switch`
* Can break out of **labeled loops** (rare, advanced)

---

### `continue`

**Skips to the next iteration**

```js
continue;
```

* Loop keeps running
* Skips remaining code in the current iteration

---

## Labeled Statements (Advanced / Rare)

Labels let you control **outer loops** from inside nested loops:

```js
labelName: while (...) {
  break labelName;
}
```

⚠️ Powerful but rarely needed—easy to make code harder to read.

---

## Looping Over Data

### `for...in`

**Loops over property names (keys)**

```js
for (const key in obj) {
  // key = property name
}
```

* Intended for **objects**
* ❌ Not recommended for arrays (includes extra properties)

---

### `for...of`

**Loops over values**

```js
for (const value of iterable) {
  // value = actual item
}
```

* Best for **arrays, strings, maps, sets**
* Clean and modern
* Most common choice for collections

---

## Key Differences (Super Important)

| Loop Type    | Iterates Over   | Use Case           |
| ------------ | --------------- | ------------------ |
| `for`        | numbers/indexes | Known loop count   |
| `while`      | condition       | Unknown loop count |
| `do...while` | condition       | Must run once      |
| `for...in`   | keys            | Objects            |
| `for...of`   | values          | Arrays & iterables |

---

## TL;DR (What to Actually Remember)

* Use `for` when counting
* Use `while` when looping until something changes
* Use `do...while` if it must run once
* Use `for...of` for arrays
* Avoid `for...in` for arrays
* `break` stops a loop, `continue` skips an iteration
