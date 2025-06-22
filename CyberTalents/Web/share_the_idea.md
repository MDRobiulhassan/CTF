# Share the idea

## Challenge Description

**Challenge Link**:  
http://wcamxwl32pue3e6mle435w9h8z5x6dv97d15t43l-web.cybertalentslabs.com

> _"can you reveal the admin password ?"_

---

## Walkthrough

## Step 1: Register with any username and password.Then login

- Create an account with any username and password.
- After logging in, you'll be redirected to the main blog interface.

---

## Step 2: SQL Injection Test
- In the **text area**, type a single quote `'`.
- You'll see an error popup in the top-left corner — this confirms that **SQL injection** is possible.

---

## Step 3: SQL version test
- Write the following payload in the textarea:
```html
' || (select sqlite_version()));--
```
The output reveals the site uses SQLite.

---

## Step 4: Find Existing Tables
- Write this code in the text area
```html
' || (SELECT sql FROM sqlite_master));--
```
- This dumps the table definitions.

- You’ll discover a table called: xde43_users, which contains the fields: username, password, and role.

---

## Step 5: Dump Admin Credentials
- Use this injection to get the admin password:
  
```html
' || (select password from xde43_users where role="admin"));--
```

This displays a post containing the flag.

## Final Result

A post appears with the flag.

<details>
<summary> Click to reveal the flag</summary>

```
flag245698
```

</details>

---


