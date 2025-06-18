# Admin has the power

## Challenge Description

**Challenge Link**:  
http://wcamxwl32pue3e6m5p6v4ehxzg1r6dv97d15t43l-web.cybertalentslabs.com

> _"Administrators only have the power to see the flag, can you be one?"_

---

## Walkthrough

### Step 1: Credential Leak in HTML

- Open the challenge page and **view the page source** (Right-click → View Page Source or Ctrl+U).
- Inside the `<head>` section, there is a comment with leaked credentials:

```html
<!-- TODO: remove this line ,  for maintenance purpose use this info (user:support password:x34245323)-->
```

* Extracted credentials:
  * **Username**: `support`
  * **Password**: `x34245323`

---

### Step 2: Logging In

* Use the above credentials to log in on the homepage.
* You will be redirected to the **admin panel** as the `support` user.

---

### Step 3: Cookie Manipulation

1. Press `F12` or right-click → **Inspect** → Go to the **Application** tab.
2. Under the left-side menu, go to **Cookies** → Select the domain (e.g., `http://wcamxwl...`).
3. You will see a cookie with:
   * **Name**: `role`
   * **Value**: `support`
4. Double-click the `value` field and change it to:

```
admin
```

5. Press **Enter**, then **refresh the page**.

---

## Final Result

You are now logged in as an **admin**, and the page reveals the **flag**.

<details>
<summary> Click to reveal the flag</summary>

```
hiadminyouhavethepower
```

</details>

---


