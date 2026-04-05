# Acceptance Criteria for Requirements 

## What is Acceptance Criteria?

Acceptance criteria define the specific conditions that a feature must meet to be considered complete and working as expected.

They provide a clear understanding of what needs to be tested and validated.

---

## Why Acceptance Criteria Matter?

Clear acceptance criteria help:
- Ensure alignment between QA, developers, and stakeholders
- Define what “done” looks like
- Reduce ambiguity and assumptions
- Improve test coverage and accuracy
- Prevent defects from reaching production

---

## Example of Acceptance Criteria

### Scenario: User Login

**Acceptance Criteria:**
- User can enter a valid username and password
- User is redirected to the dashboard after successful login
- An error message is displayed for invalid credentials
- The login button is disabled when fields are empty

# Acceptance Criteria (BDD Style Examples)

## 🔐 User Login

### Scenario: Successful login
**Given** the user is on the login page  
**When** the user enters a valid username and password  
**Then** the user is redirected to the dashboard  

### Scenario: Invalid login
**Given** the user is on the login page  
**When** the user enters invalid credentials  
**Then** an error message "Invalid username or password" is displayed  

---

## 🎯 Key Takeaway

Clear, structured acceptance criteria using Given / When / Then improve communication, ensure testability, and help teams deliver quality software efficiently.


## Good vs Bad Acceptance Criteria

### ❌ Unclear
- "Login should work properly."

### ✅ Clear
- "User is redirected to dashboard after entering valid credentials."
- "Error message 'Invalid username or password' is displayed for incorrect login attempts."

---

## Common Issues

- Missing acceptance criteria
- Vague or incomplete descriptions
- No expected outcomes defined
- Lack of edge case coverage

---

## QA Validation Checklist

QA should ensure:
- Acceptance criteria are clear and testable
- All scenarios are covered
- Expected results are defined
- Edge cases are included
- Requirements align with actual functionality

---

## Key Takeaway

Strong testing starts with clear acceptance criteria.

Without it, testing becomes guesswork. With it, testing becomes structured, efficient, and reliable.
