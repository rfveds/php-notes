# PHP Variable Scope and Static Variables

## Variable Scope

### Global Scope
- Variables defined outside of functions
- Accessible throughout the script and included/required files
- Example: `$x = 5;`

### Local Scope
- Variables defined within functions
- Only accessible within the function
- Example: `function foo() { $y = 10; }`

## Accessing Global Variables in Functions

1. Pass as parameters:
   ```php
   function foo($x) { echo $x; }
   foo($globalVar);
   ```

2. Use `global` keyword:
   ```php
   function foo() {
       global $x;
       echo $x;
   }
   ```

3. Use `$GLOBALS` superglobal:
   ```php
   function foo() {
       echo $GLOBALS['x'];
   }
   ```

## Superglobals
- Predefined PHP variables accessible from any scope
- Examples: `$_GET`, `$_POST`, `$_SESSION`
- `$GLOBALS` is a superglobal containing all global variables

## Best Practices
- Avoid using global variables when possible
- Prefer passing parameters and returning values from functions

## Static Variables

### Definition
- Declared using the `static` keyword within a function
- Retain their value between function calls

### Syntax
```php
function counter() {
    static $count = 0;
    return ++$count;
}
```

### Use Cases
1. Caching expensive operations:
   ```php
   function getValue() {
       static $value = null;
       if ($value === null) {
           $value = expensiveOperation();
       }
       return $value;
   }
   ```

2. Maintaining state between function calls
3. Implementing singleton pattern in OOP

### Key Points
- Initialized only once
- Value persists between function calls
- Local to the function scope

## Examples

```php
// Global vs Local Scope
$globalVar = 5;

function scopeExample() {
    $localVar = 10;
    echo $localVar;  // Works
    echo $globalVar; // Undefined variable
}

// Static Variable
function countCalls() {
    static $calls = 0;
    return ++$calls;
}

echo countCalls(); // 1
echo countCalls(); // 2
```

## Key Takeaways
1. Understand the difference between global and local scope
2. Use function parameters and return values instead of global variables
3. Static variables are useful for caching and maintaining state
4. Be cautious with global variables and superglobals to avoid code complexity
