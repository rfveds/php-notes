# PHP Types and Typecasting

## PHP Type System

1. Dynamically (weakly) typed language
   - Type checking happens at runtime
   - Variable types can change after definition
   - More flexible but can impact performance and lead to unexpected bugs

2. 10 Primitive Types:
   - 4 Scalar Types: boolean, integer, float, string
   - 4 Compound Types: array, object, callable, iterable
   - 2 Special Types: resource, null

3. 2 Pseudotypes (for readability): mixed, void

## Scalar Types

1. Boolean: 
   - Represents truth value (true or false)
   - Prints as 1 for true, blank for false

2. Integer: 
   - Whole numbers without decimal points
   - Examples: 1, 2, 3, 0, -5

3. Float (double/decimal): 
   - Numbers with decimal points
   - Examples: 1.5, 0.1, 0.005, -15.8

4. String: 
   - Series of characters enclosed in single or double quotes
   - Example: "Hello, world!"

## Checking Variable Types

1. `get_type()` function:
   - Returns the type of a variable
   - Example: `echo get_type($variable);`

2. `var_dump()` function:
   - Prints variable type and value
   - Example: `var_dump($variable);`

## Compound Types

1. Array:
   - List of items, can contain mixed types
   - Example: `$array = [1, 2, 3, 0.5, -9.2, "string", true];`
   - Print using `print_r()` function

2. Objects, Callables, Iterables:
   - Advanced types (covered in separate lessons)

## Type Hinting and Strict Mode

1. Type Hinting:
   - Specify expected types for function parameters
   - Example: `function sum(int $x, int $y)`

2. Type Juggling/Coercion:
   - PHP attempts to convert types automatically

3. Strict Mode:
   - Enabled with `declare(strict_types=1);`
   - Throws errors for mismatched types
   - Exception: Integers accepted for float type hints

## Typecasting

- Force a variable to a specific type
- Syntax: `(type)$variable`
- Example: `(int)"5"` casts string "5" to integer 5

## Key Takeaways

- PHP automatically determines variable types
- Use type hinting and strict mode for better code quality
- Typecasting allows forced type conversion
- Each type has specific behaviors and use cases
