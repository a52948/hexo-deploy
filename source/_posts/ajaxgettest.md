---
abbrlink: ''
categories: []
date: '2023-09-15T21:39:16.306065+08:00'
tags: []
title: ajaxget请求测试
updated: 2023-9-15T21:39:36.0+8:0
---
```
import urllib.request
import urllib.parse

url = 'https://movie.douban.com/j/chart/top_list?type=5&interval_id=100%3A90&action=&'
headers = {
	'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/116.0.0.0 Safari/537.36 Edg/116.0.1938.81',
}

page = int(input('请输入覃查询的页数：'))

number = 20


data = {
	'start':(page - 1)*number,
	'limit':number,
}


url += urllib.parse.urlencode(data)

# url += query_str

request = urllib.request.Request(url,headers=headers)

response = urllib.request.urlopen(request)

print(response.read().decode())
```
