# PHP Match Expression (PHP 8+)

## Basic Structure
```php
$result = match (expression) {
    value1 => returnExpression1,
    value2, value3 => returnExpression2,
    default => defaultExpression,
};
```

## Key Differences from Switch Statement
1. Match is an expression that returns a value
2. No need for break statements
3. Default case is required (exhaustive matching)
4. Uses strict comparison (===)

## Features
1. Can be assigned to a variable
2. Supports multiple conditions per case (comma-separated)
3. Both sides are expressions and can be complex

## Examples
```php
$status = 1;
$result = match ($status) {
    1 => 'Paid',
    2, 3 => 'Payment declined',
    0 => 'Pending payment',
    default => 'Unknown payment status',
};
```

## Use Cases
- Simpler syntax for straightforward value matching
- When strict comparison is needed
- For concise, expression-based branching

## Limitations
- Cannot contain multiple statements per case
- For multiple statements, use a function call as the return expression

## Comparison with Switch and If-Else
- More concise than switch for simple matches
- Stricter than switch (type-safe comparisons)
- More readable than nested if-else for multiple conditions
- Switch still useful for complex, multi-statement cases

## Best Practices
1. Use match for simple, expression-based comparisons
2. Prefer match over switch when strict comparison is needed
3. Always include a default case
4. Extract complex logic into functions for use with match

## Note
Match expression is available only in PHP 8 and later versions.
