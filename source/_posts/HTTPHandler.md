---
abbrlink: ''
categories: []
date: '2023-09-25T20:17:53.328558+08:00'
tags: []
title: HTTPHandler
updated: 2023-9-25T20:17:54.591+8:0
---
自动产生cookie的http请求练习。

```
import urllib.request
import urllib.parse

url = 'https://www.baidu.com'
headers = {
	'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/116.0.0.0 Safari/537.36 Edg/116.0.1938.81',
}

headler = urllib.request.HTTPHandler()
opener = urllib.request.build_opener(headler)

request = urllib.request.Request(url=url,headers=headers)

response = opener.open(request)

print(response.read().decode())
```
