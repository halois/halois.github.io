---
layout : post
title : "python写了个爬知乎帖子里图片的爬虫"
category : python
date : 2016-09-01
tags : [python,爬虫]
SyntaxHihglighter: true
shTheme: shThemeDefault 
duoshuo: true 
---

今天突然想换个桌面背景图，于是就百度一下搜搜看有什么好看的高清壁纸。搜索一会没有找到特别好的，突然想到在知乎看有没有人分享了桌面壁纸。



果不其然，知乎还是很有质量的，虽然看到的一个帖子问题已关闭，但是里面的资源还是很丰富的，于是乎就有了下面这个小爬虫

``` python
# 下载知乎某帖子里的图片。 
import urllib.request
import re,os

def open_url(url):
    req = urllib.request.Request(url)
    # req.add_header('User-Agent','*') # *需要自己填
    page = urllib.request.urlopen(req)
    html = page.read().decode('utf-8')
    page.close()
    return html

def get_img(html):
    p = r'data-original="([^"]+)"'
    imglist = re.findall(p,html)
    imglist = list(set(imglist)) #把重复的链接去除
    num = len(imglist)
    print('共有'+str(num)+'幅图')
    
    for each in imglist:
        filename = each.split('/')[-1]
        if os.path.exists(filename):
            continue
        else:
            urllib.request.urlretrieve(each,filename,None)
            print(filename,'保存好了')

if __name__ == '__main__':
    url = 'https://www.zhihu.com/question/21180335' #'http://www.zhihu.com/question/38824940'
    get_img(open_url(url))
```

于是得到了一堆图可供挑选作背景。