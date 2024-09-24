# PHP Loops

## Types of Loops in PHP
1. While loop
2. Do-while loop
3. For loop
4. Foreach loop

## While Loop
```php
while (condition) {
    // code to be executed
}
```
- Executes as long as the condition is true
- Condition is checked at the beginning of each iteration

### Infinite Loops
- Occur when the loop condition is always true
- Can be intentional (e.g., `while(true)`)
- Use `break` to exit the loop

### Break and Continue
- `break`: Exits the loop
- `continue`: Skips the current iteration
- Both accept optional numeric argument for nested loops

### Alternative Syntax
```php
while (condition):
    // code
endwhile;
```

## Do-While Loop
```php
do {
    // code to be executed
} while (condition);
```
- Executes at least once before checking the condition

## For Loop
```php
for (init; condition; increment) {
    // code to be executed
}
```
- Three expressions: initialization, condition, increment
- Each expression can be empty or contain multiple expressions separated by commas
- Condition is checked at the beginning of each iteration

### Performance Tip
- Avoid unnecessary function calls in the condition
- Example:
  ```php
  $length = count($array);
  for ($i = 0; $i < $length; $i++) {
      // code
  }
  ```

## Foreach Loop
```php
foreach ($array as $value) {
    // code to be executed
}

foreach ($array as $key => $value) {
    // code to be executed
}
```
- Used to iterate over arrays or objects
- Can access both key and value
- By default, assigns values by value, not reference

### Reference Assignment
```php
foreach ($array as &$value) {
    // $value is a reference to the array element
}
```
- Modifying $value will modify the original array
- Unset the reference variable after the loop to avoid unintended modifications

### Iterating Over Multidimensional Arrays
- Use nested foreach loops or json_encode() for complex structures

### Alternative Syntax
```php
foreach ($array as $value):
    // code
endforeach;
```

## Key Points
1. Choose the appropriate loop based on your needs
2. Be cautious of infinite loops
3. Use break and continue for more complex flow control
4. Consider performance when using function calls in loop conditions
5. Be aware of variable scope and reference issues in foreach loops
6. Alternative syntax is available for embedding in HTML

## Examples
```php
// While loop
$i = 0;
while ($i <= 15) {
    echo $i++;
}

// For loop
for ($i = 0; $i < count($array); $i++) {
    echo $array[$i];
}

// Foreach loop
$users = ['name' => 'John', 'email' => 'john@example.com'];
foreach ($users as $key => $value) {
    echo "$key: $value\n";
}
```
