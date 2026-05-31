#  OWASP ZAP

## Overview

OWASP ZAP is an open source web application security scanner designed for finding vulnerabilities in web apps during development and testing phases.

---

## Main Purpose

1 Detect common web vulnerabilities  
2 Automate security scanning for web apps  
3 Test OWASP Top 10 issues  
4 Intercept and inspect HTTP traffic  
5 Support security testing in CI pipelines  

---

## How It Works

1 ZAP acts as a proxy between browser and target  
2 It records and analyzes web traffic  
3 Spidering maps the application structure  
4 Active scanning sends test payloads  
5 Results are generated with vulnerability details  

---

## Core Components

1 Proxy  
   - Captures HTTP and HTTPS traffic  

2 Spider  
   - Crawls and maps web application  

3 Active Scanner  
   - Tests for vulnerabilities using attack payloads  

4 Passive Scanner  
   - Detects issues without modifying traffic  

5 Fuzzer  
   - Tests input fields with multiple payloads  

---

## Key Features

1 Fully open source  
2 Automated vulnerability scanning  
3 Passive and active analysis modes  
4 API scanning support  
5 Scriptable and extensible  

---

## Common Use Cases

1 Web application security testing  
2 Continuous integration security checks  
3 OWASP Top 10 compliance testing  
4 Beginner learning tool for web security  
5 API vulnerability testing  

---

## Advantages

1 Free and open source  
2 Easy to install and use  
3 Good for beginners and professionals  
4 Integrates with automation pipelines  

---

## Limitations

1 Less powerful than commercial tools like Burp Suite Pro  
2 Can produce false positives  
3 Slower scanning on large applications  
4 Requires tuning for accurate results  

---

## Typical Workflow

1 Configure browser proxy to ZAP  
2 Spider the target application  
3 Run passive scan during browsing  
4 Start active scan for deeper testing  
5 Review identified vulnerabilities  
6 Validate critical issues manually  
