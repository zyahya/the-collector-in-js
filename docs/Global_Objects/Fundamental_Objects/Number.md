# Number

The `Number` object in JavaScript represents numeric values, both integers and floating-point numbers. It provides methods and properties for performing mathematical operations, converting numbers, and handling special numeric values like `NaN` and `Infinity`.

- [Number](#number)
  - [`Number(value)` Constructor](#numbervalue-constructor)
  - [Static Methods](#static-methods)
    - [`Number.isFinite(value)`](#numberisfinitevalue)
    - [`Number.isInteger(value)`](#numberisintegervalue)
    - [`Number.isNaN(value)`](#numberisnanvalue)
    - [`Number.isSafeInteger(value)`](#numberissafeintegervalue)
    - [`Number.parseFloat(string)`](#numberparsefloatstring)
    - [`Number.parseInt(string, radix)`](#numberparseintstring-radix)
  - [Static Properties](#static-properties)
    - [`Number.EPSILON`](#numberepsilon)
    - [`Number.MAX_SAFE_INTEGER`](#numbermax_safe_integer)
    - [`Number.MAX_VALUE`](#numbermax_value)
    - [`Number.MIN_SAFE_INTEGER`](#numbermin_safe_integer)
    - [`Number.MIN_VALUE`](#numbermin_value)
    - [`Number.NaN`](#numbernan)
    - [`Number.NEGATIVE_INFINITY`](#numbernegative_infinity)
    - [`Number.POSITIVE_INFINITY`](#numberpositive_infinity)
  - [Instance Methods](#instance-methods)
    - [`toExponential(fractionDigits)`](#toexponentialfractiondigits)
    - [`toFixed(digits)`](#tofixeddigits)
    - [`toLocaleString(locales, options)`](#tolocalestringlocales-options)
    - [`toPrecision(precision)`](#toprecisionprecision)
    - [`toString(radix)`](#tostringradix)
    - [`valueOf()`](#valueof)

## `Number(value)` Constructor

Creates a `Number` object or converts a given value to a primitive number.

**Example:**

```js
console.log(Number("42")); // 42
console.log(Number("3.14")); // 3.14
console.log(Number(true)); // 1
console.log(Number(false)); // 0
console.log(Number(null)); // 0
console.log(Number(undefined)); // NaN
console.log(Number("hello")); // NaN
```

If used with `new`, it creates a `Number` object instead of a primitive number:

```js
let numObj = new Number(42);
console.log(numObj); // [Number: 42]
console.log(typeof numObj); // "object"
```

**Arguments:**

- `value`: The value to convert to a number.

**Note:**

- Avoid using `new Number()` as it creates an object instead of a primitive, which can lead to unexpected behavior.
- Use `Number(value)` for type conversion.

---

## Static Methods

### `Number.isFinite(value)`

Returns `true` if `value` is a finite number, otherwise `false`.

**Example:**

```js
console.log(Number.isFinite(42)); // true
console.log(Number.isFinite(Infinity)); // false
console.log(Number.isFinite("42")); // false
```

**Arguments:**

- `value`: The value to check.

---

### `Number.isInteger(value)`

Returns `true` if `value` is an integer, otherwise `false`.

**Example:**

```js
console.log(Number.isInteger(10)); // true
console.log(Number.isInteger(10.5)); // false
console.log(Number.isInteger("10")); // false
```

**Arguments:**

- `value`: The value to check.

---

### `Number.isNaN(value)`

Returns `true` if `value` is `NaN` and is of type `Number`, otherwise `false`.

**Example:**

```js
console.log(Number.isNaN(NaN)); // true
console.log(Number.isNaN("NaN")); // false
console.log(Number.isNaN(5 / "hello")); // true
```

**Arguments:**

- `value`: The value to check.

---

### `Number.isSafeInteger(value)`

Returns `true` if `value` is a safe integer (within `Number.MIN_SAFE_INTEGER` to `Number.MAX_SAFE_INTEGER`), otherwise `false`.

**Example:**

```js
console.log(Number.isSafeInteger(9007199254740991)); // true
console.log(Number.isSafeInteger(9007199254740992)); // false
console.log(Number.isSafeInteger(3.14)); // false
```

**Arguments:**

- `value`: The value to check.

---

### `Number.parseFloat(string)`

Parses a string and returns a floating-point number.

**Example:**

```js
console.log(Number.parseFloat("3.14")); // 3.14
console.log(Number.parseFloat("10px")); // 10
console.log(Number.parseFloat("px10")); // NaN
```

**Arguments:**

- `string`: The string to parse.

---

### `Number.parseInt(string, radix)`

Parses a string and returns an integer, using the given radix.

**Example:**

```js
console.log(Number.parseInt("42")); // 42
console.log(Number.parseInt("101", 2)); // 5
console.log(Number.parseInt("FF", 16)); // 255
console.log(Number.parseInt("10px")); // 10
console.log(Number.parseInt("px10")); // NaN
```

**Arguments:**

- `string`: The string to parse.
- `radix` (Optional): The base for conversion (between `2` and `36`). Defaults to `10`.

---

## Static Properties

### `Number.EPSILON`

The smallest difference between two representable numbers.

**Example:**

```js
console.log(Number.EPSILON); // 2.220446049250313e-16
```

---

### `Number.MAX_SAFE_INTEGER`

The largest safe integer in JavaScript (`2^53 - 1`).

**Example:**

```js
console.log(Number.MAX_SAFE_INTEGER); // 9007199254740991
```

---

### `Number.MAX_VALUE`

The largest positive number in JavaScript.

**Example:**

```js
console.log(Number.MAX_VALUE); // 1.7976931348623157e+308
```

---

### `Number.MIN_SAFE_INTEGER`

The smallest safe integer in JavaScript (`-(2^53 - 1)`).

**Example:**

```js
console.log(Number.MIN_SAFE_INTEGER); // -9007199254740991
```

---

### `Number.MIN_VALUE`

The smallest positive number in JavaScript, close to zero but not zero.

**Example:**

```js
console.log(Number.MIN_VALUE); // 5e-324
```

---

### `Number.NaN`

Represents "Not-a-Number" (`NaN`).

**Example:**

```js
console.log(Number.NaN); // NaN
console.log(Number.NaN === NaN); // false (NaN is never equal to itself)
```

---

### `Number.NEGATIVE_INFINITY`

Represents negative infinity.

**Example:**

```js
console.log(Number.NEGATIVE_INFINITY); // -Infinity
console.log(-1 / 0); // -Infinity
```

---

### `Number.POSITIVE_INFINITY`

Represents positive infinity.

**Example:**

```js
console.log(Number.POSITIVE_INFINITY); // Infinity
console.log(1 / 0); // Infinity
```

---

## Instance Methods

### `toExponential(fractionDigits)`

Returns a string representing the number in exponential notation.

**Example:**

```js
let num = 12345.6789;

console.log(num.toExponential()); // "1.23456789e+4"
console.log(num.toExponential(2)); // "1.23e+4"
```

**Arguments:**

- `fractionDigits` (Optional): The number of decimal places. Defaults to showing all significant digits.

---

### `toFixed(digits)`

Returns a string representing the number with a fixed number of decimal places.

**Example:**

```js
let num = 123.456;

console.log(num.toFixed()); // "123"
console.log(num.toFixed(2)); // "123.46"
console.log(num.toFixed(5)); // "123.45600"
```

**Arguments:**

- `digits` (Optional): The number of decimal places. Defaults to `0`.

---

### `toLocaleString(locales, options)`

Returns a string representing the number formatted according to a specific locale.

**Example:**

```js
let num = 1234567.89;

console.log(num.toLocaleString("en-US")); // "1,234,567.89"
console.log(num.toLocaleString("de-DE")); // "1.234.567,89"
console.log(num.toLocaleString("ar-EG")); // "١٬٢٣٤٬٥٦٧٫٨٩"
```

**Arguments:**

- `locales` (Optional): A BCP 47 language tag (e.g., `"en-US"`, `"de-DE"`). Defaults to the environment's locale.
- `options` (Optional): Formatting options like `{ style: "currency", currency: "USD" }`.

---

### `toPrecision(precision)`

Returns a string representing the number with a specified number of significant digits.

**Example:**

```js
let num = 123.456;

console.log(num.toPrecision(4)); // "123.5"
console.log(num.toPrecision(2)); // "1.2e+2"
console.log(num.toPrecision(6)); // "123.456"
```

**Arguments:**

- `precision`: The number of significant digits.

---

### `toString(radix)`

Returns a string representation of the number in the given base.

**Example:**

```js
let num = 255;

console.log(num.toString()); // "255"
console.log(num.toString(2)); // "11111111" (binary)
console.log(num.toString(16)); // "ff" (hexadecimal)
```

**Arguments:**

- `radix` (Optional): The base for conversion (between `2` and `36`). Defaults to `10`.

---

### `valueOf()`

Returns the primitive numeric value of a `Number` object.

**Example:**

```js
let num = new Number(42);

console.log(num.valueOf()); // 42
```
