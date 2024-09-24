# PHP Constants and Variable Variables

## Constants

1. Definition:
   - Values that cannot change once defined
   - Unlike variables, which can be overwritten

2. Ways to Define Constants:
   a. Using `define()` function:
      - Syntax: `define('CONSTANT_NAME', value)`
      - Example: `define('STATUS_PAID', 'paid')`
      - Can be defined within control structures (e.g., if statements)
      - Can use variables for constant names

   b. Using `const` keyword:
      - Syntax: `const CONSTANT_NAME = value;`
      - Example: `const STATUS_PAID = 'paid';`
      - Defined at compile time (cannot be used in control structures)

3. Naming Conventions:
   - Can start with letters or underscores
   - Cannot contain special characters
   - Case-sensitive
   - Convention: Use all uppercase (e.g., STATUS_PAID)

4. Usage:
   - Reference without $ sign: `echo STATUS_PAID;`
   - Check if defined: `defined('CONSTANT_NAME')`

5. Use Cases:
   - For static data that doesn't change often
   - Examples: statuses, configuration values

6. Predefined Constants:
   - PHP provides built-in constants
   - Example: `PHP_VERSION` (prints PHP version)

7. Magic Constants:
   - Value changes depending on where they're used
   - Examples:
     - `__LINE__`: Current line number
     - `__FILE__`: Full path of current file

## Variable Variables

1. Definition:
   - Uses the value of one variable as the name of another variable

2. Syntax:
   - Basic: `$$variableName`
   - Example:
     ```php
     $foo = 'bar';
     $$foo = 'baz';  // Creates $bar = 'baz'
     ```

3. Usage:
   - Allows dynamic creation of variable names
   - Useful for flexible, dynamic code

4. Printing Variable Variables:
   - Basic: `echo $$foo;`
   - Within strings: `echo "${$foo}";` or `echo "{$$foo}";`

5. Advanced Usage:
   - Can be used with arrays and objects (covered in later lessons)

## Key Takeaways

- Constants are immutable once defined
- Use constants for values that shouldn't change
- Variable variables allow dynamic variable creation
- Be cautious with variable variables to maintain code readability
