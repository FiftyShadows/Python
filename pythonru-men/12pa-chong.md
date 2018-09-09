```
accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8

accept-encoding: gzip, deflate, br

accept-language: zh-CN,zh;q=0.9,en-US;q=0.8,en;q=0.7
```




##爬虫前奏

- 明确目的

- 找到数据对应的网页

- 分析网页的结构找到数据所在的位置



- 模拟HTTP请求，向服务器发送这个请求，获取到服务器返回给我们的HTML

- 用正则表达式提取我们要的数据(名字、人气)





##断点调试






##VS调试快捷键

- F5调试

- F10单步执行

- F5跳到下一个断点

- F11进入某一个函数或者对象内部

- ctrl + shift + o快速找到方法





##数据分析

- 尽量选择具有唯一标识性的标签作为正则定位标签

- 尽量寻找最接近于数据的标签

- 选择标签时尽量要去选择可以闭合的标签





##总结

- 一个主方法

- 主方法里展现数据处理的每个流程和步骤

- 多写平级函数，少写嵌套函数

- 模块，类，方法的注释：多行字符串注释(块注释)

- 单行代码注释：在代码上注释，空一行

-  不要在一个函数里写太多行代码(不利于阅读)，函数名是对函数作用最好的描述，函数体积越小越灵活，复用方便，控制在10行到20行之间





##高级爬虫

- BeautifulSoup

- Scrapy多线程分布式

- 爬虫与反爬虫

- ip被封，频率    代理ip库



```py
from urllib import request
import re

class Spider():
    url = 'https://www.panda.tv/cate/kingglory?pdt=1.24.s1.53.3vu3h1fc7ou'
    reg_video = '<div class="video-info">([\s\S]*?)</div>'
    reg_name = '</i>([\s\S]*?)</span>'
    reg_num = '<span class="video-number">([\s\S]*?)</span>'

    def __fetch_content(self):
        r = request.urlopen(Spider.url)
        #这里的htmls是bytes；字节码
        htmls = r.read()
        htmls = str(htmls, encoding = 'utf-8')
        return htmls

    def __analysis(self, htmls):
        root_htmls = re.findall(Spider.reg_video, htmls)

        anchors = []
        for html in root_htmls:
            name = re.findall(Spider.reg_name, html)
            name = name[0].strip()
            num = re.findall(Spider.reg_num, html)
            num = num[0].strip()
            anchor = {'name': name, 'num': num}
            anchors.append(anchor)
        return anchors

    def __sort(self, anchors):
        anchors = sorted(anchors, key = self.__sort_seed, reverse=True)
        return anchors

    def __sort_seed(self, anchor):
        r = re.findall('\d*', anchor['num'])
        number = float(r[0])
        if '万' in anchor['num']:
            number *= 10000
        return number

    def __show(self, anchors):
        for rank in range(0, len(anchors)):
            print('第' + str(rank + 1) + '名' + '-------' + anchors[rank]['name'] + '-------' + anchors[rank]['num'])

    def go(self):
        htmls = self.__fetch_content()
        anchors = self.__analysis(htmls)
        anchors = self.__sort(anchors)
        self.__show(anchors)


spider = Spider()
spider.go()

```









