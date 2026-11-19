# GEMINI.md — PHP Web Application Development

## 1. General Principles

- Build secure, maintainable, lightweight PHP web applications.
- Follow SOLID principles where appropriate without overengineering.
- Prefer simple, readable solutions over unnecessary abstractions.
- Follow existing project architecture and coding conventions.
- Do not introduce unnecessary dependencies or frameworks.
- Do not rewrite existing functionality unless explicitly requested.
- Understand the existing codebase before making changes.
- Prioritize backward compatibility.

## 2. PHP Standards

- Use PHP 8.3 or newer.
- Follow PSR-12 coding standards.
- Use strict typing (`declare(strict_types=1);`) where practical.
- Use type declarations for function parameters, return values, and properties.
- Prefer constructor property promotion where appropriate.
- Use namespaces and autoloading (PSR-4) when appropriate.
- Prefer exceptions for exceptional conditions.
- Avoid deprecated PHP functions and language features.
- Avoid excessive inheritance and unnecessary design patterns.
- Use Composer for dependency management and autoloading.
- Do not use `eval()`, `extract()`, or variable variables.

## 3. Architecture

- Keep business logic separate from presentation.
- Separate database access, business logic, request handling, and templates.
- Keep controllers lightweight.
- Move reusable business logic into service classes.
- Use repositories or dedicated data-access classes when they provide meaningful value.
- Avoid putting complex business logic directly in templates.
- Prefer dependency injection over global state.
- Avoid unnecessary architectural layers for small applications.
- Follow the existing architecture instead of imposing a new one.

## 4. Database

- Use PDO for database access unless the project already uses another established abstraction.
- Use prepared statements for all queries containing dynamic values.
- Never concatenate untrusted input into SQL queries.
- Use transactions for operations involving multiple related database changes.
- Handle database errors appropriately.
- Add indexes for frequently queried columns when justified.
- Avoid N+1 query problems.
- Use database constraints to enforce data integrity.
- Store timestamps consistently, preferably in UTC.
- Use migrations for schema changes when the project has a migration system.
- Never modify production data or schema without explicit authorization.

## 5. Security

- Treat all external input as untrusted.
- Validate and sanitize input according to its intended use.
- Escape output according to its context.
- Use `htmlspecialchars()` with appropriate flags for HTML output.
- Prevent SQL injection through prepared statements.
- Protect against Cross-Site Scripting (XSS).
- Implement CSRF protection for state-changing requests.
- Use secure session configuration:
  - `HttpOnly`
  - `Secure` when using HTTPS
  - `SameSite`
  - Session ID regeneration after authentication.
- Use `password_hash()` and `password_verify()` for passwords.
- Never store passwords in plaintext.
- Enforce authorization on the server side.
- Do not rely on frontend validation for security.
- Restrict file uploads by type, size, and content.
- Store uploaded files outside publicly accessible directories when possible.
- Never expose configuration files, logs, backups, or environment secrets.
- Never commit credentials, API keys, or passwords.
- Avoid exposing stack traces or sensitive error details to users.

## 6. HTTP and Request Handling

- Follow HTTP conventions and appropriate status codes.
- Validate request methods and content types.
- Distinguish GET, POST, PUT, PATCH, and DELETE operations where appropriate.
- Use POST/Redirect/GET for traditional form submissions.
- Return consistent JSON structures for API endpoints.
- Validate all route parameters and request payloads.
- Handle missing resources with appropriate HTTP status codes.
- Do not trust client-provided user IDs or permission information.

## 7. Frontend Integration

- Read and follow `FRONTEND.md` whenever creating or modifying frontend code.
- Use semantic HTML5.
- Use Tailwind CSS for styling.
- Prefer Vanilla JavaScript.
- Use jQuery only when genuinely necessary.
- Use fetch() for asynchronous HTTP requests.
- Keep PHP business logic separate from HTML templates.
- Escape all dynamically rendered content.
- Provide meaningful validation and error messages.

## 8. Configuration and Environment

- Keep environment-specific configuration outside application code.
- Use environment variables for credentials and deployment settings.
- Never commit `.env` files containing secrets.
- Provide an `.env.example` with placeholder values when appropriate.
- Use separate development, testing, and production configurations.
- Fail safely when required configuration is missing.
- Never expose `phpinfo()` or development diagnostics in production.

## 9. Error Handling and Logging

- Use exceptions and centralized error handling where appropriate.
- Log errors with sufficient diagnostic context.
- Never display internal errors or stack traces to end users.
- Do not silently ignore exceptions.
- Avoid logging passwords, tokens, session IDs, or sensitive personal information.
- Configure production PHP with `display_errors=Off` and appropriate error logging.

## 10. Performance

- Avoid unnecessary database queries.
- Use pagination for large datasets.
- Optimize frequently executed SQL queries.
- Use caching when there is a measurable benefit.
- Avoid loading unnecessary Composer packages.
- Avoid unnecessary filesystem operations.
- Use streaming for large file downloads when appropriate.
- Do not optimize prematurely.

## 11. Testing

- Use PHPUnit for automated tests when appropriate.
- Test business logic independently from HTTP handling.
- Test authentication and authorization.
- Test input validation and security-sensitive functionality.
- Test error conditions and edge cases.
- Use a separate test database.
- Never run automated tests against production data.
- Run relevant tests after modifying existing functionality.
- Do not claim tests passed unless they were actually executed.

## 12. Dependencies

- Prefer native PHP functionality when sufficient.
- Use Composer for third-party packages.
- Review package maintenance, security, and compatibility before adding dependencies.
- Avoid introducing large frameworks for simple applications.
- Do not manually modify `vendor/`.
- Keep `composer.json` and `composer.lock` synchronized.
- Do not upgrade dependencies without a clear reason.

## 13. Git and Development Workflow

- Inspect the relevant files before modifying them.
- Make focused changes rather than unrelated refactoring.
- Preserve existing naming conventions and code structure.
- Do not overwrite user modifications.
- Never execute destructive Git commands without explicit authorization.
- Do not commit changes unless explicitly requested.
- Explain significant architectural or database changes.
- Update relevant documentation when functionality changes.

## 14. Final Checklist

Before completing a task:

- [ ] PHP syntax is valid.
- [ ] Existing functionality remains intact.
- [ ] Database queries use prepared statements.
- [ ] Input validation and output escaping are implemented.
- [ ] Authentication and authorization are enforced.
- [ ] CSRF protection is implemented where required.
- [ ] Errors are handled appropriately.
- [ ] No credentials or secrets are exposed.
- [ ] Frontend follows `FRONTEND.md`.
- [ ] Relevant tests have been executed.
- [ ] No unnecessary dependencies were introduced.
- [ ] Documentation is updated when necessary.
