# PHP Operators (Part 1)

## Introduction to Operators
- Operators work with operands to form expressions
- Types of operators based on number of operands:
  - Unary: One operand
  - Binary: Two operands (most common in PHP)
  - Ternary: Three operands

## Arithmetic Operators
1. Addition: `+`
2. Subtraction: `-`
3. Multiplication: `*`
4. Division: `/`
5. Modulus: `%`
6. Exponentiation: `**`

### Notes on Arithmetic Operators:
- `+` and `-` can be used as unary operators to convert to int/float
- Division always returns float, unless operands are integers and evenly divisible
- Modulus casts operands to integers
- Use `fmod()` for floating-point modulus
- Sign of modulus result comes from the dividend

## Assignment Operators
1. Basic assignment: `=`
2. Combined operators: `+=`, `-=`, `*=`, `/=`, `%=`, `**=`

### Notes on Assignment Operators:
- Don't confuse `=` with comparison operators (`==`, `===`)
- Multiple assignments possible: `$x = $y = 10;`
- Assignment is by value, not reference

## String Operators
1. Concatenation: `.`
2. Concatenation assignment: `.=`

## Comparison Operators
1. Equal: `==`
2. Identical (strict equality): `===`
3. Not equal: `!=` or `<>`
4. Not identical: `!==`
5. Less than: `<`
6. Greater than: `>`
7. Less than or equal to: `<=`
8. Greater than or equal to: `>=`
9. Spaceship operator: `<=>`

### Notes on Comparison Operators:
- Strict comparison (`===`, `!==`) checks value and type
- PHP 8 changed string-to-number comparison behavior
- Use strict comparisons when possible to avoid issues

## Conditional Operators
1. Ternary operator: `? :`
2. Null coalescing operator: `??`

### Notes on Conditional Operators:
- Ternary operator is a shorthand for if-else
- Use parentheses when nesting ternary operators
- Null coalescing operator useful for working with null values and undefined variables/array keys

## Examples
```php
// Arithmetic
$x = 10;
$y = 3;
var_dump($x + $y);  // 13
var_dump($x % $y);  // 1
var_dump($x ** $y); // 1000

// Assignment
$x += 5; // Same as $x = $x + 5;

// Comparison
var_dump(5 === "5"); // false (strict comparison)
var_dump(0 == "hello"); // false in PHP 8, true in PHP 7.4

// Ternary
$result = ($x > $y) ? "x is greater" : "y is greater or equal";

// Null coalescing
$name = $_GET['name'] ?? 'Guest';
```

## Key Takeaways
- Understand the difference between loose and strict comparisons
- Be aware of PHP version differences in comparison behavior
- Use strict comparisons and typing when possible to avoid unexpected results
- Ternary and null coalescing operators can make code more concise, but use judiciously for readability
