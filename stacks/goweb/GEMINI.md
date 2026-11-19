# GEMINI.md — Go Web Application

## 1. General Rules

- Use modern Go and standard library features whenever practical.
- Prefer simple, readable, maintainable code.
- Avoid unnecessary dependencies and frameworks.
- Follow Go conventions, formatting, and idiomatic practices.
- Use `gofmt` for all Go source files.
- Keep business logic separate from HTTP handlers.
- Handle errors explicitly. Never silently ignore errors.

## 2. Project Architecture

- Separate HTTP handlers, business logic, database access, and templates.
- Keep SQL queries and database schema definitions separate from Go source code.
- Store SQL files in a dedicated `sql/` directory.
- Use HTML templates for server-side rendering.
- Use Vanilla JavaScript and Tailwind CSS for frontend development.
- Follow `FRONTEND.md` if present.

Suggested structure:

```text
project/
├── GEMINI.md
├── FRONTEND.md
├── go.mod
├── main.go
├── sql/
│   ├── schema.sql
│   └── queries/
├── internal/
│   ├── handlers/
│   ├── services/
│   ├── database/
│   └── models/
├── templates/
├── static/
└── data/
    └── app.db
```

## 3. SQLite Database

- Use SQLite as the primary database.
- Prefer a lightweight, actively maintained SQLite driver.
- Keep schema definitions, migrations, and SQL queries in separate `.sql` files.
- Never embed SQL schema definitions inside Go source files.
- Use prepared statements for dynamic queries.
- Enable foreign key constraints.
- Use transactions for operations involving multiple related changes.
- Add appropriate indexes and constraints.
- Handle database errors explicitly.
- Use UTC for stored timestamps.

## 4. First-Run Initialization

Application startup must automatically verify and initialize the database.

Follow this sequence:

1. Check whether the configured SQLite database file exists.
2. If it does not exist, create the database.
3. Execute the SQL schema files to create the required tables.
4. If the database already exists, inspect its tables and columns.
5. Create missing tables and add missing columns without destroying existing data.
6. Apply any pending database migrations.
7. Check whether an administrator account exists.
8. If no administrator exists, activate first-run setup mode.
9. Display a **Create Admin** form in the web interface.
10. After successful admin creation, disable first-run setup mode and redirect to the login page.

Additional rules:

- Database initialization must be idempotent.
- Never drop tables or columns automatically.
- Never overwrite existing user data.
- Use schema versioning to track database changes.
- Use explicit migrations for schema modifications.
- Ensure initialization is safe against concurrent startup attempts.
- Do not allow normal application access to administrative functionality before the initial admin is created.
- Never use a hardcoded default administrator password.

## 5. Authentication and Security

- Use secure password hashing with Argon2id or bcrypt.
- Never store plaintext passwords.
- Use secure session management.
- Protect state-changing requests against CSRF.
- Validate all user input on the server.
- Escape dynamically rendered HTML.
- Enforce authentication and authorization on the backend.
- Use `HttpOnly`, `Secure` (under HTTPS), and `SameSite` session cookies.
- Never expose database files or configuration files through HTTP.
- Protect the Create Admin endpoint so it is accessible only during first-run setup.
- Prevent multiple administrator accounts from being created through the initial setup process.

## 6. HTTP and Frontend

- Use Go's standard `net/http` package unless a router provides meaningful benefits.
- Use Go `html/template` for server-side rendering.
- Follow REST conventions.
- Return appropriate HTTP status codes.
- Use Vanilla JavaScript by default.
- Use Tailwind CSS for styling.
- Keep frontend assets separate from backend code.
- Create responsive, accessible interfaces.
- Follow `FRONTEND.md` when available.

## 7. Testing and Quality

- Write unit tests for business logic.
- Test database initialization and migrations.
- Test first-run behavior with a new database.
- Test upgrades using existing databases.
- Test missing tables and columns.
- Test initial admin creation and duplicate prevention.
- Run `go test ./...` after relevant changes.
- Run `go vet ./...`.
- Do not claim tests passed unless they were executed.

## 8. Development Principles

- Avoid unnecessary abstractions and overengineering.
- Prefer explicit, straightforward code.
- Keep functions small and focused.
- Do not introduce dependencies without justification.
- Preserve existing functionality when modifying code.
- Do not execute destructive database operations without explicit authorization.

