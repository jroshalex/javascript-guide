# 🧱 HTML “shii” (structure)

## Core page parts

* **`<head>`**
  Invisible stuff (settings, metadata, links to CSS, etc.)

* **`<body>`**
  Everything the user actually sees

---

## Metadata & config

* **`<meta>`**
  Extra info about the page (not visible)

* **`charset`**
  Defines text encoding (almost always `"UTF-8"`)
  👉 prevents weird characters from breaking

* **`name`** (in `<meta>`)
  Label for the type of metadata

  ```html
  <meta name="viewport" ...>
  ```

---

## Links & resources

* **`<link>`**
  Connects external files (usually CSS)

* **`rel`**
  Relationship of the file
  👉 `"stylesheet"` = CSS file

* **`href`**
  The path/URL to the file

Example:

```html
<link rel="stylesheet" href="styles.css">
```

---

## Content elements

* **`<div>`**
  Generic container (box for grouping stuff)

---

## Attributes (VERY important)

* **`class`**
  Reusable label (can apply to many elements)
  👉 used for styling / JS

* **`id`**
  Unique identifier (only one per page)
  👉 used for targeting a specific element

Example:

```html
<div class="popup" id="mainPopup"></div>
```

---

## Navigation

* **`<a>`** (anchor)
  A clickable link

```html
<a href="https://google.com">Go</a>
```

---

# 🎨 CSS “shii” (styling & layout)

## Layout

* **`flex`**
  Enables flexbox layout
  👉 makes aligning stuff WAY easier

```css
display: flex;
```

---

## Display types

* **`block`**
  Takes full width (like `<div>`)

* **`none`**
  Hides element completely

---

## Units

* **`rem`**
  Relative to root font size (usually 16px)
  👉 `1rem = 16px`

---

## Positioning

* **`relative`**
  Positioned relative to itself
  👉 lets you shift it without breaking layout

---

## Value keywords (inheritance & defaults)

* **`inherit`**
  Takes value from parent element

* **`initial`**
  Resets to default browser value

---

## Text sizing

* **`larger`**
  Bigger than parent font size (relative scaling)

