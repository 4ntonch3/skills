# Test Case Template

Load this reference when: you need to validate generated test-case with user.

Information to present to user:

- Test-case name.
- Description of related business scenario which will be covered by this test-case.
- Preparation data.
- Incoming data.
- Reference data.

Example 1:

```md
**Name:** latest_logged_in_at_when_user_logged  
**Description:** getting latest log in time for user, who is registered & logged in at least 1 time  
**Preparation data:**
- Database:
  - Corresponding User is added to DB
  - User `last_log_in_at` field is set to not null value
  - Access Token is added to DB
- Cache:
  - Empty
**Incoming data:**
- username of existing User
**Reference data:**
- Response code: 200 - OK
- Response body: `{"result": {"last_log_in_at": "2026-08-08T21:17:00Z"}}`
```

Example 2:

```md
**Name:** latest_logged_in_at_when_user_not_exist  
**Description:** getting latest log in time for user, who is not registered  
**Preparation data:**
- Database:
  - Access Token is added to DB
- Cache:
  - Empty
**Incoming data:**
- username of non-existing User
**Reference data:**
- Response code: 400 - Not Found
- Response body: `{"error": "No such user found"}`
```
