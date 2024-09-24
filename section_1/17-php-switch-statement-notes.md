# PHP Switch Statement

## Basic Structure
```php
switch (expression) {
    case value1:
        // code to be executed if expression == value1
        break;
    case value2:
        // code to be executed if expression == value2
        break;
    // ...
    default:
        // code to be executed if expression doesn't match any case
}
```

## Key Points
1. Compares an expression against multiple values
2. Executes code block of the first matching case
3. Uses loose comparison (==) not strict comparison (===)
4. Default case is optional and executed if no match is found

## Break Statement
- Exits the switch block when a case is matched
- Without break, execution continues to subsequent cases ("fall-through" behavior)
- Useful for executing same code for multiple cases

## Comparison with If-Else
- Switch expression is evaluated only once
- Can be more efficient for multiple comparisons against the same variable

## Usage in Loops
- Break in switch only exits the switch, not the surrounding loop
- Use `break 2;` to exit both switch and loop
- `continue` can be used similarly with an argument

## Performance Considerations
- More efficient than multiple if-else statements when comparing a single variable against multiple values
- Especially useful when the comparison involves a function call or complex expression

## Example
```php
$status = 'paid';
switch ($status) {
    case 'paid':
    case 'processed':
        echo "Payment successful";
        break;
    case 'declined':
    case 'failed':
        echo "Payment unsuccessful";
        break;
    default:
        echo "Unknown payment status";
}
```

## Best Practices
1. Always use break unless fall-through is intentional
2. Consider readability when choosing between switch and if-else
3. Use switch when comparing a single variable against multiple values
4. Be aware of type coercion in comparisons
