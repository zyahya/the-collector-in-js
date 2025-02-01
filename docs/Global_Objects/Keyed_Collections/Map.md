# Map

The `Map` object in JavaScript represents a collection of key-value pairs. It provides methods for adding, retrieving, and iterating over entries, with keys of any data type supported.

## `Map()` Constructor

Creates a new Map object. A Map holds key-value pairs where keys can be any datatype and the values can also be any datatype.

**Example:**

```js
let map = new Map();
map.set("name", "John");
map.set(1, "One");

console.log(map.get("name")); // John
console.log(map.get(1)); // One
```

---

## Static Methods

### `Map.groupBy(array, callbackFn)`

Creates an object grouped by the results of the callback function. Useful for transforming a collection into a structured form.

**Example:**

```js
const numbers = [1, 2, 3, 4, 5];
const grouped = Map.groupBy(numbers, (num) => (num % 2 === 0 ? "even" : "odd"));

console.log(grouped); // { even: [2, 4], odd: [1, 3, 5] }
```

**Arguments:**

- `array`: The array to group.
- `callbackFn`: A function used to group the values in the array.

---

## Static Properties

### `Map[Symbol.species]`

Specifies the constructor function that should be used to create derived objects. It is used in cases like `Map` being subclassed.

**Example:**

```js
let map = new Map();
console.log(map[Symbol.species]); // [Function: Map]
```

---

## Instance Methods

- [`clear()`](#clear)
- [`delete(key)`](#deletekey)
- [`entries()`](#entries)
- [`forEach(callbackFn, thisArg)`](#foreachcallbackfn-thisarg)
- [`get(key)`](#getkey)
- [`has(key)`](#haskey)
- [`keys()`](#keys)
- [`set(key, value)`](#setkey-value)
- [`values()`](#values)
- [`[Symbol.iterator]()`](#symboliterator)

### `clear()`

Removes all entries from the map.

**Example:**

```js
let map = new Map();
map.set("name", "John");
map.clear();
console.log(map.size); // 0
```

---

### `delete(key)`

Removes the entry with the specified key from the map.

**Example:**

```js
let map = new Map();
map.set("name", "John");
map.delete("name");
console.log(map.has("name")); // false
```

**Arguments:**

- `key`: The key of the entry to remove.

---

### `entries()`

Returns a new iterator object that contains an array of `[key, value]` pairs from the map.

**Example:**

```js
let map = new Map();
map.set("name", "John");
let entries = map.entries();
for (let [key, value] of entries) {
  console.log(key, value); // "name", "John"
}
```

---

### `forEach(callbackFn, thisArg)`

Executes a provided function once for each key-value pair in the map.

**Example:**

```js
let map = new Map();
map.set("name", "John");
map.forEach((value, key) => {
  console.log(key, value); // "name", "John"
});
```

**Arguments:**

- `callbackFn`: Function to execute on each element in the map.
- `thisArg` (Optional): Value to use as `this` inside `callbackFn`.

---

### `get(key)`

Returns the value associated with the given key.

**Example:**

```js
let map = new Map();
map.set("name", "John");
console.log(map.get("name")); // John
```

**Arguments:**

- `key`: The key of the element to retrieve.

---

### `has(key)`

Returns `true` if the map contains the specified key, otherwise `false`.

**Example:**

```js
let map = new Map();
map.set("name", "John");
console.log(map.has("name")); // true
console.log(map.has("age")); // false
```

**Arguments:**

- `key`: The key to check for existence in the map.

---

### `keys()`

Returns a new iterator object that contains the keys in the map.

**Example:**

```js
let map = new Map();
map.set("name", "John");
let keys = map.keys();
for (let key of keys) {
  console.log(key); // "name"
}
```

---

### `set(key, value)`

Adds or updates an entry in the map with the given key and value.

**Example:**

```js
let map = new Map();
map.set("name", "John");
console.log(map.get("name")); // John
map.set("name", "Jane");
console.log(map.get("name")); // Jane
```

**Arguments:**

- `key`: The key to set.
- `value`: The value associated with the key.

---

### `values()`

Returns a new iterator object that contains the values of the map.

**Example:**

```js
let map = new Map();
map.set("name", "John");
let values = map.values();
for (let value of values) {
  console.log(value); // "John"
}
```

---

### `[Symbol.iterator]()`

Returns a new iterator object that iterates over `[key, value]` pairs from the map.

**Example:**

```js
let map = new Map();
map.set("name", "John");
for (let [key, value] of map) {
  console.log(key, value); // "name", "John"
}
```

---

## Instance Properties

### `size`

Returns the number of key-value pairs in the map.

**Example:**

```js
let map = new Map();
map.set("name", "John");
console.log(map.size); // 1
```
