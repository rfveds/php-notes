# PHP Arrays

## Introduction
Arrays in PHP are versatile data structures that can store multiple values of different types.

## Creating Arrays
1. Using square brackets:
   ```php
   $programmingLanguages = ['PHP', 'Java', 'Python'];
   ```
2. Using the `array()` function (older syntax):
   ```php
   $programmingLanguages = array('PHP', 'Java', 'Python');
   ```

## Accessing Array Elements
- Arrays are zero-indexed by default
- Access elements using square brackets: `$array[0]`
- Cannot use negative indexes like with strings

## Array Types
1. Indexed Arrays: Default numeric keys (0, 1, 2, ...)
2. Associative Arrays: Custom string or integer keys
   ```php
   $versions = [
       'PHP' => '8.0',
       'Python' => '3.9'
   ];
   ```

## Multidimensional Arrays
Arrays can contain other arrays as elements:
```php
$languages = [
    'PHP' => [
        'versions' => ['8.0', '7.4'],
        'creator' => 'Rasmus Lerdorf',
        'isOpenSource' => true
    ],
    // More languages...
];
```

## Array Operations
1. Adding elements:
   - To the end: `$array[] = $value;` or `array_push($array, $value);`
   - With a specific key: `$array['key'] = $value;`

2. Removing elements:
   - Last element: `array_pop($array);`
   - First element: `array_shift($array);`
   - Specific element: `unset($array[key]);`

3. Checking if a key exists:
   - `isset($array['key'])`: Returns false for null values
   - `array_key_exists('key', $array)`: Returns true even for null values

4. Getting array length: `count($array)`

## Array Behavior
- Duplicate keys: Last value overwrites previous ones
- Key types: Strings and integers (other types are converted)
- Auto-incrementing: PHP assigns incremental keys when not specified
- Re-indexing: Occurs with `array_shift()` but not with `unset()`

## Casting to Array
- Scalar values become the first element of a new array
- Null becomes an empty array

## Important Notes
- Be cautious of warnings when accessing non-existent keys
- Use `isset()` or `array_key_exists()` to check for key existence
- Be aware of the difference between `isset()` and `array_key_exists()`

## Examples
```php
// Associative array
$versions = ['PHP' => '8.0', 'Python' => '3.9'];
echo $versions['PHP']; // Outputs: 8.0

// Multidimensional array
$languages['PHP']['versions'][] = '8.1';
echo $languages['PHP']['versions'][2]; // Outputs: 8.1

// Removing elements
unset($array[1]); // Removes element at index 1 without re-indexing

// Checking key existence
$array = ['a' => 1, 'b' => null];
var_dump(array_key_exists('b', $array)); // true
var_dump(isset($array['b'])); // false
```
