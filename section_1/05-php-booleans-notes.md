# PHP Booleans

## Basic Definition
- Represents a truth value
- Can be either `true` or `false`
- Case-insensitive (`TRUE`, `True`, `true` are all valid)

## Usage
- Commonly used in control structures (loops, if/else conditionals)
- Example: 
  ```php
  $isComplete = true;
  if ($isComplete) {
      // do something
  } else {
      // do something else
  }
  ```

## Type Conversion to Boolean

### Values that evaluate to `false`:
1. Integers: 0 and -0
2. Floats: 0.0 and -0.0
3. Strings: "" (empty string) and "0"
4. Empty array: []
5. Special type: `null`

### Values that evaluate to `true`:
- Everything else, including negative numbers (except -0)

## Printing Booleans

1. Using conditionals:
   ```php
   echo ($booleanVar) ? "Success" : "Fail";
   ```

2. Direct echo:
   - `true` prints as "1"
   - `false` prints as "" (empty string)

3. Reason for echo behavior:
   - PHP casts boolean to string when printing
   - `(string)true` becomes "1"
   - `(string)false` becomes ""

4. Using `var_dump()`:
   - Shows both type and value
   - Example: `var_dump($booleanVar);`

## Checking Boolean Type

1. `is_bool()` function:
   - Returns `true` if the variable is a boolean
   - Example: `var_dump(is_bool($var));`

## Important Note
- String "false" evaluates to `true` because it's a non-empty string

## Example
```php
$isComplete = true;
echo $isComplete; // Outputs: 1
var_dump($isComplete); // Outputs: bool(true)
echo is_bool($isComplete) ? 'Yes' : 'No'; // Outputs: Yes

$falseString = "false";
echo ($falseString) ? "True" : "False"; // Outputs: True
```
