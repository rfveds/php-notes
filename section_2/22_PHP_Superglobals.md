### Superglobals in PHP
- Superglobals are built-in variables in PHP that are always accessible, regardless of scope.
- **Superglobals** are:
  - `$GLOBALS`
  - `$_SERVER` - Contains information about the server and the execution environment.
    - `$_SERVER['REQUEST_URI']` - Contains the URI of the current request.
  - `$_GET` 
  -   - Used to collect form data after submitting an HTML form with method="get" or to collect data sent in the URL.
  - `$_POST` 
      - Used to collect form data after submitting an HTML form with method="post".
      - If value with the same key is present in both $_GET and $_POST, $_POST will overwrite $_GET in $_REQUEST superglobal.
  - `$_FILES`
  - `$_COOKIE`
  - `$_SESSION`
  - `$_REQUEST`
  - `$_ENV`
