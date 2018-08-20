scrapy

requests

beautifulsoup


## 技术选型

- scrapy是框架

- scrapy框架中可以加入requests和beautifulsoup库

- scrapy基于twisted，性能是最大的优势

- scrapy方便扩展，提供了很多内置的功能

- scrapy内置的css和xpath selector非常方便，beautifulsoup最大的缺点就是慢



## 正则

![](/assets/360截图17290430372218.png)



## 深度优先

- 递归实现

- 递归太深，会栈溢出

![](/assets/360截图17571120446868.png)




## 广度优先

- 队列实现

![](/assets/360截图186411307011392.png)



## 字符串编码

![](/assets/360截图16270829516461.png)

![](/assets/360截图1648022981111121.png)

![](/assets/360截图1878042170114108.png)




## 爬虫去重策略

1. 将访问过的url保存到数据库中

2. 将访问过的url保存到set中，只需要o(1)的代价就可以查询url，内存占用会越来越大

3. url经过md5等方法哈希后保存到set中

4. 用bitmap方法，将访问过的url通过hash函数映射到某一位

5. bloomfilter方法对bitmap进行改进，多重hash函数降低冲突























