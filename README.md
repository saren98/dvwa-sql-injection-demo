# SQL Injection Demonstration on DVWA (Low Security)

## Objective

This project demonstrates an SQL Injection vulnerability using DVWA (Damn Vulnerable Web Application) in a controlled and educational environment.

The goal is to understand how improper input validation can allow attackers to manipulate database queries.

---

## Tools Used

- Ubuntu 24.04 LTS
- DVWA (Damn Vulnerable Web Application)
- Apache Web Server
- PHP
- MariaDB (MySQL)

---

## Environment Setup

1. Installed DVWA on a local Ubuntu system.
2. Configured Apache, PHP, and MariaDB.
3. Created a DVWA database and user.
4. Set the DVWA security level to Low.

---

## SQL Injection Steps

1. Logged into the DVWA dashboard.
2. Navigated to the SQL Injection module.
3. Entered the following payload in the User ID field:

```text
1 OR 1=1
````

4. Submitted the input.

---

## Result

The application returned multiple user records instead of a single record.

This confirms that the SQL Injection vulnerability is present when the security level is set to Low.

---

## Explanation

The application executes a SQL query similar to:

```sql
SELECT * FROM users WHERE id = 1;
```

After injection, it becomes:

```sql
SELECT * FROM users WHERE id = 1 OR 1=1;
```

Since `1=1` is always true, the database returns all records.

---

## Files Included

* `sql_injection_exploit.sh` — Demonstration script
* `README.md` — Documentation
* Screenshots — SQL injection process and result

---

## Learning Outcomes

* Understanding SQL Injection basics
* Setting up a vulnerable lab environment
* Identifying improper input handling
* Demonstrating real-world web security risks

---

## Disclaimer

This project is for educational purposes only and was performed on a local vulnerable application.

Do NOT attempt these techniques on real systems.

---

## Author

Sagen Saren
