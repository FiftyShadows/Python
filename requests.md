pip3 install -i https://pypi.doubanio.com/simple/ gunicorn httpbin

gunicorn httpbin:app

curl -v http://www.imooc.com > tmp.txt



## urllib

- urllib和urllib2是相互独立的模块

- requests库使用了urllib3(多次请求重复使用一个socket)



## r.elapsad

print(r.elapsed.microseconds) #网上很多资料写的是用microseconds获取响应时间，再除1000*1000得到时间为秒的单位，当请求小于1s时，发现不出什么问题。如果时间超过1s，问题就来了。（很显然，大于1s的时候，只截取了后面的小数部分）3.所以获取响应时间的正确姿势应该是：r.elapsed.total_seconds()，单位是s

```
data.elapsed                             0:00:03.715776
data.elapsed.total_seconds()             3.715776
data.elapsed.microseconds                715776
data.elapsed.seconds                     3
data.elapsed.days                        0
data.elapsed.max                         999999999 days, 23:59:59.999999
data.elapsed.min                         -999999999 days, 0:00:00
data.elapsed.resolution                  0:00:00.000001
```