---
abbrlink: ''
categories: []
date: '2023-09-04T21:07:40.720812+08:00'
tags: []
title: URLlibprase
updated: 2023-9-4T21:7:56.893+8:0
---
urllib.parse
quote
url编码函数，将中文进行转化为%xxx
unquote url解码函数，将%xxx转化为指定字符
urlencode给一个字典，将字典拼接为query_.string

```
import urllib.parse


url = 'http://www.baidu.com/index.html?name=&pwd=123456'
# url编码
ret = urllib.parse.quote(url)

print(ret)
# url解码
re = urllib.parse.unquote(ret)
print(re)
```

```
import urllib.parse
url = 'http://www.baidu.com/index.html'
name = 'goudan'
age = 18
sex = 'nv'
height = '180'

data = {
	'name':name,
	'age':age,
	'sex':sex,
	'height':height,
}

# 遍历字典

lt = []
for k,v in data.items():
	lt.append(k + '=' +str(v))
query_string ='&'.join(lt)

print(lt)
# url = url +'?'+query_string

# print(url)
```

```
query_string = urllib.parse.urlencode(data)

print(query_string)

url = url + '?' +query_string

print(url)
```

response
read()读取相应内容，内容是字节类型
geturl()获取请求的url
getheaders()获取头部信息，列表里面有元组
getcode()获取状态码
readlines()按行读取，返回列表，都是字节类型

```
import urllib.request

abc = "http://www.baidu.com"

reponse = urllib.request.urlopen(url=abc)
# print(reponse.read().decode())

# with open('baidu.html','w', encoding='utf8') as f:
# 	f.write(reponse.read().decode())
# print(reponse.geturl())
# print(dict(reponse.getheaders()))
# print(reponse.getcode())
# print(reponse.readlines())
# with open('baidu2.html', 'wb') as f:
# 	f.write(reponse.read())

img_url = 'https://img2.baidu.com/it/u=3354585195,1512541150&fm=253&app=138&size=w931&n=0&f=JPEG&fmt=auto?sec=1693674000&t=5b9d9a7c11c5627c7b7bcb28b56ce8f2'

reponse = urllib.request.urlopen(url=img_url)
# with open('qing.jpg', 'wb') as f:
# 	f.write(reponse.read())
urllib.request.urlretrieve(img_url, 'chun.jpg')
```
