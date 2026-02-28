# JavaScript for QA Professionals

JavaScript is widely used in web automation frameworks such as Playwright, Cypress, and WebDriver-based tools.

This guide covers essential JavaScript concepts relevant to QA testing.

---

# 1. Variables & Data Types

```javascript
// 1. Variables & Data Types
let username = "testUser";     // string value used for login validation
const retryLimit = 3;          // maximum retry attempts
let isLoggedIn = false;        // boolean flag to track session state

// 2. Conditional Logic
if (response.status === 200) {   // check for successful API response
  console.log("Request successful");
} else {                         // handle failed API response
  console.log("Request failed");
}
// 3. Looping Through Data
for (let i = 0; i < users.length; i++) {   // iterate through user list
  console.log(users[i].email);             // validate email field
}
// 4. Function for Reusable Validation
function validateStatus(code) {  // function definition
  return code === 200;           // return true if status is OK
}
// 5. JSON Validation
let response = {
  id: 1,
  name: "John",
  active: true
};

console.log(response.name);  // access specific JSON property
