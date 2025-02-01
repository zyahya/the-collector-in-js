# Array

The `Array` object in JavaScript is a collection of ordered elements that can store multiple values in a single variable. Arrays are zero-indexed, meaning the first element has an index of `0`.

## Static Methods

This category includes:

- [`Array.from(arrayLike, mapFn, thisArg)`](#arrayfromarraylike-mapfn-thisarg)
- [`Array.fromAsync(arrayLike, mapFn, thisArg)`](#arrayfromasyncarraylike-mapfn-thisarg)
- [`Array.isArray(value)`](#arrayisarrayvalue)
- [`Array.of(elementN)`](#arrayofelementn)

---

### `Array.from(arrayLike, mapFn, thisArg)`

Creates a new array from an array-like or iterable object. An optional `mapFn` can modify elements during creation.

**Example:**

```js
let str = "hello";

console.log(Array.from(str)); // ["h", "e", "l", "l", "o"]
console.log(Array.from([1, 2, 3], (x) => x * 2)); // [2, 4, 6]
console.log(Array.from("9528", Number)); // [9, 5, 2, 8]
```

**Arguments:**

- `arrayLike`: The array-like or iterable object to convert.
- `mapFn` (Optional): A function to apply to each element before adding it to the array.
  - `element`: The current element.
  - `index` (Optional): The index of the element. Defaults to `0`.
  - `array` (Optional): The array being created.
- `thisArg` (Optional): Value to use as `this` inside `mapFn`.

---

### `Array.fromAsync(arrayLike, mapFn, thisArg)`

Similar to `Array.from`, but supports async iterables and returns a `Promise` resolving to an array.

**Example:**

```js
async function* asyncGen() {
  yield 1;
  yield 2;
  yield 3;
}

Array.fromAsync(asyncGen()).then(console.log); // [1, 2, 3]
```

**Arguments:**

- `arrayLike`: The array-like or async iterable object to convert.
- `mapFn` (Optional): A function to apply to each element before adding it to the array.
  - `element`: The current element.
  - `index` (Optional): The index of the element. Defaults to `0`.
  - `array` (Optional): The array being created.
- `thisArg` (Optional): Value to use as `this` inside `mapFn`.

---

### `Array.isArray(value)`

Returns `true` if `value` is an array, otherwise `false`.

**Example:**

```js
console.log(Array.isArray([1, 2, 3])); // true
console.log(Array.isArray("hello")); // false
console.log(Array.isArray({})); // false
```

**Arguments:**

- `value`: The value to check.

---

### `Array.of(elementN)`

Creates a new array with the provided elements. Unlike `Array`, it avoids unintended behavior with a single numeric argument.

**Example:**

```js
console.log(Array.of(3)); // [3]
console.log(Array(3)); // [ <3 empty slots> ]
console.log(Array.of(1, 2, 3)); // [1, 2, 3]
```

**Arguments:**

- `elementN`: Elements to include in the new array.

---

## Instance Methods

### Accessing Elements

Used to retrieve elements from an array based on their position or check for their existence.

This category includes:

- [`at(index)`](#atindex)
- [`indexOf(searchElement, fromIndex)`](#indexofsearchelement-fromindex)
- [`lastIndexOf(searchElement, fromIndex)`](#lastindexofsearchelement-fromindex)
- [`includes(searchElement, fromIndex)`](#includessearchelement-fromindex)

---

#### `at(index)`

Returns the element at the specified `index`. Supports negative indexing.

**Example:**

```js
let arr = [10, 20, 30];

console.log(arr.at(1)); // 20
console.log(arr.at(-1)); // 30
```

**Arguments:**

- `index`: The position of the element to retrieve. Supports negative values for accessing from the end.

---

#### `indexOf(searchElement, fromIndex)`

Returns the first index where `searchElement` is found, or `-1` if not found.

**Example:**

```js
let arr = [10, 20, 30, 20];

console.log(arr.indexOf(20)); // 1
console.log(arr.indexOf(50)); // -1
console.log(arr.indexOf(20, 2)); // 3
```

**Arguments:**

- `searchElement`: The value to locate in the array.
- `fromIndex` (Optional): The index to start the search from. Defaults to `0`.

---

#### `lastIndexOf(searchElement, fromIndex)`

Returns the last index where `searchElement` is found, or `-1` if not found.

**Example:**

```js
let arr = [10, 20, 30, 20];

console.log(arr.lastIndexOf(20)); // 3
console.log(arr.lastIndexOf(50)); // -1
console.log(arr.lastIndexOf(20, 2)); // 1
```

**Arguments:**

- `searchElement`: The value to locate in the array.
- `fromIndex` (Optional): The index to start searching backwards from. Defaults to `array.length - 1`.

---

#### `includes(searchElement, fromIndex)`

Returns `true` if `searchElement` exists in the array, otherwise `false`.

**Example:**

```js
let arr = [10, 20, 30];

console.log(arr.includes(20)); // true
console.log(arr.includes(50)); // false
console.log(arr.includes(20, 2)); // false
```

**Arguments:**

- `searchElement`: The value to check for in the array.
- `fromIndex` (Optional): The index to start the search from. Defaults to `0`.

---

### Searching & Filtering

Help find specific elements in an array, either by condition or direct match, and filter elements based on criteria.

This category includes:

- [`filter(callbackFn, thisArg)`](#filtercallbackfn-thisarg)
- [`find(callbackFn, thisArg)`](#findcallbackfn-thisarg)
- [`findIndex(callbackFn, thisArg)`](#findindexcallbackfn-thisarg)
- [`findLast(callbackFn, thisArg)`](#findlastcallbackfn-thisarg)
- [`findLastIndex(callbackFn, thisArg)`](#findlastindexcallbackfn-thisarg)

---

#### `filter(callbackFn, thisArg)`

Returns a new array with elements that satisfy `callbackFn`.

**Example:**

```js
let arr = [10, 20, 30, 40];

let result = arr.filter((num) => num > 20);
console.log(result); // [30, 40]
```

**Arguments:**

- `callbackFn`: A function called for each element. Should return `true` to keep the element, which takes three arguments:
  - `element`: The current element being processed in the array.
  - `index` (Optional): The index of the current element in the array.
  - `array` (Optional): The array that filter was called on.
- `thisArg` (Optional): Value to use as `this` inside `callbackFn`.

---

#### `find(callbackFn, thisArg)`

Returns the first element that satisfies `callbackFn`, or `undefined` if none match.

**Example:**

```js
let arr = [10, 20, 30, 40];

let result = arr.find((num) => num > 20);
console.log(result); // 30
```

**Arguments:**

- `callbackFn`: A function called for each element. Should return `true` to return the element, which takes three arguments:
  - `element`: The current element being processed in the array.
  - `index` (Optional): The index of the current element in the array.
  - `array` (Optional): The array that filter was called on.
- `thisArg` (Optional): Value to use as `this` inside `callbackFn`.

---

#### `findIndex(callbackFn, thisArg)`

Returns the index of the first element that satisfies `callbackFn`, or `-1` if none match.

**Example:**

```js
let arr = [10, 20, 30, 40];

let result = arr.findIndex((num) => num > 20);
console.log(result); // 2
```

**Arguments:**

- `callbackFn`: A function called for each element. Should return `true` to return the index, which takes three arguments:
  - `element`: The current element being processed in the array.
  - `index` (Optional): The index of the current element in the array.
  - `array` (Optional): The array that filter was called on.
- `thisArg` (Optional): Value to use as `this` inside `callbackFn`.

---

#### `findLast(callbackFn, thisArg)`

Returns the last element that satisfies `callbackFn`, or `undefined` if none match.

**Example:**

```js
let arr = [10, 20, 30, 40];

let result = arr.findLast((num) => num > 20);
console.log(result); // 40
```

**Arguments:**

- `callbackFn`: A function called for each element. Should return `true` to return the element, which takes three arguments:
  - `element`: The current element being processed in the array.
  - `index` (Optional): The index of the current element in the array.
  - `array` (Optional): The array that filter was called on.
- `thisArg` (Optional): Value to use as `this` inside `callbackFn`.

---

#### `findLastIndex(callbackFn, thisArg)`

Returns the index of the last element that satisfies `callbackFn`, or `-1` if none match.

**Example:**

```js
let arr = [10, 20, 30, 40];

let result = arr.findLastIndex((num) => num > 20);
console.log(result); // 3
```

**Arguments:**

- `callbackFn`: A function called for each element. Should return `true` to return the index, which takes three arguments:
  - `element`: The current element being processed in the array.
  - `index` (Optional): The index of the current element in the array.
  - `array` (Optional): The array that filter was called on.
- `thisArg` (Optional): Value to use as `this` inside `callbackFn`.

---

### Adding & Removing Elements

Enable modifying the array by adding or removing elements at the start, middle, or end.

This category includes:

- [`push(elementN)`](#pushelementn)
- [`pop()`](#pop)
- [`shift()`](#shift)
- [`unshift(elementN)`](#unshiftelementn)
- [`splice(start, deleteCount, ...itemN)`](#splicestart-deletecount-itemn)
- [`toSpliced(start, deleteCount, ...itemN)`](#tosplicedstart-deletecount-itemn)

---

#### `push(elementN)`

Adds one or more elements to the end of the array and returns the new length.

**Example:**

```js
let arr = [10, 20];

console.log(arr.push(30, 40)); // 4
console.log(arr); // [10, 20, 30, 40]
```

**Arguments:**

- `elementN`: Elements to add at the end of the array.

---

#### `pop()`

Removes the last element from the array and returns it. Returns `undefined` if the array is empty.

**Example:**

```js
let arr = [10, 20, 30];

console.log(arr.pop()); // 30
console.log(arr); // [10, 20]
```

---

#### `shift()`

Removes the first element from the array and returns it. Returns `undefined` if the array is empty.

**Example:**

```js
let arr = [10, 20, 30];

console.log(arr.shift()); // 10
console.log(arr); // [20, 30]
```

---

#### `unshift(elementN)`

Adds one or more elements to the beginning of the array and returns the new length.

**Example:**

```js
let arr = [20, 30];

console.log(arr.unshift(10)); // 3
console.log(arr); // [10, 20, 30]
```

**Arguments:**

- `elementN`: Elements to add at the beginning of the array.

---

#### `splice(start, deleteCount, ...itemN)`

Modifies the array by removing or replacing elements and returns the removed elements.

**Example:**

```js
let arr = [10, 20, 30, 40];

console.log(arr.splice(1, 2, 50, 60)); // [20, 30]
console.log(arr); // [10, 50, 60, 40]
```

**Arguments:**

- `start`: The index at which to start modifying the array.
- `deleteCount` (Optional): The number of elements to remove. Defaults to `0`.
- `itemN` (Optional): Elements to insert at `start`.

---

#### `toSpliced(start, deleteCount, ...itemN)`

Returns a new array with modifications without changing the original array.

**Example:**

```js
let arr = [10, 20, 30, 40];

let result = arr.toSpliced(1, 2, 50, 60);
console.log(result); // [10, 50, 60, 40]
console.log(arr); // [10, 20, 30, 40]
```

**Arguments:**

- `start`: The index at which to start modifying the array.
- `deleteCount` (Optional): The number of elements to remove. Defaults to `0`.
- `itemN` (Optional): Elements to insert at `start`.

---

### Conditions

Used to determine if all or some elements meet a specified condition.

This category includes:

- [`every(callbackFn, thisArg)`](#everycallbackfn-thisarg)
- [`some(callbackFn, thisArg)`](#somecallbackfn-thisarg)

---

#### `every(callbackFn, thisArg)`

Returns `true` if all elements satisfy `callbackFn`, otherwise returns `false`. Stops checking once it finds a `false` result.

**Example:**

```js
let arr = [10, 20, 30];

console.log(arr.every((num) => num > 5)); // true
console.log(arr.every((num) => num > 15)); // false
```

**Arguments:**

- `callbackFn`: A function called for each element. Should return `true` to keep checking, which takes three arguments:
  - `element`: The current element being processed in the array.
  - `index` (Optional): The index of the current element in the array.
  - `array` (Optional): The array that filter was called on.
- `thisArg` (Optional): Value to use as `this` inside `callbackFn`.

---

#### `some(callbackFn, thisArg)`

Returns `true` if at least one element satisfies `callbackFn`, otherwise returns `false`. Stops checking once it finds a `true` result.

**Example:**

```js
let arr = [10, 20, 30];

console.log(arr.some((num) => num > 25)); // true
console.log(arr.some((num) => num > 40)); // false
```

**Arguments:**

- `callbackFn`: A function called for each element. Should return `true` to stop checking, which takes three arguments:
  - `element`: The current element being processed in the array.
  - `index` (Optional): The index of the current element in the array.
  - `array` (Optional): The array that filter was called on.
- `thisArg` (Optional): Value to use as `this` inside `callbackFn`.

---

### Sorting & Reversing

Provide ways to order elements in ascending or descending order and reverse their sequence.

This category includes:

- [`sort(compareFn)`](#sortcomparefn)
- [`toSorted(compareFn)`](#tosortedcomparefn)
- [`reverse()`](#reverse)
- [`toReversed()`](#toreversed)

---

#### `sort(compareFn)`

Sorts the array in place and returns the sorted array. If `compareFn` is not provided, it sorts elements as strings in ascending order.

**Example:**

```js
let arr = [30, 10, 20];

console.log(arr.sort()); // [10, 20, 30] (default behavior)
console.log(arr.sort((a, b) => b - a)); // [30, 20, 10] (descending order)
```

**Arguments:**

- `compareFn` (Optional): A function that defines the sorting logic. Should return a negative value for ascending order, positive for descending, and zero for equal values.

---

#### `toSorted(compareFn)`

Returns a new sorted array without modifying the original array.

**Example:**

```js
let arr = [30, 10, 20];

let result = arr.toSorted((a, b) => a - b);
console.log(result); // [10, 20, 30]
console.log(arr); // [30, 10, 20] (unchanged)
```

**Arguments:**

- `compareFn` (Optional): A function that defines the sorting logic.

---

#### `reverse()`

Reverses the elements of the array in place and returns the modified array.

**Example:**

```js
let arr = [10, 20, 30];

console.log(arr.reverse()); // [30, 20, 10]
console.log(arr); // [30, 20, 10] (modified)
```

---

#### `toReversed()`

Returns a new array with elements reversed without modifying the original array.

**Example:**

```js
let arr = [10, 20, 30];

let result = arr.toReversed();
console.log(result); // [30, 20, 10]
console.log(arr); // [10, 20, 30] (unchanged)
```

### Reducing

Used for accumulating values from an array into a single result, like sums or averages.

This category includes:

- [`reduce(callbackFn, initialValue)`](#reducecallbackfn-initialvalue)
- [`reduceRight(callbackFn, initialValue)`](#reducerightcallbackfn-initialvalue)

---

#### `reduce(callbackFn, initialValue)`

Applies `callbackFn` to each element, accumulating a single result from left to right.

**Example:**

```js
let arr = [1, 2, 3, 4];

let sum = arr.reduce((acc, num) => acc + num, 0);
console.log(sum); // 10
```

**Arguments:**

- `callbackFn`: A function executed on each element in the array, which takes four arguments:
  - `accumulator`: The accumulated value returned by the last execution of `callbackFn`, or `initialValue` if provided.
  - `currentValue`: The current element being processed in the array.
  - `index` (Optional): The index of the current element being processed.
  - `array` (Optional): The array `reduce` was called on.
- `initialValue` (Optional): The initial value to start the accumulation. If omitted, the first element of the array will be used as the initial value and the iteration will start from the second element.

---

#### `reduceRight(callbackFn, initialValue)`

Works like `reduce` but processes elements from right to left.

**Example:**

```js
let arr = ["a", "b", "c"];

let result = arr.reduceRight((acc, char) => acc + char, "");
console.log(result); // "cba"
```

**Arguments:**

- `callbackFn`: A function executed on each element in the array, which takes four arguments:
  - `accumulator`: The accumulated value returned by the last execution of `callbackFn`, or `initialValue` if provided.
  - `currentValue`: The current element being processed in the array.
  - `index` (Optional): The index of the current element being processed.
  - `array` (Optional): The array `reduceRight` was called on.
- `initialValue` (Optional): The initial value to start the accumulation. If omitted, the first element of the array will be used as the initial value and the iteration will start from the second element.

---

### Extracting & Slicing

Provide ways to extract portions of an array without modifying the original.

This category includes:

- [`slice(start, end)`](#slicestart-end)

---

#### `slice(start, end)`

Returns a new array containing elements from `start` up to (but not including) `end`, without modifying the original array.

**Example:**

```js
let arr = [10, 20, 30, 40, 50];

console.log(arr.slice(1, 4)); // [20, 30, 40]
console.log(arr.slice(2)); // [30, 40, 50]
console.log(arr.slice(-3)); // [30, 40, 50]
console.log(arr); // [10, 20, 30, 40, 50] (unchanged)
```

**Arguments:**

- `start`: The index to begin slicing. Defaults to `0`.
- `end` (Optional): The index to stop slicing (not included). Defaults to the array length.

---

### Copying & Modifying

Allow duplicating and modifying elements within an array without adding or removing anything.

This category includes:

- [`copyWithin(target, start, end)`](#copywithintarget-start-end)
- [`fill(value, start, end)`](#fillvalue-start-end)

---

#### `copyWithin(target, start, end)`

Copies a sequence of elements within the array to another position, overwriting existing values. Modifies the original array.

**Example:**

```js
let arr = [10, 20, 30, 40, 50];

console.log(arr.copyWithin(1, 3)); // [10, 40, 50, 40, 50]
console.log(arr); // [10, 40, 50, 40, 50] (modified)
```

**Arguments:**

- `target`: The index where copied elements will be placed.
- `start`: The index to start copying from.
- `end` (Optional): The index to stop copying (not included). Defaults to the array length.

---

#### `fill(value, start, end)`

Replaces all elements in a specified range with `value`. Modifies the original array.

**Example:**

```js
let arr = [1, 2, 3, 4, 5];

console.log(arr.fill(0, 1, 4)); // [1, 0, 0, 0, 5]
console.log(arr); // [1, 0, 0, 0, 5] (modified)
```

**Arguments:**

- `value`: The value to fill the array with.
- `start` (Optional): The index to begin filling. Defaults to `0`.
- `end` (Optional): The index to stop filling (not included). Defaults to the array length.

---

### Creation & Combination

These functions help in creating new arrays by merging, flattening, or modifying existing ones.

This category includes:

- [`concat(arrN)`](#concatarrn)
- [`flat(depth)`](#flatdepth)
- [`flatMap(callbackFn, thisArg)`](#flatmapcallbackfn-thisarg)
- [`with(index, value)`](#withindex-value)

---

#### `concat(arrN)`

Returns a new array by merging the original array with one or more provided arrays or values.

**Example:**

```js
let arr = [1, 2, 3];

console.log(arr.concat([4, 5], 6)); // [1, 2, 3, 4, 5, 6]
console.log(arr); // [1, 2, 3] (unchanged)
```

**Arguments:**

- `arrN`: One or more arrays or values to merge with the original array.

---

#### `flat(depth)`

Returns a new array with sub-arrays flattened up to the specified `depth`.

**Example:**

```js
let arr = [1, [2, [3, [4]]]];

console.log(arr.flat(2)); // [1, 2, 3, [4]]
console.log(arr.flat()); // [1, 2, [3, [4]]] (default depth = 1)
```

**Arguments:**

- `depth` (Optional): The level of nested arrays to flatten. Defaults to `1`.

---

#### `flatMap(callbackFn, thisArg)`

Maps each element using `callbackFn` and flattens the result into a new array.

**Example:**

```js
let arr = [1, 2, 3];

console.log(arr.flatMap((num) => [num, num * 2])); // [1, 2, 2, 4, 3, 6]
```

**Arguments:**

- `callbackFn`: A function called for each element. Should return an array or value, which takes three arguments:
  - `element`: The current element being processed.
  - `index` (Optional): The index of the current element. Defaults to `0`.
  - `array` (Optional): The array that `flatMap` was called on.
- `thisArg` (Optional): Value to use as `this` inside `callbackFn`.

---

#### `with(index, value)`

Returns a new array with the element at `index` replaced by `value`, without modifying the original array.

**Example:**

```js
let arr = [10, 20, 30];

console.log(arr.with(1, 99)); // [10, 99, 30]
console.log(arr); // [10, 20, 30] (unchanged)
```

**Arguments:**

- `index`: The position of the element to replace.
- `value`: The new value to insert at `index`.

---

### String Conversion

Convert arrays into strings, either directly or with specific formatting.

This category includes:

- [`toString()`](#tostring)
- [`toLocaleString(locales, options)`](#tolocalestringlocales-options)
- [`join(separator)`](#joinseparator)

---

#### `toString()`

Returns a string representation of the array, where elements are separated by commas.

**Example:**

```js
let arr = [10, 20, 30];

console.log(arr.toString()); // "10,20,30"
```

---

#### `toLocaleString(locales, options)`

Returns a localized string representation of the array, formatting elements based on the given locale and options.

**Example:**

```js
let arr = [1000, new Date("2023-01-01")];

console.log(arr.toLocaleString("en-US")); // "1,000, 1/1/2023, 12:00:00 AM"
console.log(arr.toLocaleString("de-DE")); // "1.000, 1.1.2023, 00:00:00"
```

**Arguments:**

- `locales` (Optional): A string or array of locale codes (e.g., `"en-US"`). Defaults to the system's locale.
- `options` (Optional): An object specifying formatting options.

---

#### `join(separator)`

Returns a string where array elements are joined by `separator`.

**Example:**

```js
let arr = ["apple", "banana", "cherry"];

console.log(arr.join(" - ")); // "apple - banana - cherry"
console.log(arr.join()); // "apple,banana,cherry" (default separator is ",")
```

**Arguments:**

- `separator` (Optional): The string to place between elements. Defaults to `","`.

---

### Iteration & Transformation

Return iterable objects that allow traversing an array’s elements with key-value pairs.

This category includes:

- [`map(callbackFn, thisArg)`](#mapcallbackfn-thisarg)
- [`forEach(callbackFn, thisArg)`](#foreachcallbackfn-thisarg)
- [`entries()`](#entries)

---

#### `map(callbackFn, thisArg)`

Creates a new array by applying `callbackFn` to each element of the original array.
This category includes:
**Example:**

```js
let arr = [1, 2, 3];

console.log(arr.map((num) => num * 2)); // [2, 4, 6]
console.log(arr); // [1, 2, 3] (unchanged)
```

**Arguments:**

- `callbackFn`: A function called for each element, which takes three arguments:
  - `element`: The current element being processed.
  - `index` (Optional): The index of the current element. Defaults to `0`.
  - `array` (Optional): The array that `map` was called on.
- `thisArg` (Optional): Value to use as `this` inside `callbackFn`.

---

#### `forEach(callbackFn, thisArg)`

Executes `callbackFn` for each array element but does not return a new array.

**Example:**

```js
let arr = ["a", "b", "c"];

arr.forEach((char, index) => console.log(index, char));
// 0 "a"
// 1 "b"
// 2 "c"
```

**Arguments:**

- `callbackFn`: A function called for each element, which takes three arguments:
  - `element`: The current element being processed.
  - `index` (Optional): The index of the current element. Defaults to `0`.
  - `array` (Optional): The array that `forEach` was called on.
- `thisArg` (Optional): Value to use as `this` inside `callbackFn`.

---

#### `entries()`

Returns an iterator containing key-value pairs of the array, where the key is the index and the value is the element.

**Example:**

```js
let arr = ["x", "y", "z"];

for (let [index, value] of arr.entries()) {
  console.log(index, value);
}
// 0 "x"
// 1 "y"
// 2 "z"
```

---

## Instance Properties

### `length`

Represents the number of elements in the array. Can be used to get or set the array's length.

**Example (Getting the length):**

```js
let arr = [10, 20, 30];

console.log(arr.length); // 3
```

**Example (Setting the length):**

```js
let arr = [1, 2, 3, 4, 5];

arr.length = 3;
console.log(arr); // [1, 2, 3] (truncated)

arr.length = 6;
console.log(arr); // [1, 2, 3, <3 empty slots>]
```
