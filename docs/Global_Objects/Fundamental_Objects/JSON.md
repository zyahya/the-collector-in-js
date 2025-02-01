# JSON

The `JSON` object in JavaScript provides methods for parsing and serializing data in JavaScript Object Notation (JSON) format. It enables easy conversion between JSON strings and JavaScript objects.

## Static Methods

- [`JSON.isRawJSON(jsonString)`](#jsonisrawjsonjsonstring)
- [`JSON.parse(text, reviver)`](#jsonparsetext-reviver)
- [`JSON.rawJSON(obj)`](#jsonrawjsonobj)
- [`JSON.stringify(value, replacer, space)`](#jsonstringifyvalue-replacer-space)

### `JSON.isRawJSON(jsonString)`

Checks if the provided string is valid raw JSON. Returns `true` if the string is valid JSON, otherwise `false`.

**Example:**

```js
let validJson = '{"name": "John", "age": 30}';
let invalidJson = "{name: John, age: 30}";

console.log(JSON.isRawJSON(validJson)); // true
console.log(JSON.isRawJSON(invalidJson)); // false
```

**Arguments:**

- `jsonString`: The string to check if it is valid JSON.

---

### `JSON.parse(text, reviver)`

Parses a JSON string, constructing the JavaScript value or object described by the string. Optionally, you can provide a `reviver` function to transform the parsed values.

**Example:**

```js
let jsonString = '{"name": "John", "age": 30}';
let parsedObject = JSON.parse(jsonString);

console.log(parsedObject); // { name: 'John', age: 30 }
```

**Arguments:**

- `text`: The JSON string to parse.
- `reviver` (Optional): A function that can modify the parsed object before it is returned.

---

### `JSON.rawJSON(obj)`

Converts a JavaScript object into a raw JSON string. This function is typically used for custom serialization, where you don't want the object to be transformed.

**Example:**

```js
let obj = { name: "John", age: 30 };
let rawJson = JSON.rawJSON(obj);

console.log(rawJson); // '{"name":"John","age":30}'
```

**Arguments:**

- `obj`: The object to convert to raw JSON string.

---

### `JSON.stringify(value, replacer, space)`

Converts a JavaScript value to a JSON string. You can optionally specify a `replacer` function to control the serialization of specific values, and `space` to add indentation for readability.

**Example:**

```js
let obj = { name: "John", age: 30 };
let jsonString = JSON.stringify(obj, null, 2);

console.log(jsonString);
// {
//   "name": "John",
//   "age": 30
// }
```

**Arguments:**

- `value`: The value to convert into a JSON string.
- `replacer` (Optional): A function or array to transform the result before stringifying.
- `space` (Optional): A number or string used for indentation. If provided, it pretty-prints the output.
