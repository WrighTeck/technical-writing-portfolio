# Charles Proxy – Setup & Configuration Guide

## Overview

Charles Proxy is an HTTP/HTTPS proxy tool used to inspect, monitor, and debug network traffic between client applications (Web, Mobile, OTT) and backend services.

It allows QA engineers to validate:

- API request and response payloads
- Authentication headers and tokens
- Environment host configuration (dev / staging / production)
- Status codes (200, 401, 403, 500)
- Redirect behavior
- OTT ad beacon tracking

---

## Installation

1. Download Charles Proxy from:
   https://www.charlesproxy.com

2. Install for macOS or Windows.

3. Launch the application.

---

## Initial Configuration

### Enable SSL Proxying

1. Navigate to:
   Proxy > SSL Proxying Settings

2. Check:
   Enable SSL Proxying

3. Add entry:
   - Host: *
   - Port: 443

This allows HTTPS traffic inspection.

---

### Install and Trust Charles Root Certificate

#### macOS

1. Help > SSL Proxying > Install Charles Root Certificate
2. Open Keychain Access
3. Locate the Charles certificate
4. Set Trust to "Always Trust"

#### Windows

1. Install certificate when prompted
2. Add to Trusted Root Certification Authorities

---

## Mobile Device Configuration (Optional)

To inspect mobile or OTT device traffic:

1. Connect device to same Wi-Fi network as your machine.
2. On device Wi-Fi settings:
   - Configure Proxy
   - Server: Your machine’s IP address
   - Port: 8888
3. Install Charles SSL certificate on device.
4. Enable full certificate trust (iOS requires manual trust toggle).

---

## Common QA Scenarios

Charles Proxy is ideally suited for:

- 403 Unauthorized API errors
- Missing or malformed authentication headers
- Token validation failures
- Environment misconfigurations
- API payload validation
- OTT ad beacon inspection
- CDN endpoint troubleshooting
- Identifying backend vs frontend responsibility

---

## Example Use Case

### Inspecting an API Call

```http
GET https://api.example.com/user/profile
```

QA should validate:
	•	Correct environment host
	•	Expected status code
	•	Authorization header presence
	•	Response structure integrity

⸻

When to Use Charles Proxy

Use Charles when:
	•	Network-level visibility is required
	•	Authentication debugging is needed
	•	OTT ad tracking validation is required
	•	Production incident investigation is necessary
	•	Backend response behavior must be confirmed
