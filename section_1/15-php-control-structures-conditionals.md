# PHP Control Structures: Conditionals

## Introduction
- Control structures group statements and control code execution flow
- They allow executing code based on conditions or repeating code

## If Statements

### Basic Syntax
```php
if (condition) {
    // code to execute if condition is true
}
```

### If-Else
```php
if (condition) {
    // code to execute if condition is true
} else {
    // code to execute if condition is false
}
```

### If-Elseif-Else
```php
if (condition1) {
    // code for condition1
} elseif (condition2) {
    // code for condition2
} else {
    // code if no conditions are true
}
```

### Nested If Statements
```php
if (outerCondition) {
    if (innerCondition) {
        // nested code
    }
}
```

## Best Practices
1. Always use curly braces for readability, even for single-line statements
2. Use `elseif` (one word) for better readability and consistency

## Alternative Syntax for HTML Embedding

### Standard PHP tags in HTML
```php
<?php
if ($condition) {
    echo "HTML content";
} else {
    echo "Other HTML content";
}
?>
```

### Alternative Syntax
```php
<?php if ($condition): ?>
    HTML content
<?php elseif ($anotherCondition): ?>
    Other HTML content
<?php else: ?>
    Default HTML content
<?php endif; ?>
```

Key points:
- Use `:` instead of `{`
- Use `endif;` to close the if statement
- Allows for cleaner integration of PHP and HTML

## Example: Simple Grading System
```php
<?php
$score = 85;

if ($score >= 90):
?>
    <p style="color: green;">A</p>
<?php elseif ($score >= 80): ?>
    <p>B</p>
<?php elseif ($score >= 70): ?>
    <p>C</p>
<?php elseif ($score >= 60): ?>
    <p>D</p>
<?php else: ?>
    <p style="color: red;">F</p>
<?php endif; ?>
```

## Key Takeaways
1. Conditional statements allow for decision-making in code
2. Multiple conditions can be chained using `elseif`
3. Alternative syntax provides cleaner integration with HTML
4. Always consider readability when choosing between standard and alternative syntax
