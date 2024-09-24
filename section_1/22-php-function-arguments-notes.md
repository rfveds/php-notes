# PHP Function Arguments and Advanced Concepts

## Basic Function Arguments
- Define parameters in function definition: `function foo($x, $y)`
- Pass arguments when calling: `foo(5, 10)`
- Parameters vs Arguments: Parameters are in definition, arguments are passed values

## Type Hinting
- Specify expected types: `function foo(int $x, float $y)`
- Use `declare(strict_types=1);` for strict type checking
- Union types (PHP 8+): `function foo(int|float $x)`

## Default Values
- Set default values: `function foo($x, $y = 10)`
- Must come after non-optional parameters

## Pass by Reference
- Use `&` before parameter: `function foo(&$x)`
- Modifies the original variable

## Variadic Functions (Splat Operator)
- Accept variable number of arguments: `function sum(...$numbers)`
- Captures arguments in an array
- Can be used after fixed parameters: `function sum($x, $y, ...$numbers)`
- Type hinting possible: `function sum(int ...$numbers)`

## Argument Unpacking
- Unpack arrays into argument list: `sum(...$array)`
- Works with associative arrays for named arguments

## Named Arguments (PHP 8+)
- Pass arguments by parameter name: `foo(y: 10, x: 5)`
- Order doesn't matter
- Useful for functions with many optional parameters
- Can be combined with positional arguments (named must come last)

## Key Points
1. Named arguments improve readability and flexibility
2. Splat operator useful for variable-length argument lists
3. Type hinting enhances code reliability, especially with strict types
4. Default values make functions more flexible
5. Pass by reference allows functions to modify original variables

## Examples
```php
// Variadic function with type hinting
function sum(int|float ...$numbers) {
    return array_sum($numbers);
}

echo sum(1, 2, 3, 4); // 10

// Named arguments
function setConfig($host, $port = 8080, $timeout = 30) {
    // ...
}

setConfig(port: 9000, host: 'localhost');

// Argument unpacking
$config = ['localhost', 9000];
setConfig(...$config);
```

## Best Practices
1. Use type hinting for better code reliability
2. Consider using named arguments for functions with many parameters
3. Use variadic functions for flexible argument handling
4. Be cautious with pass-by-reference to avoid unexpected side effects
5. Leverage union types for more flexible type hinting
