## 06 – QA Debugging Tools for Web, Mobile & OTT Testing

Practical documentation covering free debugging tools used in real-world QA workflows across platforms.

### Tools Included

- **Charles Proxy** – Network traffic inspection & API validation  
- **Chrome DevTools** – Front-end debugging, performance analysis, and console inspection  
- **Postman** – API testing, authentication validation, and response verification  

### Real-World Debugging Scenarios Included

- **403 Unauthorized API errors**  
- **CORS issues**  
- **Missing ad beacons on OTT platforms**  
- **Environment misconfigurations**  
- **Token expiration failures**  

---
### Charles Proxy – Network Traffic Inspection & API Validation

Charles Proxy is used to inspect HTTP and HTTPS traffic between client applications (web, mobile, OTT) and backend services.

It is commonly used in QA workflows to validate:

- API request and response payloads  
- Authentication headers and tokens  
- Environment host configuration (dev / staging / production)  
- Status codes (200, 401, 403, 500)  
- Redirects and blocked requests  
- OTT ad calls and tracking beacons  

#### Common QA Use Cases

- Confirm the correct API endpoint is being called  
- Validate required headers such as `Authorization`  
- Verify response structure matches API specification  
- Identify backend vs frontend responsibility in failures  
- Capture evidence for defect reports  

#### Example: Inspecting an API Request

```http
GET https://api.example.com/user/profile
```
QA should validate:
	•	The request is sent to the correct environment
	•	The response status code is expected
	•	The response body contains required fields
	•	The authentication header is present when required

### Chrome DevTools – Front-End Debugging, Performance Analysis & Console Inspection

Chrome DevTools is used for front-end debugging and web application validation.

It provides visibility into:

- Console errors and warnings  
- Network request failures  
- CORS configuration issues  
- DOM structure and UI rendering  
- Performance timing and load behavior  

#### Common QA Use Cases

- Identify JavaScript errors impacting functionality  
- Inspect failed API calls in the Network tab  
- Validate request and response payloads  
- Confirm CORS headers are correctly configured  
- Analyze page load performance issues  

#### Example: Console Error Investigation

```text
Uncaught TypeError: Cannot read properties of undefined
```
QA should validate:
	•	Which script triggered the error
	•	Whether the issue is reproducible
	•	Whether the error blocks core functionality
	•	If the error is environment-specific

Example: Network Request Inspection
Using the Network tab:
	•	Confirm correct request URL
	•	Validate status code (200 / 401 / 403 / 500)
	•	Inspect request headers and payload
	•	Confirm response structure matches expected schema

### Postman – API Testing, Authentication Validation & Response Verification

Postman is used to test APIs independently of the user interface.  
It allows QA to validate backend behavior directly and isolate UI-related issues.

It is commonly used to:

- Validate login and authentication flows  
- Test expired or invalid tokens  
- Switch between environments (dev / staging / production)  
- Perform negative testing (missing headers, invalid payloads)  
- Verify API response structure and status codes  

#### Common QA Use Cases

- Reproduce API failures outside the application  
- Confirm backend logic is functioning as expected  
- Validate refresh token behavior  
- Compare responses across environments  
- Confirm error handling responses match API documentation  

#### Example: Authenticated API Request

```http
GET https://api.example.com/account
Authorization: Bearer <token>
```
QA should validate:
	•	Token is present and correctly formatted
	•	Token is valid for the selected environment
	•	Response contains expected fields
	•	Status code matches expected behavior
  
Example: Token Expiration Failure
```http
HTTP/1.1 401 Unauthorized
```

## Real-World Debugging Scenarios

The following scenarios represent common issues encountered in real-world QA workflows across Web, Mobile, and OTT platforms.

---

### 403 Unauthorized API Errors

A 403 error indicates that the request was understood by the server but access is denied.

#### Common Causes

- Missing `Authorization` header  
- Expired or invalid access token  
- Role-based permission restrictions  
- Incorrect environment configuration  
- Token generated for a different environment  

#### Recommended Tools

- Charles Proxy – Inspect headers and response codes  
- Postman – Reproduce the request independently  

---

### CORS Issues

CORS (Cross-Origin Resource Sharing) errors occur when a browser blocks a request due to origin policy restrictions.

#### Common Causes

- Missing `Access-Control-Allow-Origin` header  
- Failed preflight (OPTIONS) request  
- Incorrect API domain  
- HTTP/HTTPS protocol mismatch  
- Environment misconfiguration  

#### Recommended Tools

- Chrome DevTools – Console and Network tab  
- Postman – Confirm backend works outside browser  

---

### Missing Ad Beacons on OTT Platforms

Ad beacons are tracking calls sent during ad playback (start, midpoint, completion).

#### Common Causes

- Beacon request not triggered by the app  
- Tracking endpoint blocked or unreachable  
- Incorrect ad tag configuration  
- CDN or third-party service failure  
- Environment mismatch  

#### Recommended Tools

- Charles Proxy – Filter and inspect beacon calls  
- Device logs – Confirm ad events triggered  

---

### Environment Misconfigurations

Environment issues occur when applications point to incorrect backend services.

#### Common Causes

- Incorrect base URL  
- Wrong API key  
- Feature flag misalignment  
- Staging build calling production backend  
- Incorrect configuration variables  

#### Recommended Tools

- Charles Proxy – Verify request hostnames  
- Postman – Compare environment responses  
- Chrome DevTools – Confirm network calls  

---

### CORS Issues

CORS (Cross-Origin Resource Sharing) errors occur when a browser blocks a request due to origin policy restrictions.

#### Common Causes

- Missing `Access-Control-Allow-Origin` header  
- Failed preflight (OPTIONS) request  
- Incorrect API domain  
- HTTP/HTTPS protocol mismatch  
- Environment misconfiguration  

#### Recommended Tools

- Chrome DevTools – Console and Network tab  
- Postman – Confirm backend works outside browser  

---

### Missing Ad Beacons on OTT Platforms

Ad beacons are tracking calls sent during ad playback (start, midpoint, completion).

#### Common Causes

- Beacon request not triggered by the app  
- Tracking endpoint blocked or unreachable  
- Incorrect ad tag configuration  
- CDN or third-party service failure  
- Environment mismatch  

#### Recommended Tools

- Charles Proxy – Filter and inspect beacon calls  
- Device logs – Confirm ad events triggered  

---

### Environment Misconfigurations

Environment issues occur when applications point to incorrect backend services.

#### Common Causes

- Incorrect base URL  
- Wrong API key  
- Feature flag misalignment  
- Staging build calling production backend  
- Incorrect configuration variables  

#### Recommended Tools

- Charles Proxy – Verify request hostnames  
- Postman – Compare environment responses  
- Chrome DevTools – Confirm network calls  

---

### Token Expiration Failures

Authentication failures caused by improper token lifecycle management.

#### Common Causes

- Access token expired  
- Refresh token not triggered  
- Incorrect token storage  
- Session timeout logic failure  
- Clock skew between client and server  

#### Recommended Tools

- Postman – Validate authentication flow  
- Charles Proxy – Inspect refresh requests  
- Chrome DevTools – Review console and network logs  

---

