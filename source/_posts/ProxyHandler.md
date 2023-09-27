---
abbrlink: ''
categories: []
date: '2023-09-27T20:11:02.333786+08:00'
tags: []
title: ProxyHandler
updated: 2023-9-27T20:11:3.459+8:0
---
```
import urllib.request
import urllib.parse

handler = urllib.request.ProxyHandler({'http':'1.1.1.1:8888'})
opener = urllib.request.build_opener(handler)

url = 'https://www.baidu.com/s?ie=utf-8&f=8&rsv_bp=1&rsv_idx=1&tn=baidu&wd=ip'
headers = {
	'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/116.0.0.0 Safari/537.36 Edg/116.0.1938.81',
}

request = urllib.request.Request(url,headers=headers)
response = opener.open(request)

with open('ip.html','wb') as ap:
	ap.write(response.read())
```
