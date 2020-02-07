# Laravel Installation

## Reference

[Install laravel on Ubuntu 18.04](https://www.hostinger.com/tutorials/how-to-install-laravel-on-ubuntu-18-04-with-apache-and-php/)

## Install php
 
### Ubuntu

> sudo apt install php 

### Mac

> brew install php 

## Install Composer

[Download Composer and Install](https://getcomposer.org/download/)

> wget https://getcomposer.org/download/1.9.0/composer.phar

* Make composer.phar excutable

> chmod +x composer.phar

* Move to bin directory

> sudo mv composer.phar /usr/local/bin/composer

* Install the requirement 

### Ubuntu

> sudo apt install libapache2-mod-php php-common php-xml php-zip php-mbstring php-mysql php-xmlrpc php-soap php-gd php-cli php-bcmath php-tokenizer php-json php-pear

### Mac

> Unknown or it doesn't need to install anymore.

* Install Laravel

> composer global require laravel/installer

## Include Laravel's bin directory

> vim ~/.profile

* Add the following line to the bottom

### Ubuntu

> export PATH="$HOME/.config/composer/vendor/bin:$PATH"

![Export](./img/laravel-installation/profile.png)

### Mac

> export PATH="$HOME/.composer/vendor/bin:$PATH"

* Load the new configuration

> source ~/.profile

## Create the new project

> composer create-project --prefer-dist laravel/laravel blog

* After installing laravel/laravel, it could use 

> laravel new blog

* Move to web directory

> sudo mv blog /var/www/html

## Install MySQL

### Ubuntu

> sudo apt install mysql-server

### Mac

> brew install mysql

### Optional
```
sudo mysql_secure_installation

Remove anonymous users? [Y/n] y
Disallow root login remotely? [Y/n] n
Remove test database and access to it? [Y/n] y
Reload privilege tables now? [Y/n] y
```

## Change www directory to laravel public and enable .ht file

### Ubuntu

* Chagne to laravel public

> cd /etc/apache2/sites-available

> sudo cp 000-default.conf blog.conf

```
# Uncomment ServerName
ServerName blog/public
# Modify DocumentRoot
DocumentRoot /var/www/html/blog/public

# Enable .htaccess
<Directory /var/www/html/blog/public>
	Options Indexes FollowSymLinks
	AllowOverride All
	Require all granted
</Directory>
```

* Disable default site and enable blog site

> sudo a2dissite 000-default.conf

> sudo a2ensite blog.conf

### Mac

* Change to laravel public

> sudo vi /usr/local/etc/httpd/httpd.conf

```
# Change Document and Directory to laravel public
DocumentRoot "/usr/local/var/www/blog/public"
<Directory "/usr/local/var/www/blog/public">

    Options Indexes FollowSymLinks

    AllowOverride All

    Require all granted
</Directory>
```
* Enable php file

```
<IfModule dir_module>
    DirectoryIndex index.php index.html
</IfModule>

<FilesMatch \.php$>
    SetHandler application/x-httpd-php
</FilesMatch>
```

## Enable Apache to access the directory

### Ubuntu

> sudo chgrp -R www-data /var/www/html/blog 

> sudo chmod -R 775 /var/www/html/blog/storage

> sudo chmod -R 775 /var/www/html/blog/bootstrap/cache

### Mac

* Check the group name in Mac

> cat /usr/local/etc/httpd/httpd.conf | grep Group

```
# User/Group: The name (or #number) of the user/group to run httpd as.
Group _www
``` 

> sudo chgrp -R _www /usr/local/var/www/blog

> sudo chmod -R 775 /usr/local/var/www/blog/storage

> sudo chmod -R 775 /usr/local/var/www/blog/bootstrap/cache

## Enable Apache rewrite module and php module

### Ubuntu

> sudo a2enmod rewrite

### Mac

> sudo vi /usr/local/etc/httpd/httpd.conf

```
# Uncomment mod_rewrite
LoadModule rewrite_module lib/httpd/modules/mod_rewrite.so

# Add php module
LoadModule php7_module /usr/local/opt/php@7.3/lib/httpd/modules/libphp7.so
```

## Restart apache2

> sudo systemctl restart apache2
