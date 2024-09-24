# PHP File Inclusion

## Inclusion Statements
1. `include`: Includes and evaluates a file (warning on failure)
2. `require`: Includes and evaluates a file (error on failure, stops execution)
3. `include_once`: Includes file only if not already included
4. `require_once`: Requires file only if not already included

## Syntax
```php
include 'file.php';
require 'file.php';
include_once 'file.php';
require_once 'file.php';
```

## Key Differences
- `include` vs `require`: Error handling (warning vs fatal error)
- `_once` variants: Prevent multiple inclusions of the same file

## File Path Resolution
1. Checks `include_path` in php.ini
2. Looks in the current directory of the script

## Use Cases
1. Code reusability and organization
2. Splitting HTML templates (e.g., separating navigation)
3. Including configuration files
4. Defining reusable functions or classes

## Variable Scope
- Included files inherit the variable scope of the calling file
- Variables defined in the parent file are accessible in included files

## Return Values
- `include` returns `false` on failure, `1` on success
- Can use `return` statement in included files to return specific values

## Including Content in Strings
Use output control functions:
```php
ob_start();
include 'file.php';
$content = ob_get_clean();
```

## Best Practices
1. Use `require_once` for files with function/class definitions
2. Use `include` for optional files (e.g., templates)
3. Be cautious with variable modifications across files
4. Use relative or absolute paths for clarity

## Example: Template Inclusion
```php
<!DOCTYPE html>
<html>
<head>
    <title>My Page</title>
</head>
<body>
    <?php include 'partials/header.php'; ?>
    <main>
        <!-- Page-specific content -->
    </main>
    <?php include 'partials/footer.php'; ?>
</body>
</html>
```

## Key Takeaways
1. File inclusion helps in organizing and modularizing code
2. Choose the appropriate inclusion statement based on your needs
3. Be aware of variable scope when including files
4. Use output buffering to capture file contents as strings
5. Properly structure your project for clear and maintainable includes
