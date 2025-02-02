# String

The `String` object in JavaScript represents a sequence of characters. It provides a variety of methods and properties for manipulating and inspecting strings.

- [String](#string)
  - [Static Methods](#static-methods)
    - [`String.raw(templateString)`](#stringrawtemplatestring)
    - [`String.fromCharCode(...numN)`](#stringfromcharcodenumn)
    - [`String.fromCodePoint(args)`](#stringfromcodepointargs)
  - [Instance Methods](#instance-methods)
    - [Character Access and Manipulation](#character-access-and-manipulation)
      - [`at(index)`](#atindex)
      - [`charAt(index)`](#charatindex)
      - [`charCodeAt(index)`](#charcodeatindex)
      - [`codePointAt(index)`](#codepointatindex)
    - [Searching and Matching](#searching-and-matching)
      - [`startsWith(searchString, endPosition)`](#startswithsearchstring-endposition)
      - [`endsWith(searchString, endPosition)`](#endswithsearchstring-endposition)
      - [`includes(searchString, position)`](#includessearchstring-position)
      - [`search(regexp)`](#searchregexp)
      - [`indexOf(searchString, position)`](#indexofsearchstring-position)
      - [`lastIndexOf(searchString, position)`](#lastindexofsearchstring-position)
      - [`match(regexp)`](#matchregexp)
      - [`matchAll(regexp)`](#matchallregexp)
    - [Extraction and Splitting](#extraction-and-splitting)
      - [`slice(indexStart, indexEnd)`](#sliceindexstart-indexend)
      - [`substring(indexStart, indexEnd)`](#substringindexstart-indexend)
      - [`split(separator, limit)`](#splitseparator-limit)
    - [Case Conversion](#case-conversion)
      - [`toLowerCase()`](#tolowercase)
      - [`toUpperCase()`](#touppercase)
      - [`toLocaleUpperCase(locales)`](#tolocaleuppercaselocales)
      - [`toLocaleLowerCase(locales)`](#tolocalelowercaselocales)
    - [Padding](#padding)
      - [`padStart(targetLength, padString)`](#padstarttargetlength-padstring)
      - [`padEnd(targetLength, padString)`](#padendtargetlength-padstring)
    - [Replacement](#replacement)
      - [`replace(regex, replacement)`](#replaceregex-replacement)
      - [`replaceAll(regex, replacement)`](#replaceallregex-replacement)
    - [Concatenation](#concatenation)
      - [`concat(strN)`](#concatstrn)
    - [Whitespace Handling](#whitespace-handling)
      - [`trim()`](#trim)
      - [`trimStart()`](#trimstart)
      - [`trimEnd()`](#trimend)
    - [Repetition and Normalization](#repetition-and-normalization)
      - [`repeat(count)`](#repeatcount)
      - [`isWellFormed()`](#iswellformed)
      - [`toWellFormed()`](#towellformed)
      - [`normalize(form)`](#normalizeform)
    - [String Conversion and Representation](#string-conversion-and-representation)
      - [`valueOf()`](#valueof)
      - [`toString()`](#tostring)
  - [Instance Properties](#instance-properties)
    - [`length`](#length)

## Static Methods

### `String.raw(templateString)`

Returns a raw string from a template literal, escaping any special characters (like backslashes) in the template literal as-is.

**Example:**

```js
let str = String.raw`C:\Path\to\net.conf`;

console.log(str); // "C:\Path\to\net.conf"
```

**Arguments:**

- `templateString`: A template literal passed to the method, typically containing escape sequences like `\t` or `\n`.

---

### `String.fromCharCode(...numN)`

Returns a string created from one or more Unicode values, where each number represents a UTF-16 code unit.

**Example:**

```js
console.log(String.fromCharCode(65, 66, 67)); // "ABC"
console.log(String.fromCharCode(128512)); // "😀"
```

**Arguments:**

- `numN`: One or more numbers representing UTF-16 code units.

---

### `String.fromCodePoint(args)`

Returns a string created from one or more Unicode code points. This method supports characters outside the Basic Multilingual Plane (BMP), which may require surrogate pairs.

**Example:**

```js
console.log(String.fromCodePoint(65, 66, 67)); // "ABC"
console.log(String.fromCodePoint(128512)); // "😀"
console.log(String.fromCodePoint(0x1f600)); // "😀"
```

**Arguments:**

- `args`: One or more Unicode code points, which can be outside the BMP.

---

## Instance Methods

### Character Access and Manipulation

These methods allow you to access specific characters or code points and manipulate characters.

---

#### `at(index)`

Returns the character at a given index, allowing negative indices for counting from the end.

**Example:**

```js
let str = "hello";

console.log(str.at(1)); // "e"
console.log(str.at(-1)); // "o"
console.log(str.at(10)); // undefined
```

**Arguments:**

- `index`: The position of the character to return, can be negative.

---

#### `charAt(index)`

Returns the character at a specified index. Unlike `at()`, it does not support negative indices.

**Example:**

```js
let str = "hello";

console.log(str.charAt(1)); // "e"
console.log(str.charAt(10)); // ""
```

**Arguments:**

- `index` (Optional): The position of the character to return. Defaults to `0`.

---

#### `charCodeAt(index)`

Returns the UTF-16 code unit of the character at a given index.

**Example:**

```js
let str = "ABC";

console.log(str.charCodeAt(0)); // 65
console.log(str.charCodeAt(1)); // 66
console.log(str.charCodeAt(10)); // NaN
```

**Arguments:**

- `index` (Optional): The position of the character to retrieve its code. Defaults to `0`.

---

#### `codePointAt(index)`

Returns the Unicode code point of the character at a given index, supporting surrogate pairs.

**Example:**

```js
let str = "𝒜BC";

console.log(str.codePointAt(0)); // 119964 (𝒜)
console.log(str.codePointAt(1)); // 66 (B)
```

**Arguments:**

- `index` (Optional): The position of the character to retrieve its code point. Defaults to `0`.

---

### Searching and Matching

Methods for checking if a string contains certain substrings or matches patterns.

---

#### `startsWith(searchString, endPosition)`

Checks if a string starts with a given substring. Returns `true` if it does, otherwise returns `false`.

**Example:**

```js
let str = "Hello, world!";

console.log(str.startsWith("Hello")); // true
console.log(str.startsWith("world")); // false
console.log(str.startsWith("Hello", 1)); // false
```

**Arguments:**

- `searchString`: The substring to check for at the start of the string. (Required)
- `endPosition` (Optional): The position in the string where the search should stop. Defaults to `0`.

---

#### `endsWith(searchString, endPosition)`

Checks if a string ends with a given substring. Returns `true` if it does, otherwise returns `false`.

**Example:**

```js
let str = "Hello, world!";

console.log(str.endsWith("world!")); // true
console.log(str.endsWith("Hello")); // false
console.log(str.endsWith("world", 12)); // true
```

**Arguments:**

- `searchString`: The substring to check for at the end of the string.
- `endPosition` (Optional): The length of the string to consider. Defaults to the full length of the string.

---

#### `includes(searchString, position)`

Checks if a string contains a given substring. Returns `true` if it does, otherwise returns `false`.

**Example:**

```js
let str = "Hello, world!";

console.log(str.includes("world")); // true
console.log(str.includes("Hello", 1)); // false
console.log(str.includes("o", 5)); // true
```

**Arguments:**

- `searchString`: The substring to search for. (Required)
- `position` (Optional): The index to start searching from. Defaults to `0`.

---

#### `search(regexp)`

Finds the first match of a regular expression in the string and returns the index of the match, or `-1` if no match is found.

**Example:**

```js
let str = "some string";

console.log(str.search(/str/)); // 5
console.log(str.search("ring")); // 7
console.log(str.search("wiki")); // -1
```

**Arguments:**

- `regexp`: The pattern to search for, either as a string or a regular expression.

---

#### `indexOf(searchString, position)`

Returns the index of the first occurrence of a substring, or `-1` if not found.

**Example:**

```js
let str = "hello world";

console.log(str.indexOf("o")); // 4
console.log(str.indexOf("world")); // 6
console.log(str.indexOf("o", 5)); // 7
```

**Arguments:**

- `searchString`: The substring to search for.
- `position` (Optional): The index to start searching from. Defaults to `0`.

---

#### `lastIndexOf(searchString, position)`

Returns the index of the last occurrence of a substring, or `-1` if not found.

**Example:**

```js
let str = "hello world";

console.log(str.lastIndexOf("o")); // 7
console.log(str.lastIndexOf("world")); // 6
console.log(str.lastIndexOf("o", 6)); // 4
```

**Arguments:**

- `searchString`: The substring to search for.
- `position` (Optional): The index to start searching backward from. Defaults to the string's full length.

---

#### `match(regexp)`

Finds matches for a regular expression and returns an array of matches or `null` if none are found.

**Example:**

```js
let str = "Hello 123, hello 456";

console.log(str.match(/\d+/g)); // ["123", "456"]
console.log(str.match(/hello/i)); // ["Hello", index: 0, ...]
console.log(str.match(/xyz/)); // null
```

**Arguments:**

- `regexp`: A regular expression to match against the string.

---

#### `matchAll(regexp)`

Returns an iterator for all matches of a regular expression in a string.

**Example:**

```js
let str = "Hello 123, hello 456";
let matches = str.matchAll(/\d+/g);

console.log([...matches]); // [["123"], ["456"]]
```

**Arguments:**

- `regexp`: A global regular expression (`/g` flag is required).

---

### Extraction and Splitting

Methods for extracting or splitting parts of the string.

---

#### `slice(indexStart, indexEnd)`

Extracts a section of a string and returns a new string without modifying the original.

**Example:**

```js
let str = "Hello, world!";

console.log(str.slice(7)); // "world!"
console.log(str.slice(0, 5)); // "Hello"
console.log(str.slice(-6)); // "world!"
```

**Arguments:**

- `indexStart`: The start index of the extraction.
- `indexEnd` (Optional): The index before which to stop extraction. Defaults to the end of the string.

---

#### `substring(indexStart, indexEnd)`

Extracts a portion of a string and returns it as a new string, swapping indices if `indexStart` is greater than `indexEnd`.

**Example:**

```js
let str = "Hello, world!";

console.log(str.substring(7)); // "world!"
console.log(str.substring(0, 5)); // "Hello"
console.log(str.substring(5, 0)); // "Hello"
```

**Arguments:**

- `indexStart`: The start index of the extraction.
- `indexEnd` (Optional): The index before which to stop extraction. Defaults to the end of the string.

---

#### `split(separator, limit)`

Splits a string into an array of substrings based on a given separator.

**Example:**

```js
let str = "apple,banana,cherry";

console.log(str.split(",")); // ["apple", "banana", "cherry"]
console.log(str.split(",", 2)); // ["apple", "banana"]
console.log(str.split("")); // ["a", "p", "p", "l", "e", ",", "b", "a", "n", "a", "n", "a", ",", "c", "h", "e", "r", "r", "y"]
```

**Arguments:**

- `separator`: A string or regular expression used to split the string.
- `limit` (Optional): The maximum number of splits to include in the array.

---

### Case Conversion

Methods for converting string characters to different cases or locale-specific variations.

---

#### `toLowerCase()`

Converts all characters in a string to lowercase and returns a new string.

**Example:**

```js
let str = "Hello World";

console.log(str.toLowerCase()); // "hello world"
```

---

#### `toUpperCase()`

Converts all characters in a string to uppercase and returns a new string.

**Example:**

```js
let str = "Hello World";

console.log(str.toUpperCase()); // "HELLO WORLD"
```

---

#### `toLocaleUpperCase(locales)`

Converts the string to uppercase using locale-specific rules and returns a new string.

**Example:**

```js
let str = "i";

console.log(str.toLocaleUpperCase("tr")); // "İ"
console.log(str.toLocaleUpperCase("en")); // "I"
```

**Arguments:**

- `locales` (Optional): A string or array of locale identifiers affecting case conversion. Defaults to the environment’s locale.

---

#### `toLocaleLowerCase(locales)`

Converts the string to lowercase using locale-specific rules and returns a new string.

**Example:**

```js
let str = "İ";

console.log(str.toLocaleLowerCase("tr")); // "i"
console.log(str.toLocaleLowerCase("en")); // "i"
```

**Arguments:**

- `locales` (Optional): A string or array of locale identifiers affecting case conversion. Defaults to the environment’s locale.

---

### Padding

Methods for padding strings to a certain length by adding characters.

---

#### `padStart(targetLength, padString)`

Pads the current string with another string (or spaces by default) at the beginning until it reaches the specified length.

**Example:**

```js
let str = "42";

console.log(str.padStart(5, "0")); // "00042"
console.log(str.padStart(5)); // "   42"
```

**Arguments:**

- `targetLength`: The length of the resulting string after padding.
- `padString` (Optional): The string used for padding. Defaults to a space.

---

#### `padEnd(targetLength, padString)`

Pads the current string with another string (or spaces by default) at the end until it reaches the specified length.

**Example:**

```js
let str = "42";

console.log(str.padEnd(5, "0")); // "42000"
console.log(str.padEnd(5)); // "42   "
```

**Arguments:**

- `targetLength`: The length of the resulting string after padding.
- `padString` (Optional): The string used for padding. Defaults to a space.

---

### Replacement

Methods for replace existing values in a string, with the new value you will provide.

---

#### `replace(regex, replacement)`

Replaces the first match of a given substring or regular expression with a new string.

**Example:**

```js
let str = "hello world";

console.log(str.replace("world", "there")); // "hello there"
console.log(str.replace(/o/, "O")); // "hellO world"
```

**Arguments:**

- `regex`: A string or regular expression to be replaced.
- `replacement`: The new string to replace the match with.

---

#### `replaceAll(regex, replacement)`

Replaces all occurrences of a given substring or regular expression with a new string.

**Example:**

```js
let str = "hello world, world!";

console.log(str.replaceAll("world", "there")); // "hello there, there!"
console.log(str.replaceAll(/o/g, "O")); // "hellO wOrld, wOrld!"
```

**Arguments:**

- `regex`: A string or regular expression to be replaced.
- `replacement`: The new string to replace the matches with.

---

### Concatenation

#### `concat(strN)`

Concatenates one or more strings and returns a new string.

**Example:**

```js
let str = "Hello";

console.log(str.concat(" ", "World", "!")); // "Hello World!"
```

**Arguments:**

- `strN`: One or more strings to concatenate.

---

### Whitespace Handling

These methods focus on trimming and adjusting the spaces around or inside the string.

---

#### `trim()`

Removes whitespace from both ends of a string and returns a new string.

**Example:**

```js
let str = "  hello  ";

console.log(str.trim()); // "hello"
```

---

#### `trimStart()`

Removes whitespace from the beginning of a string and returns a new string.

**Example:**

```js
let str = "  hello  ";

console.log(str.trimStart()); // "hello  "
```

An alternative to `trimStart()` do the same behavior is `trimLeft()`.

---

#### `trimEnd()`

Removes whitespace from the end of a string and returns a new string.

**Example:**

```js
let str = "  hello  ";

console.log(str.trimEnd()); // "  hello"
```

An alternative to `trimEnd()` do the same behavior is `trimRight()`.

---

### Repetition and Normalization

Methods related to repeating strings or ensuring proper encoding.

---

#### `repeat(count)`

Returns a new string containing the original string repeated `count` times.

**Example:**

```js
let str = "ha";

console.log(str.repeat(3)); // "hahaha"
console.log(str.repeat(0)); // ""
```

**Arguments:**

- `count`: The number of times to repeat the string. Must be a non-negative integer.

---

#### `isWellFormed()`

Checks if the string is well-formed, meaning it doesn’t contain lone surrogate code units. Returns `true` if well-formed, otherwise `false`.

**Example:**

```js
let str1 = "hello";
let str2 = "ab\uD800"; // Lone surrogate

console.log(str1.isWellFormed()); // true
console.log(str2.isWellFormed()); // false
```

---

#### `toWellFormed()`

Returns a well-formed version of the string by replacing lone surrogates with the Unicode replacement character `�`.

**Example:**

```js
let str = "ab\uD800"; // Lone surrogate

console.log(str.toWellFormed()); // "ab�"
```

---

#### `normalize(form)`

Returns a Unicode-normalized form of the string.

**Example:**

```js
let str = "\u1E9B\u0323"; // "ẛ̣" (ẛ + dot below)

console.log(str.normalize("NFC")); // "ṩ" (single character)
console.log(str.normalize("NFD")); // "ẛ̣"
```

**Arguments:**

- `form` (Optional): The normalization form, one of `"NFC"`, `"NFD"`, `"NFKC"`, or `"NFKD"`. Defaults to `"NFC"`.

---

### String Conversion and Representation

Methods for converting the string to different formats or representations.

---

#### `valueOf()`

Returns the primitive string value of a `String` object.

**Example:**

```js
let strObj = new String("hello");

console.log(strObj.valueOf()); // "hello"
```

---

#### `toString()`

Returns the string representation of a given string object or other data types like numbers and arrays.

**Example:**

```js
let str = new String("hello");
let arr = [1, 2, 3];
let num = 2025;

console.log(str.toString()); // "hello"
console.log(arr.toString()); // 1,2,3
console.log(num.toString()); // "2025"
```

---

## Instance Properties

### `length`

Let you know how many characters in the string

**Example:**

```js
let str = "Hello";

console.log(str.length); // 5
console.log("😊".length); // 2 (because it's a surrogate pair)
```
