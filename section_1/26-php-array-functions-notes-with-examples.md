# PHP Array Functions with Examples

## Key Functions and Examples

1. `array_chunk($array, $size, $preserve_keys = false)`
   - Splits array into chunks of specified size
   ```php
   $input = [1, 2, 3, 4, 5];
   $result = array_chunk($input, 2);
   // Result: [[1, 2], [3, 4], [5]]
   ```

2. `array_combine($keys, $values)`
   - Creates an array using one array for keys and another for values
   ```php
   $keys = ['green', 'red', 'yellow'];
   $values = ['avocado', 'apple', 'banana'];
   $result = array_combine($keys, $values);
   // Result: ['green' => 'avocado', 'red' => 'apple', 'yellow' => 'banana']
   ```

3. `array_filter($array, $callback, $mode = 0)`
   - Filters elements of an array using a callback function
   ```php
   $numbers = [1, 2, 3, 4, 5, 6];
   $evenNumbers = array_filter($numbers, fn($n) => $n % 2 == 0);
   // Result: [2, 4, 6]
   ```

4. `array_map($callback, $array1, $array2, ...)`
   - Applies the callback to the elements of the given arrays
   ```php
   $numbers = [1, 2, 3, 4, 5];
   $squared = array_map(fn($n) => $n * $n, $numbers);
   // Result: [1, 4, 9, 16, 25]
   ```

5. `array_merge($array1, $array2, ...)`
   - Merges one or more arrays
   ```php
   $array1 = ['a' => 'apple', 'b' => 'banana'];
   $array2 = ['c' => 'cherry', 'b' => 'blackberry'];
   $result = array_merge($array1, $array2);
   // Result: ['a' => 'apple', 'b' => 'blackberry', 'c' => 'cherry']
   ```

6. `array_reduce($array, $callback, $initial = null)`
   - Reduces an array to a single value using a callback function
   ```php
   $numbers = [1, 2, 3, 4, 5];
   $sum = array_reduce($numbers, fn($carry, $item) => $carry + $item, 0);
   // Result: 15
   ```

7. `array_search($needle, $haystack, $strict = false)`
   - Searches the array for a given value and returns the key if found
   ```php
   $array = ['apple', 'banana', 'cherry'];
   $key = array_search('banana', $array);
   // Result: 1
   ```

8. `in_array($needle, $haystack, $strict = false)`
   - Checks if a value exists in an array
   ```php
   $fruits = ['apple', 'banana', 'cherry'];
   $exists = in_array('banana', $fruits);
   // Result: true
   ```

9. `array_diff($array1, $array2, ...)`
   - Computes the difference of arrays (values only)
   ```php
   $array1 = ['a' => 'green', 'b' => 'brown', 'c' => 'blue', 'red'];
   $array2 = ['a' => 'green', 'yellow', 'red'];
   $result = array_diff($array1, $array2);
   // Result: ['b' => 'brown', 'c' => 'blue']
   ```

10. `array_diff_assoc($array1, $array2, ...)`
    - Computes the difference of arrays with additional index check
    ```php
    $array1 = ['a' => 'green', 'b' => 'brown', 'c' => 'blue', 'red'];
    $array2 = ['a' => 'green', 'b' => 'yellow', 'blue'];
    $result = array_diff_assoc($array1, $array2);
    // Result: ['b' => 'brown', 'c' => 'blue', 0 => 'red']
    ```

11. Sorting Functions:
    - `asort($array)`: Sort an array and maintain index association
    ```php
    $fruits = ['d' => 'lemon', 'a' => 'orange', 'b' => 'banana', 'c' => 'apple'];
    asort($fruits);
    // Result: ['c' => 'apple', 'b' => 'banana', 'd' => 'lemon', 'a' => 'orange']
    ```
    - `ksort($array)`: Sort an array by key
    ```php
    $fruits = ['d' => 'lemon', 'a' => 'orange', 'b' => 'banana', 'c' => 'apple'];
    ksort($fruits);
    // Result: ['a' => 'orange', 'b' => 'banana', 'c' => 'apple', 'd' => 'lemon']
    ```
    - `usort($array, $callback)`: Sort an array by values using a user-defined comparison function
    ```php
    $fruits = ['lemon', 'orange', 'banana', 'apple'];
    usort($fruits, fn($a, $b) => strlen($a) - strlen($b));
    // Result: ['apple', 'lemon', 'orange', 'banana']
    ```

## Array Destructuring

```php
$info = ['coffee', 'brown', 'caffeine'];

// List all variables
list($drink, $color, $power) = $info;
// $drink = 'coffee', $color = 'brown', $power = 'caffeine'

// Skip an element
[$drink, , $power] = $info;
// $drink = 'coffee', $power = 'caffeine'

// Nested arrays
$info = ['coffee', ['green', 'yellow'], 'caffeine'];
[$drink, [$color1, $color2], $power] = $info;
// $drink = 'coffee', $color1 = 'green', $color2 = 'yellow', $power = 'caffeine'
```

These examples demonstrate the usage of each array function and array destructuring in PHP. They provide a practical reference for understanding how these functions work with different types of input data.
