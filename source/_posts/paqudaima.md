---
abbrlink: ''
categories: []
date: '2023-11-07T21:07:22.646561+08:00'
tags: []
title: 图片爬取
updated: 2023-11-7T21:7:24.683+8:0
---
``

```
import urllib.request
import urllib.parse
import re
import os
def handlle_request(url,page):
	url = url + str(page) + '.html'
	# print(url)
	headers = {
	'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/116.0.0.0 Safari/537.36 Edg/116.0.1938.81',
	}
	request1 = urllib.request.Request(url,headers=headers)
	return request1
def download_img(content):
	pattern = re.compile(r'class="lazy"  data-original="(.*?jpg)!.*?".*?/dd>',re.S)
	lt = pattern.findall(content)
	print(len(lt))
	for image_u in lt:
		image_u = 'https:' + image_u
		pathename = 'zhuatu'
		if not os.path.exists(pathename):
				os.mkdir(pathename)
		filename =  image_u.split('/')[-1]
		filepath = pathename + '/' + filename
		print('%s图在下载中'%filename)
		urllib.request.urlretrieve(image_u,filepath)
		print('%s图在下载结束'%filename)
		time.sleep(1)
def main():
	url = 'https://www.tukuppt.com/sopng/gaoxiaobiaoqing/__zonghe_0_0_0_0_0_0_'
	s_page = int(input('请输入起始页:'))
	end_page  = int(input('请输入结束页:'))
	for page in range(s_page,end_page + 1):
		print('第%s页开始下载'%page)
		request = handlle_request(url,page)
		content = urllib.request.urlopen(request).read().decode()
		# print(content)
		download_img(content)
		print('第%s页开始下载……'%page)
		time.sleep(2)
if __name__ == '__main__':
  main()
```
