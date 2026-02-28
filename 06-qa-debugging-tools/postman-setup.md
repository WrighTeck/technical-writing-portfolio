# Postman – Setup & Configuration Guide

## Overview

Postman is an API testing tool used to validate backend services independently of the user interface.

It enables QA engineers to:

- Test authentication flows
- Validate API request and response structure
- Perform negative testing
- Compare environment behavior (dev / staging / production)
- Troubleshoot 401 and 403 authorization issues
- Validate token lifecycle behavior

Postman is ideal for isolating backend logic from frontend issues.

## Installation

1. Download Postman from https://www.postman.com/downloads/
2. Install the desktop application.
3. Launch Postman.

## Initial Environment Setup

### Step 1 – Create an Environment

1. Click **Environments**.
2. Select **Create Environment**.
3. Add environment variables such as:
   - `base_url`
   - `auth_token`
   - `client_id`
   - `client_secret`

This allows switching between Dev, Staging, and Production.

### Step 2 – Create a Basic API Request

Example:

```http
GET {{base_url}}/user/profile
Authorization: Bearer {{auth_token}}
```
QA should validate:

- The correct environment is selected  
- The authorization token is populated  
- The status code matches expected behavior  
- The response body matches API documentation  

## Testing Authentication Workflow
Login Request Example
```http
POST {{base_url}}/login
Content-Type: application/json
```
Request body:
```json
{
  "username": "test_user",
  "password": "secure_password"
}
```
QA should validate:
- The response includes an access token
- The token expiration time is returned
-	The status code is 200 OK
- No unexpected error message is returned

## Token Expiration Scenario
If an expired token is used:
```http
HTTP/1.1 401 Unauthorized
```
QA should validate:
-	A refresh token endpoint exists
-	A new token is issued correctly
-	The error message matches API contract
-	Session behavior aligns with requirements

## Common QA Use Cases

Postman is ideally suited for:
-	401 and 403 authentication errors
-	Token expiration failures
-	Refresh token validation
-	Backend regression testing
-	API contract validation
-	Negative testing (missing headers, invalid payloads)
-	Comparing responses across environments
-	Isolating backend defects from UI defects

## Example: Negative Testing

Test a request without an authorization header:
```http
GET {{base_url}}/account
```
QA should validate:

- Proper error status (401 or 403)  
- Clear error message  
- No unintended data exposure  
- Consistent behavior across environments  

## When to Use Postman

Use Postman when:
- Backend logic must be validated without UI interference  
- Authentication behavior must be tested independently  
- Environment discrepancies are suspected  
- Debugging API-related production incidents  
- Verifying response schemas against specifications  

## QA Investigation Workflow Using Postman

1. Reproduce the issue in the application.  
2. Identify the failing API endpoint.  
3. Replicate the request in Postman.  
4. Compare headers, payload, and status code.  
5. Confirm environment alignment.  
6. Document findings with request and response details.  

QA should validate:
- The correct environment is selected  
- The authorization token is populated  
- The status code matches expected behavior  
- The response body matches API documentation  
