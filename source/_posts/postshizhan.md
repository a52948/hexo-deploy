---
abbrlink: ''
categories: []
date: '2023-09-14T21:28:10.865048+08:00'
tags: []
title: postfanyi
updated: 2023-9-14T21:28:12.944+8:0
---
```
import urllib.request
import urllib.parse
word = 'wolf'
post_url = 'https://fanyi.baidu.com/v2transapi?from=en&to=zh'
hearders = {
	'Host': 'fanyi.baidu.com',
	'Connection': 'keep-alive',
	# 'Content-Length': '151',
	'sec-ch-ua': '"Chromium";v="116", "Not)A;Brand";v="24", "Microsoft Edge";v="116"',
	'sec-ch-ua-mobile': '?0',
	'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/116.0.0.0 Safari/537.36 Edg/116.0.1938.76',
	'Content-Type': 'application/x-www-form-urlencoded; charset=UTF-8',
	'Accept':'*/*',
	'Acs-Token': '1694697149072_1694697161652_grIp1xN+4+O/Mqn+6QlRIgL1Te8vSgV6C8hOOM7Mh0OgGOQH0s1M2znTlV3aMw7uHtlwq9VAfe/jAJeJyYiQko2u2IwKJ0m2pXpWVwUiwy8mGxihQqbRoSihR6C92JJoimguIQ9FIlV0FUSg3vXoD6434WnzN4kj3ewmDNk4Jcd9BZ8WQUjsOcvldlm8yvIQXessa0w/X6QAzQ813jzKaU7u2Ri8j8MLG2NYGGpJqUxSOd9xt/GiVsxfTVNj1u0K/EZatLKTqt+pjXR726eqRj7x6LuY56KI6JUS1ce9vng0OeFAU1vYxE7GoDTkoCnJxII4lDW+oZvWFau8JtUJeEYQ/kP4N3XgtjWcfeHdlY4gu6a5aFBga2AH1MhtcvPVnlckloNELES72ewsXORWENaoFLY2fwMwn9g6ii5oMgw5oFaI3GM0eFanwaimPrSkmW9oDxxGlZyTx3ul4kZRujCmbsTgYeUn5LC6ZORbDzDQnP9QKZmnvveKJgTTwI5kAbm1IYSCPhp+/qVsoDxDDmTOcmpNwEH6AiWlRSjPw3U=',
	'X-Requested-With': 'XMLHttpRequest',
	'sec-ch-ua-platform': '"Windows"',
	'Origin': 'https://fanyi.baidu.com',
	'Sec-Fetch-Site': 'same-origin',
	'Sec-Fetch-Mode': 'cors',
	'Sec-Fetch-Dest': 'empty',
	'Referer': 'https://fanyi.baidu.com/',
	# 'Accept-Encoding': 'gzip, deflate, br',
	'Accept-Language': 'zh-CN,zh;q=0.9,en;q=0.8,en-GB;q=0.7,en-US;q=0.6',
	'Cookie': 'BIDUPSID=5400077289767CBECB57585BA613A703; PSTM=1690891215; BAIDUID=5400077289767CBECB57585BA613A703:SL=0:NR=10:FG=1; REALTIME_TRANS_SWITCH=1; FANYI_WORD_SWITCH=1; HISTORY_SWITCH=1; SOUND_SPD_SWITCH=1; SOUND_PREFER_SWITCH=1; MCITY=-268%3A308%3A; BAIDUID_BFESS=5400077289767CBECB57585BA613A703:SL=0:NR=10:FG=1; ZFY=grTbJMiejhfvuT9DratFBB3dGiB:BbSrz5XFE3OniQew:C; BAIDU_WISE_UID=wapp_1694605716567_839; RT="z=1&dm=baidu.com&si=6d19c296-2398-4671-9638-f474519761d6&ss=lmhohlwc&sl=4&tt=3lf&bcn=https%3A%2F%2Ffclog.baidu.com%2Flog%2Fweirwood%3Ftype%3Dperf&ld=3xxf"; BA_HECTOR=05a08l0k210485a42l81ag0s1ig5ug01p; BDORZ=B490B5EBF6F3CD402E515D22BCDA1598; BDRCVFR[feWj1Vr5u3D]=I67x6TjHwwYf0; PSINO=1; delPer=0; H_PS_PSSID=39329_39362_39280_39349_39097_39198_39293_39261_39358_39377_39233_26350; Hm_lvt_64ecd82404c51e03dc91cb9e8c025574=1694093886,1694435195,1694694017; APPGUIDE_10_6_2=1; PPA_CI=afadc0f2cb4aff67ec9de4e1705c4b31; Hm_lpvt_64ecd82404c51e03dc91cb9e8c025574=1694697149; ab_sr=1.0.1_OTZkMGYyZWZmYjkzYjgyYWMzYWRmYWZkODJiYTQ5YWI3NjY4NDU5OGZkZmUyNzhlYzAxZmM4YjJkMTkxMjUzN2MzZDQzMmI3M2FmNDdkYTA1OWI4MmZmM2VjZDU3NmI2Y2ZmZDg3Zjk4YmYzODQ3MzIwMmQwZTUxMTJhMjRiOGJlMjZmNWZjNjZjNTgzNzcwNmNjMDMwZDZmOTkyYjNlMQ==',
}

form_data = {
'from':'en',
'to':'zh',
'query':'wolf',
'transtype':'realtime',
'simple_means_flag': '3',
'sign':'275695.55262',
'token':'0d0fc210f005dbe0c3c529c02b7d5447',
'domain' : 'common',
'ts' : '1694697161625',
}

request = urllib.request.Request(url=post_url,headers=hearders)

form_data = urllib.parse.urlencode(form_data).encode()

response = urllib.request.urlopen(request,form_data)

print(response.read().decode())
```
