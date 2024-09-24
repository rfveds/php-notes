# CSRF (Cross-Site Request Forgery) Protection Notes

## What is CSRF?

- An attack that forces an authenticated user to execute unwanted actions on a web application
- Involves forged requests made on the user's behalf without their intention
- Can lead to unauthorized state-changing requests (e.g., fund transfers, email changes)

## How CSRF Works

1. User logs into a website
2. Attacker tricks user into clicking a malicious link
3. Malicious script executes, making a forged request
4. Request carries over the user's session cookie
5. Server sees the request as authenticated and legitimate

## CSRF Attack Methods

- Man-in-the-middle attacks
- Injected JavaScript via XSS vulnerability
- Requests from another site to the target website

## CSRF Prevention Techniques

1. Synchronizer Token Pattern
    - Generate unique, unpredictable tokens on the server
    - Attach tokens to requests (form fields or custom headers)
    - Server validates tokens on state-changing requests

2. Same-Site, Secure, and HTTP-Only Cookie Options
    - Help prevent CSRF but shouldn't be the only protection

3. Use existing framework protection or open-source libraries

## Implementing CSRF Protection with Slim PHP

1. Install Slim CSRF package: `composer require slim/csrf`
2. Register CSRF in container bindings
3. Add CSRF middleware to the application
4. Include CSRF token fields in forms
5. Create a middleware to pass CSRF fields to templates

## Best Practices

- Generate tokens per page load or session, not per request
- Validate tokens on POST, PUT, DELETE, and PATCH requests
- Use both CSRF tokens and secure cookie options for layered security
- Consider custom error handling for failed CSRF checks

## Implementation Tips

- Use hidden form fields to include CSRF tokens
- For AJAX requests, use custom HTTP headers
- Create reusable template functions for CSRF fields
- Disable escaping when rendering CSRF fields in templates