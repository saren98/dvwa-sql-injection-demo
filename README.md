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

1. Installed DVWA on local Ubuntu system
2. Configured Apache, PHP, and MariaDB
3. Created DVWA database and user
4. Set DVWA security level to Low

---

## SQL Injection Steps

1. Logged into DVWA dashboard
2. Navigated to SQL Injection module
3. Entered the following payload in User ID field:

1 OR 1=1


4. Submitted the input

---

## Result

The application returned multiple user records instead of a single record.

This confirms the SQL Injection vulnerability is present when security level is set to Low.

---

## Explanation

The application executes a SQL query similar to:

SELECT * FROM users WHERE id = 1;

After injection, it becomes:

SELECT * FROM users WHERE id = 1 OR 1=1;

Since 1=1 is always true, the database returns all records.

---

## Files Included

- sql_injection_exploit.sh : Demonstration script
- README.md : Documentation
- Screenshots : SQL injection process and result

---

## Learning Outcomes

- Understanding SQL Injection basics
- Setting up a vulnerable lab environment
- Identifying improper input handling
- Demonstrating real-world web security risks

---

## Disclaimer

This project is for educational purposes only and was performed on a local vulnerable application.

Do NOT attempt these techniques on real systems.

---

## Author

Sagen Saren


