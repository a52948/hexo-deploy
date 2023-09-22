---
abbrlink: ''
categories: []
date: '2023-09-22T19:27:26.655150+08:00'
tags: []
title: nameerror与httperror
updated: 2023-9-22T19:27:26.334+8:0
---
```
import urllib.request
import urllib.parse
import urllib.error

url = 'https://www.jb51.cc/yingyong/292607.htm'


try:
	response = urllib.request.urlopen(url)
	print(response)
except urllib.error.HTTPError as e:
	print(e)
	print(e.code)
# except urllib.error.URLError as e:
	# print(e)
```
