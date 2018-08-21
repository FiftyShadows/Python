pip3 install -i https://pypi.doubanio.com/simple/ gunicorn httpbin

gunicorn httpbin:app

curl -v http://www.imooc.com > tmp.txt



## urllib

- urllib和urllib2是相互独立的模块

- requests库使用了urllib3(多次请求重复使用一个socket)
