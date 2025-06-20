# OWASP Top 10 TryHackMe Write-up

This is a write-up for the "OWASP Top 10" room on TryHackMe, written in 2021. It is designed for users who do not have their own virtual machines and want to utilize the resources provided by TryHackMe.

## Overview
This room focuses on the following OWASP Top 10 vulnerabilities:
- Injection
- Broken Authentication
- Sensitive Data Exposure
- XML External Entity
- Broken Access Control
- Security Misconfiguration
- Cross-site Scripting
- Insecure Deserialization
- Components with Known Vulnerabilities
- Insufficient Logging & Monitoring

## Tasks

### Task 1: Introduction
- Read the overview above.
- **No Answer Needed**

### Task 2: Accessing Machines
- Connect to the TryHackMe network or deploy the AttackBox.
- **No Answer Needed**

### Task 3: 1. Broken Access Control
- Read and understand what broken access control is.
- **No Answer Needed**

### Task 4: Broken Access Control (IDOR Challenge)
- Read and understand how Insecure Direct Object Reference (IDOR) works.
- Deploy the machine and go to `http://MACHINE_IP`.
- Login with username `noot` and password `test1234`.
- Look at other users’ notes. What is the flag?
  - **Hint**: The URL contains `?note_id=1` — try changing the parameter value.
  - **Answer Format**: `****{*************}`
  - **Answer**: `flag{fivefourthree}`

### Task 5: 2. Cryptographic Failures
- Read the introduction to Cryptographic Failures and deploy the machine.
- **No Answer Needed**

### Task 6: Cryptographic Failures (Supporting Material 1)
- Read and understand the supporting material on SQLite Databases.
- **No Answer Needed**

### Task 7: Cryptographic Failures (Supporting Material 2)
- Read the supporting material about cracking hashes.
- **No Answer Needed**

### Task 8: Cryptographic Failures (Challenge)
- Start the machine, open Firefox, and go to `http://machine-ip:81`.
- View the source code (CTRL + U) on the login page.
- What is the name of the mentioned directory?
  - **Hint**: Check the source code on the `/login` page.
  - **Answer Format**: `/******`
  - **Answer**: `/assets`
- Navigate to the directory. What file stands out as likely to contain sensitive data?
  - **Answer Format**: `******.**`
  - **Answer**: `webapp.db`
- Use the supporting material to access the sensitive data. What is the password hash of the admin user?
  - **Answer Format**: `******************************`
  - **Answer**: `6eea9b7ef19179a06954edd0f6c05ceb`
- Crack the hash. What is the admin’s plaintext password?
  - **Hint**: Use CrackStation.
  - **Answer Format**: `**********`
  - **Answer**: `qwertyuiop`
- Log in as the admin. What is the flag?
  - **Answer Format**: `***{********************************}`
  - **Answer**: `THM{Yzc2YjdkMjE5N2VjMzNhOTE3NjdiMjdl}`

### Task 9: 3. Injection
- I’ve understood Injection attacks.
- **No Answer Needed**

### Task 10: 3.1. Command Injection
- Head to `http://machine-ip:82`.
- Use commands like `$(whoami)`, `$(ls)`, `$(cat /etc/passwd)`, and `$(cat /etc/os-release)`.
- What strange text file is in the website’s root directory?
  - **Answer Format**: `********.***`
  - **Answer**: `drpepper.txt`
- How many non-root/non-service/non-daemon users are there?
  - **Answer Format**: `*`
  - **Answer**: `0`
- What is the user’s shell set as?
  - **Answer Format**: `/****/*******`
  - **Answer**: `apache`
- What is the user’s shell set as?
  - **Answer Format**: `/****/*******`
  - **Answer**: `/sbin/nologin`
- What version of Alpine Linux is running?
  - **Hint**: Check `/etc/alpine-release`.
  - **Answer Format**: `*.**.*`
  - **Answer**: `3.16.0`

### Task 11: 4. Insecure Design
- Navigate to `http://MACHINE_IP:85` and access joseph’s account.
- Try to reset joseph’s password.
- What is the value of the flag in joseph’s account?
  - **Hint**: Guess the security question.
  - **Answer Format**: `***{*******************************}`
  - **Answer**: `THM{Not_3ven_c4tz_c0uld_sav3_U!}`

### Task 12: 5. Security Misconfiguration
- Go to `http://MACHINE_IP:86/console` and use the Werkzeug console.
- Run `import os; print(os.popen("ls -l").read())`.
- What is the database file name (with .db extension)?
  - **Answer Format**: `****.**`
  - **Answer**: `todo.db`
- Modify the code to read `app.py`. What is the value of the `secret_flag` variable?
  - **Answer Format**: `***{****************************}`
  - **Answer**: `THM{Just_a_tiny_misconfiguration}`

### Task 13: 6. Vulnerable and Outdated Components
- Read about the vulnerability.
- **No Answer Needed**

### Task 14: Vulnerable and Outdated Components — Exploit
- Read the above!
- **No Answer Needed**

### Task 15: Vulnerable and Outdated Components — Lab
- Go to the given site, use the Exploit Database, and run `python3 47887.py [URL]`.
- What is the content of `/opt/flag.txt`?
  - **Hint**: Search for bookstore app RCEs.
  - **Answer Format**: `***{*********************}`
  - **Answer**: `THM{But_1ts_n0t_myf4ult!}`

### Task 16: 7. Identification and Authentication Failures
- I’ve understood broken authentication mechanisms.
- **No Answer Needed**

### Task 17: Identification and Authentication Failures Practical
- Register and login with modified usernames (e.g., `" darren"`).
- What is the flag in darren’s account?
  - **Answer Format**: `********************************`
  - **Answer**: `fe86079416a21a3c99937fea8874b667`
- What is the flag in arthur’s account?
  - **Answer Format**: `******************`
  - **Answer**: `d9ac0f7db4fda460ac3edeb75d75e16e`

### Task 18: 8. Software and Data Integrity Failures
- Read the above and continue!
- **No Answer Needed**

### Task 19: Software Integrity Failures Security Misconfiguration
- Go to `https://www.srihash.org/` and input `https://code.jquery.com/jquery-1.12.4.min.js` with SHA-256.
- What is the SHA-256 hash?
  - **Hint**: Use SRI hash calculator.
  - **Answer Format**: `SHA256-*******************************************=`
  - **Answer**: `sha256-ZosEbRLbNQzLpnKIkEdrPv7lOy9C27hHQ+Xp8a4MxAQ=`

### Task 20: Data Integrity Failures
- Go to `http://MACHINE_IP:8089/`, login as guest, and modify the JWT cookie.
- What is guest’s account password?
  - **Hint**: Try wrong credentials.
  - **Answer Format**: `*****`
  - **Answer**: `guest`
- What is the name of the website’s cookie containing a JWT token?
  - **Answer Format**: `***-*******`
  - **Answer**: `jwt-session`
- What is the flag presented to the admin user?
  - **Answer Format**: `***{********************************}`
  - **Answer**: `THM{Dont_take_cookies_from_strangers}`

### Task 21: 9. Security Logging and Monitoring Failures
- Download the log file and analyze it.
- What IP address is the attacker using?
  - **Hint**: Look for repeated actions in 15 seconds.
  - **Answer Format**: `**.**.**.**`
  - **Answer**: `49.99.13.16`
- What kind of attack is being carried out?
  - **Hint**: Identify username/password attempts.
  - **Answer Format**: `***** *****`
  - **Answer**: `Brute Force`

### Task 22: 10. Server-Side Request Forgery (SSRF)
- Go to `http://MACHINE_IP:8087/`.
- What is the only host allowed to access the admin area?
  - **Hint**: Check error messages.
  - **Answer Format**: `*********`
  - **Answer**: `localhost`
- Where does the server parameter point to?
  - **Answer Format**: `***********************`
  - **Answer**: `secure-file-storage.com`
- Using SSRF, intercept the request with your AttackBox. Are there any API keys?
  - **Answer Format**: `***{************************}`
  - **Answer**: `THM{Hello_Im_just_an_API_key}`
- **Extra Credit**: Use SSRF to access the admin area (e.g., `server=http://localhost:8087/admin%23&id=75482342`).
  - **Mark as Completed**

## Contributing
Contributions are welcome! Please fork the repository and submit pull requests with improvements.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
