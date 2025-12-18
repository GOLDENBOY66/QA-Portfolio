# Sample Bug Reports

This document contains examples of my professional bug reporting style, focusing on clarity, reproducibility, and technical detail.

---

## 🛑 BUG-001: "Forgot Password" link is unresponsive
**Severity:** High  
**Priority:** High  
**Environment:** Production - Chrome v120.0 (Windows 11)  
**Status:** New  

### Summary
The "Forgot Password" link on the main login page does not trigger any action when clicked, preventing users from recovering their accounts.

### Steps to Reproduce
1. Navigate to the Login Page (`https://imresanera.com/login`).
2. Click on the "Forgot Password" hyperlink below the login button.
3. Observe the page behavior and Network tab in DevTools.

### Actual Result
The page remains static. No redirect occurs, and no network request is sent to the authentication server.

### Expected Result
The user should be redirected to the Password Recovery page (`/forgot-password`) or receive a "Reset Email Sent" notification.

---

## ⚠️ BUG-002: Search Bar crashes on special characters (SQL Injection Risk)
**Severity:** Critical  
**Priority:** High  
**Environment:** Staging - Firefox v121.0  

### Summary
The search input field fails to sanitize special characters, resulting in a 500 Internal Server Error when symbols like `< > / \` are entered.

### Steps to Reproduce
1. Log in to the application and navigate to the Search bar.
2. Input the following string: `<script>alert('XSS')</script>`.
3. Press "Enter" or click the search icon.

### Actual Result
The application crashes and displays a "500 Internal Server Error" page.

### Expected Result
The system should sanitize or escape special characters and return a "No results found" message to the user.
