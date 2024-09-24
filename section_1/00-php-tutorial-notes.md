# PHP Basics

## Setup
- PHP files must end with .php extension
- Open project directory in code editor from htdocs folder
- Create index.php file

## PHP Syntax
- PHP code is enclosed in <?php ?> tags
  - Closing ?> tag is optional if entire file is PHP (prevents accidental whitespace)
- Statements end with semicolon ;
  - Semicolon not needed before ?> closing tag
- echo and print used to output text
  - echo faster, can take multiple comma-separated arguments 
  - print has return value, so can be used in expressions
- Single vs double quoted strings
  - Variables expanded in double quotes, not single quotes
  - Escape single quote with backslash in single quoted string
  
## Variables  
- Start with $ sign - e.g. $name = "Geo";
- Must start with letter or underscore, then letters, numbers, underscore
- Cannot use reserved words like 'this'
- Assigned by value by default
  - Original not affected by changes to copy
- Assign by reference with & to link variables
- Embed variables in strings with {} or concatenate with . operator

## Embedding PHP in HTML
- Include PHP tags <?php ?> inside HTML
- Shortcut <?= ?> for "echo"  
- Can output HTML from PHP echo/print statements

## Comments
- Single line: // or #
- Multi-line: /* */ 
- Don't nest multi-line comments
- Inline comment after closing ?> tag doesn't comment out code after it

