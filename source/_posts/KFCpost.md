---
abbrlink: bdtbpq
categories: []
date: '2023-09-19T20:12:08.137246+08:00'
tags: []
title: 百度贴码爬取
updated: 2023-9-19T20:12:12.0+8:0
---
```

import urllib.request
import urllib.parse

url = 'http://www.kfc.com.cn/kfccda/ashx/GetStoreList.ashx?op=keyword'
word = input('请输入你要查的内容：')
page = input('shuzi')
pagesz= input('sz')
formodata = {
	'cname':'' ,
	'pid':'' ,
	'keyword': word,
	'pageIndex': page,
	'pageSize': pagesz,
}

headers = {
	'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/116.0.0.0 Safari/537.36 Edg/116.0.1938.81',
}

formodata = urllib.parse.urlencode(formodata).encode()

request = urllib.request.Request(url=url,headers=headers)

response = urllib.request.urlopen(request,data=formodata)

print(response.read().decode())
```

进阶版本，生成网页保存到本地

```
import urllib.request
import urllib.parse
import os
url = 'https://tieba.baidu.com/f?ie=utf-8&'

bmname = input('请输入吧名：')
stnpage = int(input('请输入起始页码：'))
enpate = int(input('请输入结束页码：'))

if not os.path.exists(bmname):
	os.mkdir(bmname)
for page in range(stnpage,enpate+1):
	data={
	'kw':bmname,
	'pn':(page - 1)*50,
	}
	print('第%s页开始下载……'%page)
	data= urllib.parse.urlencode(data)
	urlpg = url+data
	# print(urlpg)
	headers = {
	'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/116.0.0.0 Safari/537.36 Edg/116.0.1938.81',
	}
	request = urllib.request.Request(url=urlpg,headers=headers)
	response = urllib.request.urlopen(request)
	filename = bmname + '_'+ str(page) + '.html'
	filepath = bmname + '/' + filename

	with open(filepath,'wb') as pf:
		pf.write(response.read())
	print('第%s页下载结束……'%page)
```
