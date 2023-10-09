---
abbrlink: ''
categories: []
date: '2023-10-09T21:20:29.829015+08:00'
tags: []
title: title
updated: 2023-10-9T21:20:31.875+8:0
---
```
import re

# string = '<p><div><span>test</span></div></p>'

# patter = re.compile(r'<(\w+)><(\w+)>\w+</\2></\1>')

# ret = patter.search(string)
# string = '<p><div><span>test</span></div></div></p>'
# patter = re.compile(r'<div>.*</div>')

string = '''hate you 
love you to
love you me 
love you he
'''
patter = re.compile(r'^love', re.M)
ret = patter.findall(string)
print(ret)

```

```
string = '''hate you 
love you to
love you me 
love you he
'''
# 这里需要注意的是re.M 与re.S re.M 的意思的每一行作为单独行的去匹配，re.S 是把所有的数据压缩成一行去匹配
# patter.search() 任意位置查
# patter.findall() 查所有 这三种匹配模式
# patter.match()
patter = re.compile(r'^ha.*', re.S)
ret = patter.findall(string)
print(ret)

```
