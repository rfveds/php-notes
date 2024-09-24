# PHP Floats

## Definition and Representation
- Numbers with decimal points (e.g., 13.5)
- Can be represented in exponential form (e.g., 13.5e3 = 13500)
- Underscores allowed for readability in PHP 7.4+ (e.g., 13_000.5)

## Size and Range
- Depends on the platform
- Check range with constants: PHP_FLOAT_MAX, PHP_FLOAT_MIN

## Precision Issues
- Limited precision due to binary representation
- Example: 
  ```php
  echo floor((0.1 + 0.7) * 10); // Outputs 7 instead of 8
  ```
- Never trust floats to the last digit
- Never compare floats directly for equality

## Special Float Values
1. NaN (Not a Number)
   - Represented by constant NAN
   - Result of undefined operations (e.g., log(-1))
   - Check with is_nan() function

2. Infinity
   - Represented by constant INF
   - Result of operations exceeding float bounds
   - Check with is_infinite() or is_finite() functions

## Casting to Float
- Use (float) or floatval() function
- Casting rules:
  - Numeric strings: Converted to float
  - Non-numeric strings: Converted to 0.0

## Important Considerations
1. Comparison:
   ```php
   $x = 0.23;
   $y = 1 - 0.77;
   if ($x == $y) {
       echo "Equal"; // This might not execute due to precision issues
   }
   ```

2. Checking for special values:
   ```php
   $x = log(-1);
   var_dump(is_nan($x)); // bool(true)

   $y = PHP_FLOAT_MAX * 2;
   var_dump(is_infinite($y)); // bool(true)
   ```

## Examples
```php
$x = 13.5;
$y = 13.5e3; // 13500
$z = 13.5e-3; // 0.0135

$readableFloat = 13_000.5; // PHP 7.4+

var_dump((float)"15.5"); // float(15.5)
var_dump((float)"not a number"); // float(0)
```

## Key Takeaways
- Be cautious with float precision
- Use appropriate functions (is_nan(), is_infinite()) to check for special values
- Avoid direct equality comparisons between floats
- Be aware of casting behavior, especially with strings
