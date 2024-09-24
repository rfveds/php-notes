# PHP Operators (Part 2)

## Error Control Operator
- Symbol: `@`
- Suppresses error messages
- Not recommended for general use
- Example: `@file_get_contents('non_existent_file.txt');`

## Increment/Decrement Operators
- Pre-increment: `++$x`
- Post-increment: `$x++`
- Pre-decrement: `--$x`
- Post-decrement: `$x--`

Notes:
- Only affect numbers and strings
- Incrementing null results in 1, decrementing null has no effect
- Incrementing strings affects characters

## Logical Operators
1. AND: `&&` or `and`
2. OR: `||` or `or`
3. NOT: `!`

Notes:
- Short-circuiting: PHP stops evaluating as soon as the result is known
- `&&` and `||` have different precedence than `and` and `or`

## Bitwise Operators
1. AND: `&`
2. OR: `|`
3. XOR: `^`
4. NOT: `~`
5. Left shift: `<<`
6. Right shift: `>>`

Use cases:
- Encryption
- Storing flags as bits
- Storing permissions

## Array Operators
1. Union: `+`
2. Equality: `==`
3. Identity: `===`
4. Inequality: `!=` or `<>`
5. Non-identity: `!==`

Notes:
- Union combines arrays, keeping original keys
- Comparison checks key-value pairs
- Strict comparison also checks data types and order

## Other Operators
1. Execution Operator: `` ` ` `` (backticks)
2. Type Operators: `instanceof`
3. Null-safe Operator: `?->`

Note: These are advanced operators covered later in the course.

## Examples

```php
// Error Control
$content = @file_get_contents('non_existent_file.txt');

// Increment/Decrement
$x = 5;
echo $x++;  // Outputs 5, then $x becomes 6
echo ++$x;  // $x becomes 7, then outputs 7

// Logical Operators
$result = (true && false);  // false
$result = (true || false);  // true

// Bitwise Operators
$a = 6;  // 110 in binary
$b = 3;  // 011 in binary
echo $a & $b;  // Outputs 2 (010 in binary)

// Array Operators
$arr1 = ['a' => 1, 'b' => 2];
$arr2 = ['b' => 3, 'c' => 4];
$result = $arr1 + $arr2;  // ['a' => 1, 'b' => 2, 'c' => 4]
```

## Key Takeaways
1. Avoid using the error control operator (@) unless absolutely necessary
2. Understand the difference between pre and post increment/decrement
3. Be aware of short-circuiting in logical operations
4. Bitwise operators are useful for certain optimizations and flag operations
5. Array operators behave differently from their scalar counterparts
6. Always consider using strict comparison (`===`) for arrays to avoid unexpected results
