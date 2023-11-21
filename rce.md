There is an RCE vulnerability in the intelligent management platform of Byzro Networks Smart S210 multi-service security gateway.

Vulnerability location:/Tool/repair.php

version：S210

1. The login interface is as shown in the figure.

![image](https://github.com/houhuidong/cve/assets/151603975/0a377256-1af0-4107-bdcf-fbb585a5130a)

2. Execute the SQL statement and write it to the shell.
![image](https://github.com/houhuidong/cve/assets/151603975/11166cc5-9828-42ec-a95d-0fce22e1e4fe)

Then execute the poc:

![image](https://github.com/houhuidong/cve/assets/151603975/47d91c29-ffd9-41e8-8c25-5f44c194ecbd)
