# Date

The `Date` object in JavaScript represents a specific point in time. It provides methods for creating, formatting, and manipulating dates and times, including support for time zones and daylight saving time.

- [Date](#date)
  - [`Date()` Constructor](#date-constructor)
  - [Static Methods](#static-methods)
    - [`Date.now()`](#datenow)
    - [`Date.parse(dateString)`](#dateparsedatestring)
    - [`Date.UTC(year, month, day, hours, minutes, seconds, ms)`](#dateutcyear-month-day-hours-minutes-seconds-ms)
  - [Instance Methods](#instance-methods)
    - [Date and Time Retrieval (Local Time)](#date-and-time-retrieval-local-time)
      - [`getDate()`](#getdate)
      - [`getDay()`](#getday)
      - [`getFullYear()`](#getfullyear)
      - [`getHours()`](#gethours)
      - [`getMilliseconds()`](#getmilliseconds)
      - [`getMinutes()`](#getminutes)
      - [`getMonth()`](#getmonth)
      - [`getSeconds()`](#getseconds)
      - [`getTime()`](#gettime)
      - [`getTimezoneOffset()`](#gettimezoneoffset)
    - [Date and Time Retrieval (UTC)](#date-and-time-retrieval-utc)
      - [`getUTCDate()`](#getutcdate)
      - [`getUTCDay()`](#getutcday)
      - [`getUTCFullYear()`](#getutcfullyear)
      - [`getUTCHours()`](#getutchours)
      - [`getUTCMilliseconds()`](#getutcmilliseconds)
      - [`getUTCMinutes()`](#getutcminutes)
      - [`getUTCMonth()`](#getutcmonth)
      - [`getUTCSeconds()`](#getutcseconds)
    - [Date and Time Modification (Local Time)](#date-and-time-modification-local-time)
      - [`setDate(date)`](#setdatedate)
      - [`setFullYear(year, month, day)`](#setfullyearyear-month-day)
      - [`setHours(hours, minutes, seconds, milliseconds)`](#sethourshours-minutes-seconds-milliseconds)
      - [`setMilliseconds(milliseconds)`](#setmillisecondsmilliseconds)
      - [`setMinutes(minutes, seconds, milliseconds)`](#setminutesminutes-seconds-milliseconds)
      - [`setMonth(month, date)`](#setmonthmonth-date)
      - [`setSeconds(seconds, milliseconds)`](#setsecondsseconds-milliseconds)
      - [`setTime(time)`](#settimetime)
    - [Date and Time Modification (UTC)](#date-and-time-modification-utc)
      - [`setUTCDate(date)`](#setutcdatedate)
      - [`setUTCFullYear(year, month, date)`](#setutcfullyearyear-month-date)
      - [`setUTCHours(hours, minutes, seconds, milliseconds)`](#setutchourshours-minutes-seconds-milliseconds)
      - [`setUTCMilliseconds(milliseconds)`](#setutcmillisecondsmilliseconds)
      - [`setUTCMinutes(minutes, seconds, milliseconds)`](#setutcminutesminutes-seconds-milliseconds)
      - [`setUTCMonth(month, date)`](#setutcmonthmonth-date)
      - [`setUTCSeconds(seconds, milliseconds)`](#setutcsecondsseconds-milliseconds)
    - [Date and Time Formatting](#date-and-time-formatting)
      - [`toDateString()`](#todatestring)
      - [`toISOString()`](#toisostring)
      - [`toJSON()`](#tojson)
      - [`toLocaleDateString(locales, options)`](#tolocaledatestringlocales-options)
      - [`toLocaleString(locales, options)`](#tolocalestringlocales-options)
      - [`toLocaleTimeString(locales, options)`](#tolocaletimestringlocales-options)
      - [`toString()`](#tostring)
      - [`toTimeString()`](#totimestring)
      - [`toUTCString()`](#toutcstring)
      - [`toTemporalInstant()` (Experimental)](#totemporalinstant-experimental)
    - [Primitive Value Conversion](#primitive-value-conversion)
      - [`valueOf()`](#valueof)
      - [`[Symbol.toPrimitive](hint)`](#symboltoprimitivehint)

## `Date()` Constructor

Creates a `Date` object representing a specific date and time or the current date and time if called without arguments.

**Example (Current Date and Time):**

```js
let now = new Date();
console.log(now); // Current date and time
```

**Example (Specific Date):**

```js
let specificDate = new Date(2025, 0, 30); // Year, Month (0-based), Day
console.log(specificDate); // Thu Jan 30 2025 00:00:00 GMT+0000
```

**Example (Using a Timestamp):**

```js
let timestampDate = new Date(1706592000000);
console.log(timestampDate); // Date based on milliseconds since Unix Epoch
```

**Example (Parsing a Date String):**

```js
let stringDate = new Date("2025-01-30T12:00:00Z");
console.log(stringDate); // Thu Jan 30 2025 12:00:00 GMT
```

**Arguments:**

- No arguments: Returns the current date and time.
- `year, month, day, hours, minutes, seconds, milliseconds`: Constructs a date with specific values.
- `timestamp`: Constructs a date from a number of milliseconds since `1970-01-01T00:00:00Z`.
- `dateString`: Parses a string and returns the corresponding date.

**Note:**

- Months are **zero-based** (`0` = January, `11` = December).
- If an invalid date is provided, `Invalid Date` is returned.

## Static Methods

### `Date.now()`

Returns the current timestamp as the number of milliseconds since January 1, 1970 (UTC).

**Example:**

```js
console.log(Date.now()); // 1700000000000 (example output)
```

---

### `Date.parse(dateString)`

Parses a date string and returns the timestamp (milliseconds since January 1, 1970, UTC). Returns `NaN` if the string is invalid.

**Example:**

```js
console.log(Date.parse("2024-01-30")); // 1706572800000
console.log(Date.parse("Invalid Date")); // NaN
```

**Arguments:**

- `dateString`: A string representing a date. Must be in a recognized format.

---

### `Date.UTC(year, month, day, hours, minutes, seconds, ms)`

Creates a timestamp (milliseconds since January 1, 1970, UTC) for a given date and time.

**Example:**

```js
console.log(Date.UTC(2024, 0, 30)); // 1706572800000
console.log(Date.UTC(2024, 0, 30, 12, 30)); // 1706617800000
```

**Arguments:**

- `year`: The full year.
- `month`: The month (0-based, `0` for January, `11` for December).
- `day` (Optional): The day of the month. Defaults to `1`.
- `hours` (Optional): The hour. Defaults to `0`.
- `minutes` (Optional): The minutes. Defaults to `0`.
- `seconds` (Optional): The seconds. Defaults to `0`.
- `ms` (Optional): The milliseconds. Defaults to `0`.

## Instance Methods

### Date and Time Retrieval (Local Time)

Retrieve specific components of the date and time in the local time zone.

---

#### `getDate()`

Gets the day of the month (1–31) of the `Date` object in the local time zone.

**Example:**

```js
let date = new Date("2025-02-01");
console.log(date.getDate()); // 1
```

---

#### `getDay()`

Gets the day of the week (0–6) of the `Date` object in the local time zone. 0 represents Sunday, 1 represents Monday, and so on.

**Example:**

```js
let date = new Date("2025-02-01");
console.log(date.getDay()); // 6 (Saturday)
```

---

#### `getFullYear()`

Gets the four-digit year of the `Date` object in the local time zone.

**Example:**

```js
let date = new Date("2025-02-01");
console.log(date.getFullYear()); // 2025
```

---

#### `getHours()`

Gets the hour (0–23) of the `Date` object in the local time zone.

**Example:**

```js
let date = new Date("2025-02-01T12:30:00");
console.log(date.getHours()); // 12
```

---

#### `getMilliseconds()`

Gets the milliseconds (0–999) of the `Date` object in the local time zone.

**Example:**

```js
let date = new Date("2025-02-01T12:30:30.123");
console.log(date.getMilliseconds()); // 123
```

---

#### `getMinutes()`

Gets the minutes (0–59) of the `Date` object in the local time zone.

**Example:**

```js
let date = new Date("2025-02-01T12:30:00");
console.log(date.getMinutes()); // 30
```

---

#### `getMonth()`

Gets the month (0–11) of the `Date` object in the local time zone. 0 represents January, 1 represents February, and so on.

**Example:**

```js
let date = new Date("2025-02-01");
console.log(date.getMonth()); // 1 (February)
```

---

#### `getSeconds()`

Gets the seconds (0–59) of the `Date` object in the local time zone.

**Example:**

```js
let date = new Date("2025-02-01T12:30:45");
console.log(date.getSeconds()); // 45
```

---

#### `getTime()`

Gets the number of milliseconds since the Unix epoch (`1970-01-01T00:00:00Z`) for the `Date` object in the local time zone.

**Example:**

```js
let date = new Date("2025-02-01");
console.log(date.getTime()); // 1738329600000
```

---

#### `getTimezoneOffset()`

Gets the time difference between UTC and the local time zone, in minutes, for the `Date` object.

**Example:**

```js
let date = new Date("2025-02-01");
console.log(date.getTimezoneOffset()); // The time difference in minutes (e.g., -120 for UTC+2)
```

---

### Date and Time Retrieval (UTC)

Retrieve specific components of the date and time in Coordinated Universal Time (UTC).

---

#### `getUTCDate()`

Gets the day of the month (1–31) of the `Date` object in Coordinated Universal Time (UTC).

**Example:**

```js
let date = new Date("2025-02-01T12:30:00Z");
console.log(date.getUTCDate()); // 1
```

---

#### `getUTCDay()`

Gets the day of the week (0–6) of the `Date` object in UTC. 0 represents Sunday, 1 represents Monday, and so on.

**Example:**

```js
let date = new Date("2025-02-01T12:30:00Z");
console.log(date.getUTCDay()); // 6 (Saturday)
```

---

#### `getUTCFullYear()`

Gets the four-digit year of the `Date` object in UTC.

**Example:**

```js
let date = new Date("2025-02-01T12:30:00Z");
console.log(date.getUTCFullYear()); // 2025
```

---

#### `getUTCHours()`

Gets the hour (0–23) of the `Date` object in UTC.

**Example:**

```js
let date = new Date("2025-02-01T12:30:00Z");
console.log(date.getUTCHours()); // 12
```

---

#### `getUTCMilliseconds()`

Gets the milliseconds (0–999) of the `Date` object in UTC.

**Example:**

```js
let date = new Date("2025-02-01T12:30:30.123Z");
console.log(date.getUTCMilliseconds()); // 123
```

---

#### `getUTCMinutes()`

Gets the minutes (0–59) of the `Date` object in UTC.

**Example:**

```js
let date = new Date("2025-02-01T12:30:00Z");
console.log(date.getUTCMinutes()); // 30
```

---

#### `getUTCMonth()`

Gets the month (0–11) of the `Date` object in UTC. 0 represents January, 1 represents February, and so on.

**Example:**

```js
let date = new Date("2025-02-01T12:30:00Z");
console.log(date.getUTCMonth()); // 1 (February)
```

---

#### `getUTCSeconds()`

Gets the seconds (0–59) of the `Date` object in UTC.

**Example:**

```js
let date = new Date("2025-02-01T12:30:45Z");
console.log(date.getUTCSeconds()); // 45
```

---

### Date and Time Modification (Local Time)

Set or modify specific components of the date and time in the local time zone.

---

#### `setDate(date)`

Sets the day of the month (1–31) for the `Date` object.

**Example:**

```js
let date = new Date("2025-02-01");
date.setDate(15);
console.log(date); // 2025-02-15T00:00:00.000Z
```

**Arguments:**

- `date`: The day of the month (1–31) to set.

---

#### `setFullYear(year, month, day)`

Sets the full year (four digits) for the `Date` object.

**Example:**

```js
let date = new Date("2025-02-01");
date.setFullYear(2027);
console.log(date); // 2027-02-01T00:00:00.000Z
```

**Arguments:**

- `year`: The full year (four digits) to set.
- `month` (Optional): The month (0–11) to set. Defaults to the current month if not provided.
- `day` (Optional): The day of the month (1–31) to set. Defaults to the current day if not provided.

---

#### `setHours(hours, minutes, seconds, milliseconds)`

Sets the hour (0–23) for the `Date` object.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
date.setHours(15);
console.log(date); // 2025-02-01T15:00:00.000Z
```

**Arguments:**

- `hours`: The hour (0–23) to set.
- `minutes` (Optional): The minutes (0–59) to set. Defaults to the current minutes if not provided.
- `seconds` (Optional): The seconds (0–59) to set. Defaults to the current seconds if not provided.
- `milliseconds` (Optional): The milliseconds (0–999) to set. Defaults to the current milliseconds if not provided.

---

#### `setMilliseconds(milliseconds)`

Sets the milliseconds (0–999) for the `Date` object.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00.500Z");
date.setMilliseconds(300);
console.log(date); // 2025-02-01T10:00:00.300Z
```

**Arguments:**

- `milliseconds`: The milliseconds (0–999) to set.

---

#### `setMinutes(minutes, seconds, milliseconds)`

Sets the minutes (0–59) for the `Date` object.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
date.setMinutes(45);
console.log(date); // 2025-02-01T10:45:00.000Z
```

**Arguments:**

- `minutes`: The minutes (0–59) to set.
- `seconds` (Optional): The seconds (0–59) to set. Defaults to the current seconds if not provided.
- `milliseconds` (Optional): The milliseconds (0–999) to set. Defaults to the current milliseconds if not provided.

---

#### `setMonth(month, date)`

Sets the month (0–11) for the `Date` object.

**Example:**

```js
let date = new Date("2025-02-01");
date.setMonth(5); // June (5)
console.log(date); // 2025-06-01T00:00:00.000Z
```

**Arguments:**

- `month`: The month (0–11) to set.
- `date` (Optional): The day of the month (1–31) to set. Defaults to the current day if not provided.

---

#### `setSeconds(seconds, milliseconds)`

Sets the seconds (0–59) for the `Date` object.

**Example:**

```js
let date = new Date("2025-02-01T10:00:30Z");
date.setSeconds(15);
console.log(date); // 2025-02-01T10:00:15.000Z
```

**Arguments:**

- `seconds`: The seconds (0–59) to set.
- `milliseconds` (Optional): The milliseconds (0–999) to set. Defaults to the current milliseconds if not provided.

---

#### `setTime(time)`

Sets the `Date` object to the specified timestamp (in milliseconds since the Unix epoch).

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
date.setTime(1583020800000); // Timestamp for 2020-02-01T10:00:00Z
console.log(date); // 2020-02-01T10:00:00.000Z
```

**Arguments:**

- `time`: The timestamp (in milliseconds) to set the `Date` object to.

---

### Date and Time Modification (UTC)

Set or modify specific components of the date and time in Coordinated Universal Time (UTC).

---

#### `setUTCDate(date)`

Sets the day of the month (1–31) for the `Date` object in UTC time.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
date.setUTCDate(15);
console.log(date); // 2025-02-15T10:00:00.000Z
```

**Arguments:**

- `date`: The day of the month (1–31) to set in UTC.

---

#### `setUTCFullYear(year, month, date)`

Sets the full year (four digits) for the `Date` object in UTC time.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
date.setUTCFullYear(2027);
console.log(date); // 2027-02-01T10:00:00.000Z
```

**Arguments:**

- `year`: The full year (four digits) to set in UTC.
- `month` (Optional): The month (0–11) to set. Defaults to the current month if not provided.
- `date` (Optional): The day of the month (1–31) to set. Defaults to the current day if not provided.

---

#### `setUTCHours(hours, minutes, seconds, milliseconds)`

Sets the hour (0–23) for the `Date` object in UTC time.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
date.setUTCHours(15);
console.log(date); // 2025-02-01T15:00:00.000Z
```

**Arguments:**

- `hours`: The hour (0–23) to set in UTC.
- `minutes` (Optional): The minutes (0–59) to set in UTC. Defaults to the current minutes if not provided.
- `seconds` (Optional): The seconds (0–59) to set in UTC. Defaults to the current seconds if not provided.
- `milliseconds` (Optional): The milliseconds (0–999) to set in UTC. Defaults to the current milliseconds if not provided.

---

#### `setUTCMilliseconds(milliseconds)`

Sets the milliseconds (0–999) for the `Date` object in UTC time.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00.500Z");
date.setUTCMilliseconds(300);
console.log(date); // 2025-02-01T10:00:00.300Z
```

**Arguments:**

- `milliseconds`: The milliseconds (0–999) to set in UTC.

---

#### `setUTCMinutes(minutes, seconds, milliseconds)`

Sets the minutes (0–59) for the `Date` object in UTC time.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
date.setUTCMinutes(45);
console.log(date); // 2025-02-01T10:45:00.000Z
```

**Arguments:**

- `minutes`: The minutes (0–59) to set in UTC.
- `seconds` (Optional): The seconds (0–59) to set in UTC. Defaults to the current seconds if not provided.
- `milliseconds` (Optional): The milliseconds (0–999) to set in UTC. Defaults to the current milliseconds if not provided.

---

#### `setUTCMonth(month, date)`

Sets the month (0–11) for the `Date` object in UTC time.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
date.setUTCMonth(5); // June (5)
console.log(date); // 2025-06-01T10:00:00.000Z
```

**Arguments:**

- `month`: The month (0–11) to set in UTC.
- `date` (Optional): The day of the month (1–31) to set. Defaults to the current day if not provided.

---

#### `setUTCSeconds(seconds, milliseconds)`

Sets the seconds (0–59) for the `Date` object in UTC time.

**Example:**

```js
let date = new Date("2025-02-01T10:00:30Z");
date.setUTCSeconds(15);
console.log(date); // 2025-02-01T10:00:15.000Z
```

**Arguments:**

- `seconds`: The seconds (0–59) to set in UTC.
- `milliseconds` (Optional): The milliseconds (0–999) to set in UTC. Defaults to the current milliseconds if not provided.

---

### Date and Time Formatting

Convert the date and time into human-readable strings or other formats.

---

#### `toDateString()`

Converts the `Date` object to a human-readable string that only includes the date part (not the time).

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
console.log(date.toDateString()); // Sat Feb 01 2025
```

---

#### `toISOString()`

Converts the `Date` object to a string in ISO 8601 format, which includes both the date and time in UTC.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
console.log(date.toISOString()); // 2025-02-01T10:00:00.000Z
```

---

#### `toJSON()`

Returns a string representing the `Date` object, suitable for JSON serialization, typically in ISO 8601 format.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
console.log(date.toJSON()); // 2025-02-01T10:00:00.000Z
```

---

#### `toLocaleDateString(locales, options)`

Converts the `Date` object to a string representing only the date, formatted according to the local conventions of a specified locale.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
console.log(date.toLocaleDateString("en-US")); // 2/1/2025
```

**Arguments:**

- `locales` (Optional): A string with a BCP 47 language tag, specifying the locale.
- `options` (Optional): An object containing options for formatting the date (e.g., `weekday`, `year`, `month`, `day`).

---

#### `toLocaleString(locales, options)`

Converts the `Date` object to a string representing both the date and time, formatted according to the local conventions of a specified locale.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
console.log(date.toLocaleString("en-US")); // 2/1/2025, 10:00:00 AM
```

**Arguments:**

- `locales` (Optional): A string with a BCP 47 language tag, specifying the locale.
- `options` (Optional): An object containing options for formatting the date and time (e.g., `weekday`, `year`, `month`, `day`, `hour`, `minute`, `second`).

---

#### `toLocaleTimeString(locales, options)`

Converts the `Date` object to a string representing only the time, formatted according to the local conventions of a specified locale.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
console.log(date.toLocaleTimeString("en-US")); // 10:00:00 AM
```

**Arguments:**

- `locales` (Optional): A string with a BCP 47 language tag, specifying the locale.
- `options` (Optional): An object containing options for formatting the time (e.g., `hour`, `minute`, `second`, `timeZoneName`).

---

#### `toString()`

Converts the `Date` object to a string representation that includes both the date and time, formatted according to the local time zone.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
console.log(date.toString()); // Sat Feb 01 2025 10:00:00 GMT+0000 (Coordinated Universal Time)
```

---

#### `toTimeString()`

Converts the `Date` object to a string that only includes the time part, formatted according to the local time zone.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
console.log(date.toTimeString()); // 10:00:00 GMT+0000 (Coordinated Universal Time)
```

---

#### `toUTCString()`

Converts the `Date` object to a string that represents the date and time in UTC, in a format similar to `Date.toString()`, but in Coordinated Universal Time.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
console.log(date.toUTCString()); // Sat, 01 Feb 2025 10:00:00 GMT
```

---

#### `toTemporalInstant()` (Experimental)

Converts the `Date` object to a `Temporal.Instant` object, which is a part of the newer `Temporal` API for more precise date and time handling.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
console.log(date.toTemporalInstant()); // Temporal.Instant { timeZone: ... }
```

---

### Primitive Value Conversion

Convert the Date object to a primitive value (number or string) for comparison or arithmetic operations.

---

#### `valueOf()`

Returns the primitive value of a `Date` object, which is the number of milliseconds since the Unix Epoch (January 1, 1970, 00:00:00 UTC).

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
console.log(date.valueOf()); // 1738380000000
```

---

#### `[Symbol.toPrimitive](hint)`

This is a special method that allows you to customize how an object is converted to a primitive value when it's used in operations that expect a primitive value, such as arithmetic or string concatenation. For `Date` objects, this method returns the number of milliseconds since the Unix Epoch.

**Example:**

```js
let date = new Date("2025-02-01T10:00:00Z");
console.log(date[Symbol.toPrimitive]("number")); // 1738380000000
console.log(date[Symbol.toPrimitive]("string")); // Sat Feb 01 2025 10:00:00 GMT+0000 (Coordinated Universal Time)
```

**Arguments:**

- `hint`: A string that indicates the desired type of conversion, either `"number"`, `"string"`, or `"default"`. When the `hint` is `"number"`, the `Date` object will be converted to its primitive numeric value (milliseconds). When `"string"` is used, it converts to a string representation.
