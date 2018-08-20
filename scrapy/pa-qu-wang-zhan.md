pip3 install -i https://pypi.doubanio.com/simple/ scrapy

scrapy startproject ArticleSpider

scrapy genspider jobbole blog.jobbole.com

pip install pypiwin32

scrapy crawl jobbole

# Obey robots.txt rules
ROBOTSTXT_OBEY = False




## xpath

![](/assets/360截图18310112101104121.png)

![](/assets/360截图17001016867485.png)

![](/assets/360截图17001015556675.png)


scrapy shell http://blog.jobbole.com/110287/

title = response.xpath('//*[@id="post-110287"]/div[1]/h1/text()')    //text会忽略掉子元素

title.extract()[0]

title.extract()[0].strip()

title.extract()[0].strip().replace('·', '').strip()

response.xpath('//span[contains(@class, 'vote-post-up')]');











