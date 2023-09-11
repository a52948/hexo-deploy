---
abbrlink: ''
categories: []
date: '2023-09-11T21:07:48.896312+08:00'
tags: []
title: urlpost请求方式
updated: 2023-9-11T21:7:49.916+8:0
---
```
import urllib.request
import urllib.parse
word = input('请输入要翻译的单词:')
post_url = 'https://fanyi.baidu.com/sug'
form_data = {
	'kw':word
}

headers = {
	'User-Agen':'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/116.0.0.0 Safari/537.36 Edg/116.0.1938.76'
}
# 注意form_data需要通过urllib.parse.urlencode转码转换成&拼接的方式，需要通过encode转换成字节形式
request = urllib.request.Request(url=post_url,headers=headers)
form_data = urllib.parse.urlencode(form_data).encode()
response = urllib.request.urlopen(request,data=form_data)
print(response.read().decode())
```
