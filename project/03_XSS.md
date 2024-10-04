# Cross-Site Scripting (XSS) Attacks

## Definition

- XSS attacks are a type of injection where malicious scripts are injected into trusted websites
- Attackers use web applications to send malicious code (usually browser-side scripts) to different end users

## Vulnerability

- Occurs when web applications use user input in output without proper validation or encoding
- Widespread due to lack of proper input handling

## Example Scenario

- Registration form in an expense app
- User can inject HTML or JavaScript code in input fields (e.g., name field)

## Potential Dangers

- Inject harmful code
- Make AJAX requests to steal cookies or sensitive data
- Redirect users
- Perform actions on user's behalf
- Make site unusable

## Types of XSS Attacks

- Can occur in HTML, JavaScript, CSS, URL contexts

## Protection Methods

1. Never trust user input
2. Properly escape or encode output
3. Use templating engines with built-in XSS protection (e.g., Twig, Laravel Blade)

## Twig Protection

- Auto-escaping enabled by default
- Uses `htmlspecialchars()` function behind the scenes
- Converts special characters to HTML entities

## Manual Escaping in PHP

- Use `htmlspecialchars()` function
- Example: `htmlspecialchars($username, ENT_QUOTES, 'UTF-8')`

## Sanitization vs. Escaping

- Sanitizing input (stripping tags) not always ideal
- May interfere with legitimate user content for example, a blog post with HTML tags, greater-than, less-than signs
- Better to save raw data and escape on output

## Context-Specific Escaping

- Different escaping needed for HTML body, attributes, JavaScript, CSS, URLs
- Twig provides context-specific filters (e.g., `escape('html_attr')`)

## Best Practices

- Use templating engines with built-in protection
- Always escape output in the appropriate context
- Stay informed about OWASP Top 10 vulnerabilities
- https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqa3lEZkdGSHp6M2lzT0xMaHo1VzgyZ1FWT3RoUXxBQ3Jtc0ttTFo3TUdyejNxLWgzZWMycV9mRVliQ0gyRmVxcFZmUE51SEtBeEdVRDRYc2lxTVZtSEx3WUV2SHF3T0dod1JJclp5UFdlbnh6ZG1mOTRGNmNVaDBfMXg0MGNqSlZfNjdmeWtuMS1CV2RTU0FtODU4NA&q=https%3A%2F%2Fowasp.org%2Fwww-project-top-ten%2F&v=gPU_jyKDYx0
- https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqblNJQ1VGYk9QSTFlS2djSlVtTWJLMUhEcm5VZ3xBQ3Jtc0ttSTZKZmdDUzZfSmlOLUNabkFySDlMVFd2UzBrdzFFaXd4ak1zaDlXWGo1QnlZSVFzLTNxQnRSVldVRHhtX0cxTnpFcDNIRFlLbTZsUm1QMFM4UEJHQ2lkRy1GTjRDRmMtNVlDdnN5OFBjc3AzYU9vUQ&q=https%3A%2F%2Fowasp.org%2Fwww-community%2Fattacks%2Fxss%2F&v=gPU_jyKDYx0