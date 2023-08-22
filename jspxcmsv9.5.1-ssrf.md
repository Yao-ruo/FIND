Hi i found an Server-Side Request Forgery (SSRF) - Stored in jspxcms v9.5.1

What is SSRF?

Server-Side Request Forgery (SSRF) payload = url + '/cmscp/ext/collect/fetch_url.do'

First,obtain backend permissions url = url + '/cmscp/index.do'

![image](https://github.com/Yao-ruo/FIND/assets/94469929/bcbed2a4-3e3d-4812-959b-0cfbb1a55ad8)

Then, we go to  模块组件 > 采集管理 > 修改

![image](https://github.com/Yao-ruo/FIND/assets/94469929/650b8941-7f85-4e1c-98f1-2ada6611dad4)

We input `https://www.baidu.com` use 设置

![image](https://github.com/Yao-ruo/FIND/assets/94469929/ad6c2e15-0328-4cfc-b0a9-4d26c722c9ab)

Click to obtain the corresponding website source code

![image](https://github.com/Yao-ruo/FIND/assets/94469929/d18660ca-e8a3-478b-b543-84933ce78458)

Modify URL  , we can get SSRF.

![image](https://github.com/Yao-ruo/FIND/assets/94469929/59827585-554e-4f98-9fe7-776d2ae2225c)

