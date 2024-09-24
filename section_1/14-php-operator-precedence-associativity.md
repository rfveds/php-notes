# PHP Operator Precedence and Associativity

## Introduction
- When multiple operators are used in an expression, they are grouped by their precedence
- If operators have the same precedence, their associativity determines how they are grouped

## Precedence
- Operators with higher precedence are executed first
- Precedence can be overridden using parentheses

Example:
```php
$x = 5 + 3 * 5;  // Result: 20 (3 * 5 is executed first)
$x = (5 + 3) * 5;  // Result: 40 (parentheses force 5 + 3 to be executed first)
```

## Associativity
- Determines the order of execution for operators with the same precedence
- Can be:
  1. Left associative: Grouped from left to right
  2. Right associative: Grouped from right to left
  3. Non-associative: Cannot be used next to each other

Examples:
1. Right associative (assignment):
   ```php
   $x = $y = 5;  // Equivalent to $x = ($y = 5)
   ```

2. Left associative (multiplication and division):
   ```php
   $result = $x / $y * $z;  // Equivalent to ($x / $y) * $z
   ```

## Precedence Table
- Operators are listed from highest to lowest precedence
- Operators on the same line have the same precedence

## Logical Operators
- `&&` has higher precedence than `||`
- `and` and `or` have lower precedence than most operators, including assignment

Example:
```php
$x = true;
$y = false;
$z = $x and $y;  // $z is true because ($x and $y) is evaluated after the assignment
$z = ($x and $y);  // $z is false because of the parentheses
```

## Best Practices
1. Use parentheses to make the intended order of operations clear
2. Don't rely solely on operator precedence for complex expressions
3. Be especially careful with `and` and `or` keywords vs. `&&` and `||` operators

## Key Takeaways
- Understanding operator precedence and associativity is crucial for writing correct PHP code
- When in doubt, use parentheses to ensure the desired order of operations
- Be aware of the differences between symbolic (`&&`, `||`) and keyword (`and`, `or`) logical operators

