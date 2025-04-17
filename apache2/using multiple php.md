## Requirement

 - php versi safe
 - apache lounge
 - text editor
## Step step

 1. Install Apache2 windows version
 2. buka cmd dengan akses Administrator, pada directory tempat apache di extract contoh **apache24/bin**
 3. jalankan perintah `httpd -k install -n "apache2-php7"` lau tekan enter
 4. periksa pada service windows apakah sudah ada service baru dengan nama **apache2-php7** jika ada lanjut tahap selajutnya
 5. Edit **httpd.conf** pada folder **apache24/conf**
 6. edit server root **ServerRoot** edit sesuaikan dengan directory tempat apache2 terinstall
 7. edit server root **ServerName** isikan `localhost`
 8. tambahkandi akhir baris kode berikut:	 

	    

> LoadModule php7_module "C:\webSvr\php-7.4.9\php7apache2_4.dll"
>         AddHandler application/x-httpd-php .php
>         PHPIniDir "C:\webSvr\php-7.4.9"

> sesuaikan kode diatas dengan kebutuhan php

 9. Download php 7.4.9 dan extract dengan nama folder **php -7.4.9** 
 10. duplicate & rename file **php.ini-production**  menjadi **php.ini** 
 11. Jalan kan service **apache2-php7**

> Lakukan hal yang sama untuk versi php berbeda dengan folder apache
> tersendiri & jangan lupa atur port


##Permasalahan Extension yang tidak terload dengan benar 
- **;extension=intl** to this **extension=intl**
- edit php.ini
> ; On windows:
> extension_dir="E:\xampp\php\ext"
- I found a way to do that which works for me. What I did is to copy the all the files containing this name icu****.dll from my php directory into the Apache bin directory then restart my server. The icu****.dll files are up to 4 in my own php directory.
