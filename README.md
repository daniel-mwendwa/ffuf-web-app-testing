# FFUF Web Application Testing

## Overview
This repository demonstrates the use of `ffuf`, a web fuzzing tool, to identify vulnerabilities in web applications. Techniques covered include directory fuzzing, page fuzzing, recursive fuzzing, sub-domain fuzzing, vhost fuzzing, parameter fuzzing, and value fuzzing. Below is the consolidated workflow demonstrating these techniques.

```bash
# Directory Fuzzing
ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ \
-u http://SERVER_IP:PORT/FUZZ

# Page Fuzzing
ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ \
-u http://target_ip:port/blog/FUZZ.php -ic

# Recursive Fuzzing
ffuf -w /opt/useful/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt:FUZZ \
-u http://SERVER_IP:PORT/forum/FUZZ \
-recursion -recursion-depth 1 -e .php -v

# Sub-domain Fuzzing
ffuf -w /opt/useful/SecLists/Discovery/DNS/subdomains-top1million-5000.txt:FUZZ \
-u https://FUZZ.hackthebox.eu/

# Vhost Fuzzing
ffuf -w /opt/useful/SecLists/Discovery/DNS/subdomains-top1million-5000.txt:FUZZ \
-u http://ip:PORT/ -H 'Host: FUZZ.academy.htb' -fs 986

# Parameter Fuzzing
ffuf -w /opt/useful/SecLists/Discovery/Web-Content/burp-parameter-names.txt:FUZZ \
-u http://admin.academy.htb:PORT/admin/admin.php?FUZZ=key -fs 227

# Value Fuzzing
ffuf -w ids.txt:FUZZ \
-u http://admin.academy.htb:port/admin/admin.php -X POST \
-d 'id=FUZZ' -H 'Content-Type: application/x-www-form-urlencoded' -fs 768
