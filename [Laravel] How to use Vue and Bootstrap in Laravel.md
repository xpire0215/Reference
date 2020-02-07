# Laravel - How to use Vue and Bootstrap in Laravel

## Use composer

* If your composer.phar is not at global environment, execute the below command.

> sudo mv composer.phar /usr/local/bin

* Move to the laravel project root directory

	For example:
	
	* Create a new laravel project
	
	> composer create\-project laravel/laravel blog
	
	> cd blog (The root directory of the project)

* Install the Vue and Bootstrap to Laravel

> (/blog)

> composer require laravel/ui \-\-dev

> \-\-dev (optional, I don't know what it does)

> php artisan ui vue

> php artisan ui bootstrap

## (Optional, require with global mode)

If use the below command

> composer global require laravel/ui

It will save the laravel/ui in ~/.composer (Mac) or ~/.config (Ubuntu)

After that, "composer require laravel/ui" will use the cached files in ~/.composer or ~/.config

Save the downloading time
