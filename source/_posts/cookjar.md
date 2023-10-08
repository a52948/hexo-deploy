---
abbrlink: ''
categories: []
date: '2023-10-08T21:07:32.277815+08:00'
tags: []
title: cookjar
updated: 2023-10-8T21:8:15.406+8:0
---
```
import urllib.request
import urllib.parse
import http.cookiejar

cj = http.cookiejar.CookieJar()

handler = urllib.request.HTTPCookieProcessor(cj)
opener = urllib.request.build_opener(handler)


post_url = 'https://passport.aliyundrive.com/newlogin/login.do?appName=aliyun_drive&fromSite=52&_bx-v=2.5.3'

formdate = {
	'loginId':	'13048971844',
	'password2':'596d136ac3b157af97b2cce708a5fccc77f38e7b902825ad456fc1c0ecc9a21faf052587240ec11222e1755184d206d4f07c0ca1ad8ed3e9767c507e443bd005f07c79153a8ab6a1ec240d73a151ade606836a67e62b3c158c80177667a8702ddd21668eb44eb096545a6ebfba072133e5740de7c3cfd75be4e7b2312c79a2bf',
	'keepLogin':'false',
	'ua':'140#0MrD7pwszzFhjQo22idsCtSdvzyDfqQcddSkY6TiFjTW294SrhEok2v+cTcvg2qDCbJdR4s7Hzh6Cc1vxFM/ZyTt93hqzznNH7hMg/QzzWF2ijlBUbzx2DD3VthqzFHjl5hwlymLzPrSI2v/tFzx2DccPHkN0FriN1832Pzx18fVtl7uMFKk2P3iR35XzFK62X1tlplyzPKIV26mDpipONdOHaU+UC1B8myB8vEUOvVfFWw/RlOA8S3QMXgw57UcQMFG/PwzdA5gUx/CE01XApPcjvGBwphUWZiqdRtGEheRmYsSbHmqpK4OlbqfZYblFc7EBrqNJQaz1E5kvvbjB28dE3MBtN27xWNMpYDmdRP3j+JuNDbxCV4q5fuP3UzYtBKrxR9iLmL/q7+lllYJaXnrJoUBRgQfseq1J7iCLzoEpzY3r8cgRR5IaFdcjv28C/VK9nMyxEfVvIXsV3HznDouwnGj4/zTBMtFhJA0qsvVfXCqNENF4XQT48pAsv7BG5fAYPnwna0Z2KI5OvaYssbImYJfI/+tfgT8riV0zD2o4URE9QM/BJLyNb/Jf/PJMcxGxL2Rw5sShV18WC13m3M+Q9IrTkqpvUF7YzyHPC2c5gyhPxyv3faOQRO+xWBNOOZ1QaHASU5fKOa5YOaBMaOruPB+vu1l7vnIgy2iJuGB/DTQ3GIyTxhelmTQium+aWfJhOKGf++7nSTD7jjfhWkWOdDOJaTYyEeKezXmHC1ZfRixAOz+x3lobXJqTpg8tazdm5O8zJ07X0rH58ni95eunYOYCO02WXi3KwcEh/j/OWUon7pvfgIDeYRygras4KJrJ40waAampcT6RSzCccWTPZl4UQKdDM3xyEfhWVqvBR54aL4cKFjyQLUcfAgBUW4FerdLk+0xAIp+uoz91odgrTacrc7glDl74SpYEvTtdCA4imJu1Gj+kRBLUA9p7x89zj9ArEFsJgEnDgCjya1vfaF1q8qEwkQ/JUjOtEDPEj/SfForx2IjcDczVoe7GwEPR/AczOHVcyOIvdsdnkeosrWcj+EBQXdZOdsG2KdomiNauflpbTRwV010ho4d733H7qaoQuMLCthQHSF4cGwMnNKzQkNrHESozPTIlB8T0uQjc1DPZ/FbpiwDwYEWrgCbozjqzdRi/Ead2FbV3PHtEKRocgTZxudnxmASaEVqmLNsleW5IT/wfSGjSKlYu9ucaKpWYa5qW2PUz35oLn0CX7QQiwTW8Bn7LC4K+Wn8SMNG2WqyiePqk0Wu/NRbzLv1lnglBEeJqazebP/uQKQqgQERyZeHFRGpT/WfVNMCafCCY3bgVZgiW1Rfs1b3aY8vnkGSaSh41s6ssc1kyuqUYsZ8c8r=',
	'umidGetStatusVal':	'255',
	'screenPixel':'1366x768',
	'navlanguage':'zh-CN',
	'navUserAgent':'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/117.0.0.0 Safari/537.36 Edg/117.0.2045.60',
	'navPlatform':'Win32',
	'appName':'aliyun_drive',
	'appEntrance':'web_default',
	'_csrf_token':'FfwbFzvIafN1kuKIvgHNU7',
	'umidToken':'5280a418a9f64e7b3a4eb7d4c97e2a5f4d647725',
	'isMobile':'false',
	'lang':'zh_CN',
	'returnUrl':'',
	'hsiz':'19a4f1a609be0e777d4629117fcc3300',
	'fromSite':'52',
	# 'bizParams':'renderRefer=https%3A%2F%2Fauth.aliyundrive.com%2F',
	'umidTag':'SERVER',
	# 'weiBoMpBridge':'',
	'deviceId':'x0KNHYUPnBECAdud0e5WdLze',
	'pageTraceId':'213e1f0816967659735417881e2016',
	'bx-ua':'226!0M2X6eGRblMeahbvPW0vlGJe2twZOGpzS7/Yjk22kHo6NzYPdBj6fYiSOUy6Ns4rbFLBfTlJEnIIRbCrNkWZC7b9feqn4BVjx36as869lMpGg/LonxB71uCnUieTycidBPYPbIdoW6KMq1h2mA2CArq5PU9bghCs6rJwjNzmEiWsnO1LMzybjqEM/fPM7LmlVEkxnyTUt92Kj2Wk Iq0vH2WfpDYOxnBezL7nTDZE9itf Q qFH12xgQK0iRjhQmQyQs38WqfYmhzO9W3DaHpXbZg8IMQWrCBZQs38TldUNHfsCLcVw4q503nFNev/bSgjWO2zMtqcrMRWGeWAiBvhRuMY92yUafnyMsUQQLyoh5v2lpWqiv4gv8lzy9HDoeycWAOJn3soDv4y4Jj2oM0DksHkjwH5hTbmWDOED7s5JBs9xuA4OQq5s6pp/q8DkEbvwWOEWxghUlsqyeUSJHeR5eMfxwnucIb01aDknceorlIVG9jZ1svsu0zwYynhW5emsaKiOGgguHbXqdj2004uUwl3lMdURzgs7cS8wl8Ic7zmga2gBfp9Zcg8D9yUlkneaR35QlyVchG1qDGU0b5Xbogvl2hnuahYcR3BRlyVmc/m/j3Dk1HmhvvnyZpDkMQbb5kMs6qe1twSqvkhaHyAg0EntjeysfgsEikdzzHgUhwXtDkWaMs0g/g8/ZyvKw/yasJQ0/sKOVehMCsgbQ/lY7r6ubssUM2bzAp6n0Wta8UXxKq1Ky41nal rxvAtOkUVLw2HrF1HYROGuaE/lMaXeAMIWRvWsFtvUzqlHMDCmPH DiuWzjMUXg55u6dTBbUIV5uyTUVR f3PL9N0gOtfyHrlZYbc03Af a54uwfBL9m3i 4vHoZpp3XZOli3bqPa8X4Osi5reJA1EHVVAmt7i8HwsPhTATRYb6WEOVpyJbvRN 5EkZjQrkrSNw8hgGl4xOreUqPTQtgqRksmHzn3mpbxbJDbdP1N/UXJNtQIFilT4rwbMxKX9jtCN/4p NBbfXeRg1ucBulBEGHyL//jK ZEqbQb8vYK04VFs/er0jybbEXfboCx5VXvZC/RkLQJF8xJUX2BUGQzhU513Yd3dQgTfyT 391dRwZCY70P4hngLw3GpBmwLlmnN3XRwRoybr6TG5JcXUERiD4CrCPD4NU20/6PkabsMmN3Es5tdqLTPXg OiET8AUhezUBhyKcObfXC3svb7IzFc3TIwFNwBolLUxVyTCbRbwzyv5bNFTGNOhHS2FgUUxXEP0n2c8758BlrD6Q0fw4aszYZN5YrjL1 2uPpqvYRaNhsptCRhhZJWXUt9TWUi8LrlmsAEWf=',
	'bx-umidtoken':'G97A4A441E3ED6EBFBE44DAA7D658DB9A059EAC10AF8DEAF941',
	}

headers = {
	'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/116.0.0.0 Safari/537.36 Edg/116.0.1938.81',
}

request = urllib.request.Request(post_url,headers=headers)
formdate = urllib.parse.urlencode(formdate).encode()

response = opener.open(request,data=formdate)

print(response.read().decode())
```

正规表达式测试学习

```
import re

string = '<p><div><span>test</span></div></p>'

patter = re.compile(r'<(\w+)><(\w+)>\w+</\2></\1>')

ret = patter.search(string)

print(ret)
```
