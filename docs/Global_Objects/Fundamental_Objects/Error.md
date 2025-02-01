# Error

The `Error` object in JavaScript represents an error that occurs during the execution of code. It serves as the base constructor for various error types, such as `SyntaxError`, `TypeError`, and `ReferenceError`, and provides properties for debugging and error handling.

## `Error(message)` Constructor

The `Error()` constructor is used to create error objects. These objects represent runtime errors and help with debugging by providing a message and a stack trace.

```js
const error = new Error("Something went wrong!");
console.log(error.name); // "Error"
console.log(error.message); // "Something went wrong!"
console.log(error.stack); // Stack trace (useful for debugging)
```

**Arguments:**

- `message` (Optional): A string describing the error.
