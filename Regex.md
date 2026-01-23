

## 💡 What Regular Expressions Are

Regular expressions (often called **regex**) are **patterns used to find, match, or manipulate text** within strings. In JavaScript, regexes are objects that you can use with string and regex methods to test for patterns, extract data, replace text, split strings, etc. ([MDN Web Docs][1])

---

## 🔨 Creating Regular Expressions

You can make a regex in two ways: ([MDN Web Docs][1])

1. **Literal format** — pattern between slashes:

   ```js
   const re = /ab+c/;
   ```

   This is compiled when the script loads. ([MDN Web Docs][1])

2. **Constructor function** — using `RegExp`:

   ```js
   const re = new RegExp("ab+c");
   ```

   Useful when the pattern is variable or built from user input. ([MDN Web Docs][1])

---

## 📜 Regex Pattern Basics

A regex pattern is a mix of normal characters and **special characters** that mean things like:

* Repeating patterns (`*`, `+`, `{n}`, etc.)
* Character types (`\d`, `\w`, `\s`, etc.)
* Boundaries (`^`, `$`)
* Groups and submatches (`(...)`) ([MDN Web Docs][1])

To match special characters literally (like `*`), you **escape** them with a backslash `\`. ([MDN Web Docs][1])

---

## 🔄 Using Regex with JavaScript

You apply regex patterns with methods on **RegExp** or **String**: ([MDN Web Docs][1])

| Method                       | What it Does                                |
| ---------------------------- | ------------------------------------------- |
| `test()`                     | Checks if a pattern exists (true/false)     |
| `exec()`                     | Finds a match and returns details OR `null` |
| `match()`                    | Returns all matches as an array             |
| `matchAll()`                 | Returns an iterator over all matches        |
| `search()`                   | Returns index of first match                |
| `replace()` / `replaceAll()` | Replace matches in text                     |
| `split()`                    | Breaks string using pattern                 |

---

## 🚩 Regex Flags

Flags modify how the regex works. Common flags include: ([MDN Web Docs][2])

| Flag | Meaning                                             |
| ---- | --------------------------------------------------- |
| `g`  | Global search — finds all matches                   |
| `i`  | Case-insensitive                                    |
| `m`  | Multiline — `^` and `$` match each line             |
| `s`  | Dotall — `.` matches newlines                       |
| `u`  | Unicode mode                                        |
| `y`  | Sticky — match starting exactly at current position |
| `d`  | Generates indices for matched parts                 |

Flags are part of the regex and cannot be changed afterward. ([MDN Web Docs][2])

---

## 🧠 Important Notes

* If you use a regex literal repeatedly without storing it in a variable, each use creates a **new regex object**, so properties like `lastIndex` won’t persist. ([MDN Web Docs][1])
* Unicode mode (`u`) enables support for matching extended Unicode patterns and properties. ([MDN Web Docs][2])

---

## 📊 How Matches Differ

* `test()` and `search()` tell you **if** a match exists.
* `exec()` and `match()` provide **match details** and capture groups.
* With the `g` flag, you can iterate over all matches with multiple `exec()` calls. ([MDN Web Docs][1])

---

## 👩‍💻 Practical Use

Regex is great for:

* Validating input (like emails or phone numbers)
* Extracting patterns (like dates in text)
* Replacing text using patterns instead of simple substrings ([MDN Web Docs][2])

---


[1]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions?utm_source=chatgpt.com "Regular expressions - JavaScript | MDN"
[2]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions?utm_source=chatgpt.com "Regular expressions - JavaScript | MDN"
