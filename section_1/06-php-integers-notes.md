# PHP Integers

## Definition and Range
- Numbers without decimal points (e.g., 1, 2, 3, 0, -5)
- Size depends on platform:
  - 32-bit systems: -2 billion to +2 billion
  - 64-bit systems: much larger range
- Check range with constants: PHP_INT_MAX, PHP_INT_MIN, PHP_INT_SIZE

## Integer Representations
1. Decimal (Base 10): Default, e.g., `$x = 5;`
2. Hexadecimal (Base 16): Prefix 0x, e.g., `$x = 0x2A;` (equals 42)
3. Octal (Base 8): Prefix 0, e.g., `$x = 055;` (equals 45)
4. Binary (Base 2): Prefix 0b, e.g., `$x = 0b110;` (equals 6)

## Integer Overflow
- When exceeding PHP_INT_MAX, type changes to float
- Example:
  ```php
  $x = PHP_INT_MAX;
  var_dump($x); // int(2147483647)
  $x += 1;
  var_dump($x); // float(2147483648)
  ```

## Casting to Integer
- Use `(int)` or `(integer)`
- Casting rules:
  - Boolean true → 1, false → 0
  - Float → Rounded down (e.g., 5.9 → 5)
  - Numeric strings → Converted to integer
  - Strings with leading numbers → Only the number part is used
  - Non-numeric strings → 0
  - Null → 0

## Checking for Integer Type
- Use `is_int()` or `is_integer()` function
- Returns true if variable is an integer, false otherwise

## Integer Readability (PHP 7.4+)
- Use underscores for readability in integer literals
- Example: `$x = 1_000_000;` (equals 1000000)
- Only works with integer literals, not strings

## Important Notes
- Underscores in strings are not ignored when casting to int
- Example: `(int)"1_000_000"` results in 1, not 1000000

## Example
```php
$x = 42;
$y = 0x2A;  // Hexadecimal
$z = 052;   // Octal
$w = 0b101010;  // Binary

echo $x, $y, $z, $w;  // All print 42

$bigNumber = 1_000_000;
echo $bigNumber;  // Prints 1000000

var_dump(is_int($bigNumber));  // bool(true)
```
