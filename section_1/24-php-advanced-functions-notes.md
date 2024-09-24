# PHP Advanced Function Concepts

## Variable Functions
- Call functions using variables: `$funcName = 'myFunc'; $funcName();`
- Use `is_callable()` to check if a variable can be called as a function
- Doesn't work with language constructs (e.g., echo, include)

## Anonymous Functions (Lambda Functions)
- Functions without names: `$sum = function($a, $b) { return $a + $b; };`
- Must end with a semicolon
- Can be assigned to variables or passed as arguments

## Closures
- Anonymous functions that can access variables from the parent scope
- Use the `use` keyword: `function() use ($x) { ... }`
- Variables are copied by value unless passed by reference

## Callable Type and Callback Functions
- `callable` is a data type for functions that can be called
- Callback functions are passed as arguments to other functions
- Ways to pass callbacks:
  1. Anonymous function
  2. Variable containing an anonymous function
  3. String with function name

## Arrow Functions (PHP 7.4+)
- Shorthand syntax for anonymous functions
- Syntax: `fn($x) => $x * 2`
- Automatically capture variables from parent scope
- Single expression only, implicit return

## Key Differences and Features
1. Variable Functions:
   - Call functions dynamically
   - Useful for plugins or dynamic method calls

2. Anonymous Functions:
   - Can be used inline or assigned to variables
   - Useful for callbacks and one-time use functions

3. Closures:
   - Access parent scope variables
   - Useful for maintaining state or creating factory functions

4. Arrow Functions:
   - Concise syntax for simple functions
   - Automatically capture parent scope variables
   - Useful for short callbacks in array functions

## Examples
```php
// Variable function
$func = 'strtoupper';
echo $func('hello'); // HELLO

// Anonymous function
$greet = function($name) {
    return "Hello, $name!";
};
echo $greet('Alice'); // Hello, Alice!

// Closure
$x = 10;
$addX = function($n) use ($x) {
    return $n + $x;
};
echo $addX(5); // 15

// Arrow function
$numbers = [1, 2, 3, 4];
$squared = array_map(fn($n) => $n * $n, $numbers);
print_r($squared); // [1, 4, 9, 16]
```

## Best Practices
1. Use arrow functions for short, simple callbacks
2. Use closures when you need to access parent scope variables
3. Use variable functions carefully and check with `is_callable()`
4. Prefer named functions for complex or reusable logic
5. Use type hinting (e.g., `callable`) for function arguments expecting callbacks

