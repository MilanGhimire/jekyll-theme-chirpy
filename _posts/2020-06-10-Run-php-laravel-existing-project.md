---
title: Run PHP Laravel project and how to host in shared hosting
author: Milan Ghimire
date: 2020-06-10 20:46:15 +05:45
categories: [Database]
tags: [untaged]
---

Following are the instructions:

`Run PHP`
`php artisan serve`

Changes need to do after cloning:
    1. Setup `.env` file
    2. `composer install` in the root folder
    3. `composer update` in the root folder
    4. `php artisan key:generate` in the root folder
    5. `php artisan config:cache`  to clear cache

Hosting to Share Hosting
./Public (Folder) To the website Path /public_html or root folder of the website
./* (Except Public) to different folder

then configure the path where the folder is kept in file of `./Pubic/index.php` in
`require __DIR__.'/../vendor/autoload.php';`
`$app = require_once __DIR__.'/../bootstrap/app.php';`

these files path

then configure the .env file database as for me like,

```
DB_CONNECTION=mysql
DB_HOST=mysql5019.site4now.net
DB_PORT=3306
DB_DATABASE=db_a53ca8_banquet
DB_USERNAME=a53ca8_banquet
DB_PASSWORD=Corei7pass
```

Change Email:
in .env use following: example:
```
MAIL_DRIVER=smtp
MAIL_HOST=smtp.gmail.com
MAIL_PORT=465
MAIL_USERNAME=mailreply580@gmail.com
MAIL_PASSWORD=iamwfmygadyisuqm
MAIL_FROM=mailreply580@gmail.com
MAIL_NAME=No-Reply
MAIL_ENCRYPTION=ssl
```
in mail.php