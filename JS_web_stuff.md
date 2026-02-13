
# 1️⃣ `querySelector` → “Get stuff from the page”

### What it really is:

A way to **grab HTML elements so you can control them**

### Syntax:

```js
const el = document.querySelector("selector");
```

### Selectors you’ll use:

```js
"#id"        // one element
".class"     // group
"div"        // tag
```

### Mental model:

👉 “I can’t change something unless I grab it first”

### Example:

```js
const button = document.querySelector("#submit");
```

---

# 2️⃣ `addEventListener` → “Wait for user action”

### What it really is:

Lets your page **react to events**

### Syntax:

```js
element.addEventListener("event", function);
```

### Example:

```js
button.addEventListener("click", () => {
    console.log("clicked");
});
```

### Common events:

* `"click"` → button press
* `"input"` → typing
* `"change"` → dropdown
* `"submit"` → form

### Mental model:

👉 “When X happens → do Y”

---

# 3️⃣ `classList` → “Change appearance cleanly”

### Why it matters:

You **don’t hardcode styles in JS** — you toggle CSS classes instead

### Syntax:

```js
element.classList.add("active");
element.classList.remove("active");
element.classList.toggle("active");
```

### Example:

```js
popup.classList.add("show");
```

### CSS:

```css
.popup { display: none; }
.popup.show { display: block; }
```

### Mental model:

👉 “JS controls *state*, CSS controls *appearance*”

---

# 4️⃣ `.value` → “Get user input”

### What it does:

Reads what the user typed

### Example:

```js
const input = document.querySelector("#name");

console.log(input.value);
```

### Real use:

```js
button.addEventListener("click", () => {
    alert(input.value);
});
```

### Mental model:

👉 “What did the user enter?”

---

# 5️⃣ `setTimeout` → “Do something later”

### What it does:

Runs code **after a delay**

```js
setTimeout(() => {
    console.log("2 seconds later");
}, 2000);
```

### Why useful:

* popups
* animations
* delays

### Mental model:

👉 “Not now — later”

---

# 6️⃣ Functions (especially arrow functions)

### What they are:

Reusable blocks of code

---

## Normal function:

```js
function greet() {
    console.log("hi");
}
```

## Arrow function (modern JS):

```js
const greet = () => {
    console.log("hi");
};
```

### Why arrow functions matter:

* shorter
* used everywhere (especially in events)

---

### Real usage:

```js
button.addEventListener("click", () => {
    console.log("clicked");
});
```

---

### Mental model:

👉 “Bundle actions into a reusable command”

---

# 7️⃣ `fetch` → “Talk to servers / backend”

### What it does:

Gets data from somewhere else (API, ESP32, backend)

---

### Basic example:

```js
fetch("/data")
    .then(res => res.json())
    .then(data => {
        console.log(data);
    });
```

---

### Why YOU care (important for your ESP32 idea):

👉 Your web page can:

* send commands to ESP32
* receive data (sensor values, button states)

---

### Mental model:

👉 “Ask another computer for data”

---

# 🔥 How they ALL connect (this is key)

### Example: button → send command → update UI

```js
const btn = document.querySelector("#ledBtn");

btn.addEventListener("click", () => {
    fetch("/toggle-led");

    btn.classList.toggle("active");
});
```

---

# 🧠 Ultimate mental model

Every web app is basically:

### 1. Grab element

```js
querySelector
```

### 2. Wait for something

```js
addEventListener
```

### 3. Do something

* change class (`classList`)
* read input (`.value`)
* delay (`setTimeout`)
* run logic (functions)
* talk to server (`fetch`)


