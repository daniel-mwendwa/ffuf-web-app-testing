# FFUF Web Application Testing

## Overview
This repository documents the practical knowledge and techniques gained from the Hack the Box Academy module "Attacking Web Applications with ffuf." It covers the use of `ffuf`, a powerful web fuzzing tool, for testing and identifying vulnerabilities in web applications. The report outlines various fuzzing methods and provides examples to help security researchers and testers improve their web application security assessment skills.

## Topics Covered
1. **Directory Fuzzing**  
   Discover hidden directories and files on a web server using ffuf.

2. **Page Fuzzing**  
   Test web application behavior by sending unexpected or malformed inputs.

3. **Recursive Fuzzing**  
   Perform multi-level fuzzing to explore interconnected components within applications.

4. **Sub-domain Fuzzing**  
   Identify hidden sub-domains associated with a target domain.

5. **Vhost Fuzzing**  
   Discover virtual hosts running on the same server or IP address.

6. **Parameter Fuzzing**  
   Manipulate GET and POST parameters to analyze application responses.

7. **Value Fuzzing**  
   Test parameter values with various inputs to uncover vulnerabilities.

8. **Skill Assessment**  
   Application of the above techniques to solve practical challenges.

## Tools Used
- **ffuf:** A fast web fuzzer for finding vulnerabilities and hidden elements in web applications.
- **SecLists:** A collection of multiple types of lists used during security assessments, such as directory lists, sub-domain names, and parameter names.

## Example Commands
### Directory Fuzzing
```bash
ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ \
-u http://SERVER_IP:PORT/FUZZ

