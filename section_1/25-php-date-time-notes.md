# PHP Date and Time Handling

## Basic Functions

1. `time()`: 
   - Returns current Unix timestamp (seconds since January 1, 1970)
   - Example: `echo time();`

2. `date()`:
   - Formats a timestamp or current time
   - Syntax: `date(format, [timestamp])`
   - Example: `echo date("m-d H:i a");`

3. `mktime()`:
   - Creates a timestamp for a specific date
   - Syntax: `mktime(hour, minute, second, month, day, year)`
   - Example: `mktime(0, 0, 0, 4, 10, null)` (April 10th, current year)

4. `strtotime()`:
   - Converts a string to a timestamp
   - Example: `strtotime("2021-01-18 7am")`
   - Supports relative formats: "tomorrow", "first day of February", etc.

5. `date_parse()` and `date_parse_from_format()`:
   - Parse date strings into detailed arrays
   - Example: `date_parse("2021-01-18 7am")`

## Time Zone Handling

- Set default time zone: `date_default_timezone_set("UTC")`
- Get current time zone: `date_default_timezone_get()`

## Date Formatting

- Use format characters in `date()` function
- Common format characters:
  - `d`: Day of month (01-31)
  - `m`: Month (01-12)
  - `Y`: Four-digit year
  - `H`: 24-hour format (00-23)
  - `i`: Minutes (00-59)
  - `a`: am/pm

## Date Calculations

- Add/subtract seconds from timestamp:
  ```php
  $future = time() + (5 * 24 * 60 * 60); // 5 days in future
  $past = time() - (24 * 60 * 60); // 1 day in past
  ```

## Best Practices

1. Store dates in UTC
2. Convert to local time zones only for display
3. Use `strtotime()` for parsing user input
4. Always validate and sanitize date inputs

## Examples

```php
// Current formatted date
echo date("Y-m-d H:i:s");

// Future date
$futureTimestamp = time() + (5 * 24 * 60 * 60);
echo date("Y-m-d", $futureTimestamp);

// Parsing string to date
$timestamp = strtotime("next Friday");
echo date("Y-m-d", $timestamp);

// Working with time zones
date_default_timezone_set("UTC");
echo date("Y-m-d H:i:s");
```

## Key Takeaways

1. Unix timestamp is the foundation for PHP date/time functions
2. `date()` function is versatile for formatting dates
3. `strtotime()` is powerful for parsing various date formats
4. Always be mindful of time zones in date/time operations
5. Use appropriate functions for creating, parsing, and formatting dates

