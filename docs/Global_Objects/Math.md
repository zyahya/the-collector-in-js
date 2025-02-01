# Math

The `Math` object in JavaScript provides a collection of properties and methods for performing mathematical operations and calculations. It includes functions for trigonometry, logarithms, rounding, and generating random numbers.

## Static Properties

### Basic Arithmetic and Number Manipulation

Functions that perform basic arithmetic operations or manipulate numbers in simple ways.

This category includes:

- [`Math.abs(x)`](#mathabsx)
- [`Math.ceil(x)`](#mathceilx)
- [`Math.floor(x)`](#mathfloorx)
- [`Math.round(x)`](#mathroundx)
- [`Math.trunc(x)`](#mathtruncx)
- [`Math.sign(x)`](#mathsignx)
- [`Math.max(...args)`](#mathmaxargs)
- [`Math.min(...args)`](#mathminargs)
- [`Math.pow(x, y)`](#mathpowx-y)
- [`Math.sqrt(x)`](#mathsqrtx)
- [`Math.cbrt(x)`](#mathcbrtx)
- [`Math.hypot(...args)`](#mathhypotargs)
- [`Math.imul(x, y)`](#mathimulx-y)

---

#### `Math.abs(x)`

Returns the absolute value of a number, which is its distance from zero on the number line. The return value is always non-negative.

**Example:**

```js
console.log(Math.abs(-5)); // 5
console.log(Math.abs(3.14)); // 3.14
```

**Arguments:**

- `x`: A number for which the absolute value is calculated.

---

#### `Math.ceil(x)`

Returns the smallest integer greater than or equal to a number.

**Example:**

```js
console.log(Math.ceil(1.2)); // 2
console.log(Math.ceil(-1.2)); // -1
```

**Arguments:**

- `x`: A number.

---

#### `Math.floor(x)`

Returns the largest integer less than or equal to a number.

**Example:**

```js
console.log(Math.floor(1.8)); // 1
console.log(Math.floor(-1.8)); // -2
```

**Arguments:**

- `x`: A number.

---

#### `Math.round(x)`

Returns the value of a number rounded to the nearest integer.

**Example:**

```js
console.log(Math.round(1.4)); // 1
console.log(Math.round(1.6)); // 2
```

**Arguments:**

- `x`: A number.

---

#### `Math.trunc(x)`

Returns the integer part of a number by removing any fractional digits.

**Example:**

```js
console.log(Math.trunc(1.7)); // 1
console.log(Math.trunc(-1.7)); // -1
```

**Arguments:**

- `x`: A number.

---

#### `Math.sign(x)`

Returns the sign of a number: `1` for positive, `-1` for negative, or `0`/`-0` for zero.

**Example:**

```js
console.log(Math.sign(5)); // 1
console.log(Math.sign(-5)); // -1
```

**Arguments:**

- `x`: A number.

---

#### `Math.max(...args)`

Returns the largest of zero or more numbers.

**Example:**

```js
console.log(Math.max(1, 2, 3)); // 3
console.log(Math.max(-1, -2, -3)); // -1
```

**Arguments:**

- `...args`: A list of numbers.

---

#### `Math.min(...args)`

Returns the smallest of zero or more numbers.

**Example:**

```js
console.log(Math.min(1, 2, 3)); // 1
console.log(Math.min(-1, -2, -3)); // -3
```

**Arguments:**

- `...args`: A list of numbers.

---

#### `Math.pow(x, y)`

Returns `x` raised to the power of `y`.

**Example:**

```js
console.log(Math.pow(2, 3)); // 8
console.log(Math.pow(4, 0.5)); // 2
```

**Arguments:**

- `x`: The base number.
- `y`: The exponent.

---

#### `Math.sqrt(x)`

Returns the square root of a number.

**Example:**

```js
console.log(Math.sqrt(4)); // 2
console.log(Math.sqrt(-1)); // NaN
```

**Arguments:**

- `x`: A non-negative number.

---

#### `Math.cbrt(x)`

Returns the cube root of a number.

**Example:**

```js
console.log(Math.cbrt(27)); // 3
console.log(Math.cbrt(-8)); // -2
```

**Arguments:**

- `x`: A number.

---

#### `Math.hypot(...args)`

Returns the square root of the sum of squares of its arguments.

**Example:**

```js
console.log(Math.hypot(3, 4)); // 5
console.log(Math.hypot(1, 1, 1)); // 1.7320508075688772
```

**Arguments:**

- `...args`: A list of numbers.

---

#### `Math.imul(x, y)`

Returns the result of a 32-bit integer multiplication of two numbers.

**Example:**

```js
console.log(Math.imul(2, 4)); // 8
console.log(Math.imul(0xffffffff, 5)); // -5
```

**Arguments:**

- `x`: A number.
- `y`: A number.

---

### Trigonometric Functions

Functions that perform trigonometric calculations, including inverse and hyperbolic variants.

This category includes:

- [`Math.sin(x)`](#mathsinx)
- [`Math.cos(x)`](#mathcosx)
- [`Math.tan(x)`](#mathtanx)
- [`Math.asin(x)`](#mathasinx)
- [`Math.acos(x)`](#mathacosx)
- [`Math.atan(x)`](#mathatanx)
- [`Math.atan2(y, x)`](#mathatan2y-x)
- [`Math.sinh(x)`](#mathsinhx)
- [`Math.cosh(x)`](#mathcoshx)
- [`Math.tanh(x)`](#mathtanhx)
- [`Math.asinh(x)`](#mathasinhx)
- [`Math.acosh(x)`](#mathacoshx)
- [`Math.atanh(x)`](#mathatanhx)

---

#### `Math.sin(x)`

Returns the sine of an angle (in radians).

**Example:**

```js
console.log(Math.sin(0)); // 0
console.log(Math.sin(Math.PI / 2)); // 1
```

**Arguments:**

- `x`: A number representing an angle in radians.

---

#### `Math.cos(x)`

Returns the cosine of an angle (in radians).

**Example:**

```js
console.log(Math.cos(0)); // 1
console.log(Math.cos(Math.PI)); // -1
```

**Arguments:**

- `x`: A number representing an angle in radians.

---

#### `Math.tan(x)`

Returns the tangent of an angle (in radians).

**Example:**

```js
console.log(Math.tan(0)); // 0
console.log(Math.tan(Math.PI / 4)); // 1
```

**Arguments:**

- `x`: A number representing an angle in radians.

---

#### `Math.asin(x)`

Returns the arcsine (in radians) of a number between -1 and 1. If the input is outside this range, it returns `NaN`.

**Example:**

```js
console.log(Math.asin(0.5)); // 0.5235987755982989
console.log(Math.asin(2)); // NaN
```

**Arguments:**

- `x`: A number between -1 and 1.

---

#### `Math.acos(x)`

Returns the arccosine (in radians) of a number between -1 and 1. If the input is outside this range, it returns `NaN`.

**Example:**

```js
console.log(Math.acos(0.5)); // 1.0471975511965979
console.log(Math.acos(2)); // NaN
```

**Arguments:**

- `x`: A number between -1 and 1.

---

#### `Math.atan(x)`

Returns the arctangent (in radians) of a number.

**Example:**

```js
console.log(Math.atan(1)); // 0.7853981633974483
console.log(Math.atan(0)); // 0
```

**Arguments:**

- `x`: A number.

---

#### `Math.atan2(y, x)`

Returns the arctangent of the quotient of its arguments, representing the angle between the positive x-axis and the point (x, y).

**Example:**

```js
console.log(Math.atan2(1, 1)); // 0.7853981633974483
console.log(Math.atan2(-1, -1)); // -2.356194490192345
```

**Arguments:**

- `y`: The y-coordinate.
- `x`: The x-coordinate.

---

#### `Math.sinh(x)`

Returns the hyperbolic sine of a number.

**Example:**

```js
console.log(Math.sinh(0)); // 0
console.log(Math.sinh(1)); // 1.1752011936438014
```

**Arguments:**

- `x`: A number.

---

#### `Math.cosh(x)`

Returns the hyperbolic cosine of a number.

**Example:**

```js
console.log(Math.cosh(0)); // 1
console.log(Math.cosh(1)); // 1.5430806348152437
```

**Arguments:**

- `x`: A number.

---

#### `Math.tanh(x)`

Returns the hyperbolic tangent of a number.

**Example:**

```js
console.log(Math.tanh(0)); // 0
console.log(Math.tanh(1)); // 0.7615941559557649
```

**Arguments:**

- `x`: A number.

---

#### `Math.asinh(x)`

Returns the hyperbolic arcsine of a number.

**Example:**

```js
console.log(Math.asinh(1)); // 0.881373587019543
console.log(Math.asinh(-1)); // -0.881373587019543
```

**Arguments:**

- `x`: A number.

---

#### `Math.acosh(x)`

Returns the hyperbolic arccosine of a number. The input must be greater than or equal to 1; otherwise, it returns `NaN`.

**Example:**

```js
console.log(Math.acosh(1)); // 0
console.log(Math.acosh(0.5)); // NaN
```

**Arguments:**

- `x`: A number greater than or equal to 1.

---

#### `Math.atanh(x)`

Returns the hyperbolic arctangent of a number between -1 and 1. If the input is outside this range, it returns `NaN`.

**Example:**

```js
console.log(Math.atanh(0.5)); // 0.5493061443340548
console.log(Math.atanh(2)); // NaN
```

**Arguments:**

- `x`: A number between -1 and 1.

---

### Logarithmic and Exponential Functions

Functions that deal with logarithms, exponents, and related calculations.

This category includes:

- [`Math.exp(x)`](#mathexpx)
- [`Math.expm1(x)`](#mathexpm1x)
- [`Math.log(x)`](#mathlogx)
- [`Math.log10(x)`](#mathlog10x)
- [`Math.log1p(x)`](#mathlog1px)
- [`Math.log2(x)`](#mathlog2x)

---

#### `Math.exp(x)`

Returns `e^x`, where `e` is Euler's number (~2.718).

**Example:**

```js
console.log(Math.exp(1)); // 2.718281828459045
console.log(Math.exp(0)); // 1
```

**Arguments:**

- `x`: A number.

---

#### `Math.expm1(x)`

Returns `e^x - 1`, where `e` is Euler's number (~2.718).

**Example:**

```js
console.log(Math.expm1(1)); // 1.718281828459045
console.log(Math.expm1(0)); // 0
```

**Arguments:**

- `x`: A number.

---

#### `Math.log(x)`

Returns the natural logarithm (base `e`) of a number.

**Example:**

```js
console.log(Math.log(1)); // 0
console.log(Math.log(Math.E)); // 1
```

**Arguments:**

- `x`: A number greater than 0.

---

#### `Math.log10(x)`

Returns the base-10 logarithm of a number.

**Example:**

```js
console.log(Math.log10(100)); // 2
console.log(Math.log10(1)); // 0
```

**Arguments:**

- `x`: A number greater than 0.

---

#### `Math.log1p(x)`

Returns the natural logarithm of `1 + x`.

**Example:**

```js
console.log(Math.log1p(0)); // 0
console.log(Math.log1p(1)); // 0.6931471805599453
```

**Arguments:**

- `x`: A number greater than -1.

---

#### `Math.log2(x)`

Returns the base-2 logarithm of a number.

**Example:**

```js
console.log(Math.log2(8)); // 3
console.log(Math.log2(1)); // 0
```

**Arguments:**

- `x`: A number greater than 0.

---

### Rounding and Precision

Functions that handle rounding numbers or adjusting their precision.

This category includes:

- [`Math.fround(x)`](#mathfroundx)
- [`Math.f16round(x)`](#mathf16roundx)

---

#### `Math.fround(x)`

Returns the nearest 32-bit single-precision float representation of a number.

**Example:**

```js
console.log(Math.fround(1.337)); // 1.3370000123977661
console.log(Math.fround(1.5)); // 1.5
```

**Arguments:**

- `x`: A number.

---

#### `Math.f16round(x)`

Rounds a number to the nearest 16-bit floating-point representation.

**Example:**

```js
console.log(Math.f16round(1.337)); // 1.3369140625
console.log(Math.f16round(1.5)); // 1.5
```

**Arguments:**

- `x`: A number.

---

### Bitwise and Binary Operations

Functions that operate on the binary representation of numbers.

This category includes:

- [`Math.clz32(x)`](#mathclz32x)

---

#### `Math.clz32(x)`

Returns the number of leading zero bits in the 32-bit binary representation of a number.

**Example:**

```js
console.log(Math.clz32(1)); // 31
console.log(Math.clz32(1000)); // 22
```

**Arguments:**

- `x`: A number.

---

### Random Number Generation

Functions that generate random numbers.

This category includes:

- [`Math.random()`](#mathrandom)

---

#### `Math.random()`

Returns a pseudo-random number between 0 (inclusive) and 1 (exclusive).

**Example:**

```js
console.log(Math.random()); // e.g., 0.123456789
```

---

This chapter provides a concise yet comprehensive overview of the `Math` object's functions, organized by functionality and formatted for quick reference.

## Static Properties

Static properties that represent commonly used mathematical constants.

This category includes:

- [`Math.E`](#mathe)
- [`Math.LN10`](#mathln10)
- [`Math.LN2`](#mathln2)
- [`Math.LOG10E`](#mathlog10e)
- [`Math.LOG2E`](#mathlog2e)
- [`Math.PI`](#mathpi)
- [`Math.SQRT1_2`](#mathsqrt1_2)
- [`Math.SQRT2`](#mathsqrt2)

---

### `Math.E`

Represents Euler's number, the base of natural logarithms, approximately equal to `2.718`.

**Example:**

```js
console.log(Math.E); // 2.718281828459045
```

---

### `Math.LN10`

Represents the natural logarithm of 10, approximately equal to `2.302`.

**Example:**

```js
console.log(Math.LN10); // 2.302585092994046
```

---

### `Math.LN2`

Represents the natural logarithm of 2, approximately equal to `0.693`.

**Example:**

```js
console.log(Math.LN2); // 0.6931471805599453
```

---

### `Math.LOG10E`

Represents the base-10 logarithm of Euler's number, approximately equal to `0.434`.

**Example:**

```js
console.log(Math.LOG10E); // 0.4342944819032518
```

---

### `Math.LOG2E`

Represents the base-2 logarithm of Euler's number, approximately equal to `1.442`.

**Example:**

```js
console.log(Math.LOG2E); // 1.4426950408889634
```

---

### `Math.PI`

Represents the ratio of the circumference of a circle to its diameter, approximately equal to `3.14159`.

**Example:**

```js
console.log(Math.PI); // 3.141592653589793
```

---

### `Math.SQRT1_2`

Represents the square root of 1/2, approximately equal to `0.707`.

**Example:**

```js
console.log(Math.SQRT1_2); // 0.7071067811865476
```

---

### `Math.SQRT2`

Represents the square root of 2, approximately equal to `1.414`.

**Example:**

```js
console.log(Math.SQRT2); // 1.4142135623730951
```
