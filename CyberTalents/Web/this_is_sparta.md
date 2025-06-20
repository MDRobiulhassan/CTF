# This is Sparta

## Challenge Description

**Challenge Link**:  
http://wcamxwl32pue3e6m4m2360mtg3016dv97d15t43l-web.cybertalentslabs.com

> _"Morning has broken today they're fighting in the shade when arrows blocked the sun they fell tonight they dine in hell"_

- FLAG Format:  {flagbody}
---

## Walkthrough

## Step 1: Inspect the page

- The page includes a **Hint** button.
- When clicked, the hint says:
  > _"Easier than Ableton"_

---

## Step 2: Analyze the JavaScript

The page contains obfuscated JavaScript which controls the login validation.Press Ctrl+U or select View Page Source

```js
var _0xae5b = [
  "\x76\x61\x6C\x75\x65",                            // "value"
  "\x75\x73\x65\x72",                                // "user"
  "\x67\x65\x74\x45\x6C\x65\x6D\x65\x6E\x74\x42\x79\x49\x64", // "getElementById"
  "\x70\x61\x73\x73",                                // "pass"
  "\x43\x79\x62\x65\x72\x2d\x54\x61\x6c\x65\x6e\x74", // "Cyber-Talent"
  "\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x43\x6F\x6E\x67\x72\x61\x74\x7A\x20\x0A\x0A", // "                    Congratz \n\n"
  "\x77\x72\x6F\x6E\x67\x20\x50\x61\x73\x73\x77\x6F\x72\x64" // "wrong Password"
];
```


### Breakdown of the Array
- Use Ascii decoder 

| Index | Hex String                                                                                                   | Decoded String          
|-------|-------------------------------------------------------------------------------------------------------------|------------------------|
| 0     | `\x76\x61\x6C\x75\x65`                                                                                      | `"value"`              |
| 1     | `\x75\x73\x65\x72`                                                                                          | `"user"`               |
| 2     | `\x67\x65\x74\x45\x6C\x65\x6D\x65\x6E\x74\x42\x79\x49\x64`                                                  | `"getElementById"`     |
| 3     | `\x70\x61\x73\x73`                                                                                          | `"pass"`               |
| 4     | `\x43\x79\x62\x65\x72\x2d\x54\x61\x6c\x65\x6e\x74`                                                          | `"Cyber-Talent"`       |
| 5     | `\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x43\x6F\x6E\x67\x72\x61\x74\x7A\x20\x0A\x0A` | `"                    Congratz \n\n"` |
| 6     | `\x77\x72\x6F\x6E\x67\x20\x50\x61\x73\x73\x77\x6F\x72\x64`                                                  | `"wrong Password"`     |


### Decoded Strings from Hex Escapes:
- Username : "Cyber-Talent"

- Password : "Cyber-Talent"

---

## Final Result

You are now logged in and the page pop-up reveals the **flag**.

<details>
<summary> Click to reveal the flag</summary>

```
FLAG: {J4V4_Scr1Pt_1S_Aw3s0me}
```

</details>

---


