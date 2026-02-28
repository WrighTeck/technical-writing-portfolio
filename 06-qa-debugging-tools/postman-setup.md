## Network

**Used to:**

- Inspect API requests and responses  
- Validate status codes (200 / 401 / 403 / 500)  
- Inspect headers and payloads  
- Detect failed or blocked requests  
- Identify CORS failures  
- Validate authentication tokens  

**QA should confirm:**

- Correct request URL  
- Correct environment host  
- Expected response structure  
- No unexpected redirects  

---

## Elements

**Used to:**

- Inspect HTML structure  
- Validate UI components  
- Confirm CSS styling  
- Verify dynamic rendering  

Ideal for UI/UX validation and layout defect investigation.

---

## Performance

**Used to:**

- Analyze page load timing  
- Detect slow API responses  
- Identify long-running scripts  
- Evaluate rendering bottlenecks  

---

## Ideal QA Scenarios for Chrome DevTools

Chrome DevTools is best suited for:

- CORS issues  
- JavaScript runtime errors  
- UI rendering defects  
- Network request validation  
- Performance bottlenecks  
- Broken resource loading  
- Feature flag debugging  
- Frontend/backend responsibility isolation  

---

## Example QA Investigation Flow

1. Reproduce the issue.  
2. Open Console tab and check for runtime errors.  
3. Open Network tab and locate failing request.  
4. Inspect status code and response payload.  
5. Confirm environment configuration.  
6. Capture screenshots and network logs for defect report.  

---

## When to Use Chrome DevTools

Use Chrome DevTools when:

- Investigating web-based application defects  
- Troubleshooting CORS errors  
- Validating frontend logic  
- Confirming API responses match UI output  
- Investigating performance slowdowns  
- Supporting production issue triage

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
