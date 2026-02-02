# Overview
During testing of the user account functionality, a medium-severity horizontal privilege escalation vulnerability was identified. The application relied on a request parameter (id) to determine which user’s account information to display, but failed to enforce proper authorization checks. By modifying this parameter, an authenticated user was able to access another user’s account details, including sensitive information like API keys, demonstrating insufficient access control.

# Methodology

Step 1: Logged in with valid user credentials and navigated to the My Account page.

Step 2: Identified the id parameter in the URL controlling which account was displayed.

Step 3: Sent the request to Burp Repeater for testing.

Step 4: Altered the id parameter to target a different user’s account.

Step 5: Retrieved sensitive data from the targeted account, confirming unauthorized access.

# Conclusion

This assessment confirmed a horizontal privilege escalation vulnerability caused by inadequate server-side access controls. The flaw allows attackers to access other users’ account information by manipulating a request parameter. Implementing strict authorization checks and using session-based identifiers are essential to prevent such attacks and safeguard sensitive user data.
