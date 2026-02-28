# Chrome DevTools – Setup & Configuration Guide

## Overview

Chrome DevTools is a built-in browser debugging suite used to inspect frontend behavior, analyze network requests, troubleshoot errors, and evaluate performance in web applications.

It is a primary tool for web-based QA validation and defect investigation.

---

## What Chrome DevTools Does

Chrome DevTools provides visibility into:

- JavaScript console errors and warnings
- Network request and response inspection
- CORS configuration issues
- DOM structure and UI rendering
- Performance bottlenecks
- Resource loading failures

It helps QA engineers determine whether an issue originates from:

- Frontend logic
- API response failures
- Configuration errors
- Performance degradation
- Environment misalignment

---

## How to Access Chrome DevTools

No installation is required beyond Google Chrome.

### Open DevTools

- macOS: `Command + Option + I`
- Windows: `Ctrl + Shift + I`
- Or right-click on page → **Inspect**

---

## Key Tabs Used in QA Workflows

### Console

Used to:

- Identify JavaScript errors
- Review warnings and runtime exceptions
- Log debug statements
- Validate feature flag behavior

Common error example:

```javascript
Uncaught TypeError: Cannot read properties of undefined
```
