# Python for QA Professionals

Python is a practical language for QA because it’s great for:
- Writing quick validation scripts
- Parsing logs and test data
- API testing and response validation
- Lightweight automation utilities

This guide focuses on Python concepts that QA professionals use most often.

---

## 1. Variables & Common Data Types

Python does not require type declarations, but clean naming matters in QA scripts.

```python
# Variables (common QA examples)
username = "qa_user"          # string: login username
retry_limit = 3               # integer: max retries for flaky calls
timeout_seconds = 10.5        # float: timeouts for network operations
is_active = True              # boolean: feature flag or account state
```
## 2. Conditional Logic

Conditional logic is used to validate outcomes like API responses, status codes, or UI state.
```python
# Conditional logic (QA validation example)
status_code = 200  # simulate API response status code

if status_code == 200:
    print("PASS: Request succeeded")   # expected success path
else:
    print("FAIL: Request failed")      # unexpected failure path
```
## 3. Lists & Dictionaries (Common in API Testing)

API responses often come back as lists of objects (records).

```python
# List of dictionaries (similar to JSON records)
users = [
    {"id": 1, "email": "a@test.com", "active": True},
    {"id": 2, "email": "b@test.com", "active": False},
]

print(users[0]["email"])  # access first user's email
```
## 4. Loops for Data Validation

API responses often come back as lists of objects (records).

```python
# List of dictionaries (similar to JSON records)
users = [
    {"id": 1, "email": "a@test.com", "active": True},
    {"id": 2, "email": "b@test.com", "active": False},
]

print(users[0]["email"])  # access first user's email
```
## 5. Functions (Reusable)
Functions keep validation logic reusable and clean.

```python
# Reusable validation function
def validate_status(code: int) -> bool:
    """Return True if status code indicates success."""
    return code == 200

print(validate_status(200))  # True
print(validate_status(500))  # False
```

## 6. Working with JSON (API Response Parsing)
QA often needs to parse JSON response bodies.

```python
import json

# JSON string (similar to what an API might return)
data = '{"id": 10, "name": "Jane", "active": true}'

parsed = json.loads(data)          # convert JSON string to dict
print(parsed["name"])              # access a field
print(parsed["active"])            # validate boolean value
```

## 7. Basic File Handling (Logs & Test Data)
Reading logs is common during defect investigation.

```python
# Read a log file (example)
with open("app.log", "r") as file:
    lines = file.readlines()  # read all lines into a list

print(lines[:5])  # preview first 5 log lines
```

## 8. Exception Handling (Prevent Script Failures)

```python
# Graceful error handling example
try:
    result = 10 / 0  # this will raise an error
except ZeroDivisionError:
    print("ERROR: Division by zero detected (invalid calculation).")
```
## 9. Common Python Concepts Used in QA

The following matrix highlights frequently used Python concepts and how they apply in real-world QA and automation scenarios.

| Concept        | Description | Example | QA Use Case |
|---------------|------------|---------|-------------|
| Variables     | Store values in memory | `token = "abc123"` | Store session tokens, usernames, IDs |
| Strings       | Text data type | `error_message = "Invalid login"` | Validate error responses or UI messages |
| Integers      | Whole numbers | `status_code = 200` | Validate API response codes |
| Booleans      | True/False values | `is_active = True` | Feature flags, account state validation |
| Lists         | Ordered collections | `users = [1, 2, 3]` | Validate multiple records returned by API |
| Dictionaries  | Key-value pairs | `user["email"]` | Parse and validate JSON response fields |
| Loops         | Repeat actions | `for user in users:` | Validate all records in a response |
| Functions     | Reusable logic blocks | `def validate():` | Shared validation checks across scripts |
| JSON Parsing  | Convert JSON to dictionary | `json.loads(data)` | API response validation |
| File Handling | Read/write files | `open("app.log")` | Log analysis and test data validation |
| Exceptions    | Handle runtime errors | `try/except` | Prevent script crashes during failures |
| Assertions    | Validate expected outcomes | `assert status == 200` | Confirm test conditions programmatically |

## 10. Mini QA Example: Validate an API-Like Response
```python
# Example API-like response (simulated)
response = {
    "status_code": 200,
    "data": [
        {"id": 1, "email": "a@test.com", "active": True},
        {"id": 2, "email": "b@test.com", "active": True},
    ]
}

# Validate status code
if response["status_code"] != 200:
    print("FAIL: API did not return success status")
else:
    print("PASS: API returned 200")

# Validate required fields for each user record
for user in response["data"]:
    assert "id" in user, "FAIL: Missing id field"
    assert "email" in user, "FAIL: Missing email field"
    assert user["email"], "FAIL: Email is empty"
print("PASS: All user records contain required fields")
```
