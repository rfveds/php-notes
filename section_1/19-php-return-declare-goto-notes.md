# PHP Return, Declare, and Goto Statements

## Return Statement

1. Purpose: Returns control from a function to the calling code
2. Usage in functions:
   - Stops function execution
   - Returns the value of the given expression
   - Example: `return $x + $y;`
3. Usage in global scope:
   - Stops execution of the entire script
   - Optional expression (returns null if omitted)

## Declare Statement

1. Purpose: Sets execution directives for a block of code
2. Three directives:
   a. ticks: Defines a tick event frequency
   b. encoding: Specifies script encoding (rarely used)
   c. strict_types: Enables strict type checking

3. Ticks directive:
   - Used for low-level statement execution events
   - Example:
     ```php
     declare(ticks=3);
     register_tick_function('onTick');
     ```
   - Limited practical use cases (e.g., benchmarking)

4. Strict types directive:
   - Enables strict type checking for function calls
   - Example: `declare(strict_types=1);`
   - Applies only to the current file
   - Must be declared in both calling and called files for full effect

5. Scope:
   - Applies to code below the declare statement
   - Does not apply to included/required files automatically

## Goto Statement

1. Not recommended for use in modern PHP programming
2. Can lead to confusing and hard-to-maintain code

## Key Takeaways

1. Use return statements to exit functions and return values
2. Consider using strict_types declare for better type safety
3. Be aware of the scope limitations of declare statements
4. Avoid using goto statements in your code

## Example
```php
declare(strict_types=1);

function sum(int $x, int $y) {
    return $x + $y;
}

echo sum(5, 10);  // Works
echo sum('5', 10);  // Throws TypeError due to strict typing
```
