# Boolean

The `Boolean` object in JavaScript represents a logical value, either `true` or `false`. It serves as a wrapper for primitive boolean values and provides methods for converting other data types to boolean values.

## Constructor

### `Boolean(value)`

Converts a value to a boolean. Returns `true` for truthy values, and `false` for falsy values.

**Example:**

```js
console.log(Boolean(0)); // false
console.log(Boolean(1)); // true
console.log(Boolean("")); // false
console.log(Boolean("hello")); // true
```

**Arguments:**

- `value`: The value to convert to a boolean. (Required)

---

## Instance Methods

- [`valueOf()`](#valueof)
- [`toString()`](#tostring)

### `valueOf()`

Returns the primitive boolean value of the Boolean object.

**Example:**

```js
let boolObj = new Boolean(true);
console.log(boolObj.valueOf()); // true
```

---

### `toString()`

Returns a string representation of the boolean object, either `"true"` or `"false"`.

**Example:**

```js
let boolObj = new Boolean(false);
console.log(boolObj.toString()); // "false"
```
