

## **JavaScript Numbers & Strings — Key Points**

### **Numbers**

JavaScript’s number type represents **numeric values** using the standard floating-point format (IEEE 754). It handles:

* **Regular numbers**, including integers and decimals.
* Special values: **Infinity**, **–Infinity**, and **NaN** (not a number).([MDN Web Docs][1])

#### **Numeric Literals**

You can write numbers in different formats:

* **Decimal**: normal numbers (`42`, `100`).([MDN Web Docs][1])
* **Binary**: prefix with `0b` (`0b1010`).([MDN Web Docs][1])
* **Octal**: prefix with `0o` (`0o755`).([MDN Web Docs][1])
* **Hexadecimal**: prefix with `0x` (`0xFF`).([MDN Web Docs][1])
* **Exponent notation**: using `e` (`1e3` → `1000`).([MDN Web Docs][1])
* You can also improve readability with **numeric separators** (`1_000_000`).([MDN Web Docs][1])

#### **Number Object**

JavaScript provides the built-in `Number` object with constants and helper methods like:

* `Number.MAX_VALUE`, `Number.MIN_VALUE`
* `Number.isFinite()`, `Number.isInteger()`, `Number.isNaN()`
  And prototype methods like `toFixed()`, `toPrecision()`.([MDN Web Docs][1])

#### **Math Object**

`Math` contains mathematical constants and functions such as:

* `Math.PI`, `Math.sin()`, `Math.max()`, `Math.random()`
  These help with standard math operations.([MDN Web Docs][1])

#### **BigInt**

For integers larger than JavaScript numbers can safely represent, use **BigInt**. BigInts end with an `n` (e.g., `123n`) and allow arbitrarily large integer arithmetic.([MDN Web Docs][2])

---

### **Strings**

Strings represent **text** and are sequences of UTF-16 characters.([MDN Web Docs][1])

#### **String Literals**

You can write strings using:

* **Single quotes** (`'hello'`)
* **Double quotes** (`"world"`)
* **Escape sequences** (`"\n"`, `"\u00A9"` for ©) to include special characters.([MDN Web Docs][1])

#### **String Methods**

Strings have many built-in methods for working with text:

* Searching (`indexOf`, `includes`)
* Extracting pieces (`slice`, `substring`)
* Changing case (`toUpperCase`, `toLowerCase`)
* Modifying content (`trim`, `repeat`)
  Methods return **new strings**, because strings are immutable in JavaScript.([MDN Web Docs][3])

---

### **Template Literals**

A newer string feature using **backticks** (`` ` ``). They let you:

* Write **multi-line strings** easily
* Embed expressions directly inside `${ }` (string interpolation)
  Example: `` `Hello ${name}!` ``.([MDN Web Docs][1])

---

## **Bottom Line**

* **Numbers** in JavaScript are all floating-point, have special edge values, and work with the built-in `Number` and `Math` objects.
* **BigInts** handle very large integers precisely.
* **Strings** handle text and come with many useful methods.
* **Template literals** make building dynamic and multi-line strings easier.([MDN Web Docs][1])

---

[1]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Numbers_and_strings?utm_source=chatgpt.com "Numbers and strings - JavaScript | MDN"
[2]: https://developer.mozilla.org/my/docs/Web/JavaScript/Guide/Text_formatting?utm_source=chatgpt.com "Numbers and strings - JavaScript | MDN"
[3]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Numbers_and_strings "Numbers and strings - JavaScript | MDN"
