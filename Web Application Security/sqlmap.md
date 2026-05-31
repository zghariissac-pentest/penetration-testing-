#  SQLmap

## Overview

SQLmap is an automated penetration testing tool designed to detect and exploit SQL injection vulnerabilities in web applications.

---

## Main Purpose

1 Detect SQL injection vulnerabilities  
2 Exploit database weaknesses  
3 Extract database information  
4 Enumerate database structure  
5 Test web input security  

---

## How It Works

1 SQLmap sends crafted payloads to web inputs  
2 It analyzes server responses for database errors or behavior changes  
3 If injection is detected, it confirms vulnerability type  
4 It escalates to data extraction if permitted  
5 It can automate full database enumeration  

---

## Supported Injection Types

1 Boolean based blind injection  
2 Time based blind injection  
3 Error based injection  
4 Union based injection  
5 Stacked queries (when supported)  

---

## Database Support

1 MySQL  
2 PostgreSQL  
3 Microsoft SQL Server  
4 Oracle  
5 SQLite  
6 MariaDB  

---

## Key Features

1 Fully automated SQL injection detection  
2 Database dumping capabilities  
3 Password hash extraction  
4 Remote command execution (in some cases)  
5 Bypass techniques for filters and WAFs  

---

## Common Use Cases

1 Web application penetration testing  
2 Database security auditing  
3 Vulnerability validation for SQL injection  
4 Security research and training labs  

---

## Advantages

1 Very powerful and automated  
2 Supports many database types  
3 Can detect complex injection types  
4 Reduces manual testing time  

---

## Limitations

1 Only focused on SQL injection  
2 Requires correct target parameters  
3 Can be noisy and easily detected  
4 Not useful for non SQL vulnerabilities  

---

## Typical Workflow

1 Identify vulnerable input parameter  
2 Provide target URL to SQLmap  
3 Test for injection presence  
4 Confirm vulnerability type  
5 Extract database structure  
6 Dump sensitive data if allowed  
