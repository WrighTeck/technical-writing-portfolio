# TypeScript for QA Professionals

TypeScript is a strongly typed superset of JavaScript that improves code reliability and maintainability.

For QA professionals, TypeScript is especially useful in modern automation frameworks such as:

- WebdriverIO
- Playwright
- Cypress (with TS support)

This guide focuses on practical TypeScript concepts relevant to testing, automation, and API validation.

---

# 1. Why TypeScript Matters in QA

TypeScript helps QA engineers:

- Prevent runtime errors through static typing
- Write structured automation code
- Improve test readability and maintainability
- Validate API response structures
- Scale automation frameworks safely

---

# 2. Basic Type Annotations

Type annotations define expected data types and prevent incorrect assignments.

```typescript
// Variable declarations with explicit types
let username: string = "qaUser";     // string type
let retryLimit: number = 3;          // numeric type
let isLoggedIn: boolean = false;     // boolean type
```

# 3. Functions with Typed Parameters

TypeScript allows typing of both parameters and return values.

```typescript
// Function with typed parameter and return type
function validateStatus(code: number): boolean {
  return code === 200;
}
```
This ensures only numbers are passed into the function.

# 4. Functions with Typed Parameters

Interfaces define the expected structure of objects.

```typescript
// Define expected API response structure
interface User {
  id: number;
  name: string;
  active: boolean;
}

// Assign object to interface
const user: User = {
  id: 1,
  name: "Jane",
  active: true
};
```
If the structure does not match the interface, TypeScript will flag an error.

# 5. Working with Arrays

TypeScript ensures array type consistency.

```typescript
// Array of strings
let emails: string[] = ["a@test.com", "b@test.com"];

// Loop through array
for (let email of emails) {
  console.log(email);
}
```
This prevents mixed-type array issues.

# 6. Async/Await (Automation & API Calls)

Most automation and API interactions are asynchronous.

```typescript
async function fetchUserData(): Promise<any> {
  const response = await fetch("https://api.example.com/users");
  return response.json();
}
```

# 7.Type Safety in Automation Assertions

```typescript
function assertUserActive(user: User): boolean {
  return user.active === true;
}
```

# 8.Example: Automation Logic

This example demonstrates structured validation of an authentication response.

```typescript

interface LoginResponse {
  status: number;
  token: string;
}

function validateLogin(response: LoginResponse): boolean {
  return response.status === 200 && response.token.length > 0;
}

```

# 9. Common TypeScript Types Used in QA

The following matrix highlights frequently used TypeScript types and how they apply in real-world QA and automation scenarios.

| Type        | Description | Example | QA Use Case |
|------------|------------|---------|-------------|
| `string`   | Text-based values | `let token: string = "abc123";` | Validate authentication tokens, user IDs, error messages |
| `number`   | Numeric values | `let statusCode: number = 200;` | Validate API status codes, retry limits, counts |
| `boolean`  | True/False values | `let isActive: boolean = true;` | Feature flags, login state, validation checks |
| `array`    | Collection of values | `let users: string[] = ["A", "B"];` | Validate lists of users, products, records |
| `interface`| Defines object structure | `interface User { id: number; }` | Validate structured API responses |
| `type`     | Custom type alias | `type Status = "success" | "error";` | Restrict expected API response values |
| `enum`     | Named constant set | `enum Role { Admin, User }` | Validate role-based access logic |
| `Promise`  | Represents async operation | `Promise<string>` | API calls, async automation steps |
| `any`      | Disables type checking | `let data: any;` | Temporary placeholder (use cautiously) |
| `unknown`  | Safer alternative to `any` | `let input: unknown;` | Validate dynamic API data safely |
