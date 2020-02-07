# Apache

## Pre-User Web Directory

Each user can be permitted to have a web site in their home directory.

[Reference](!https://websiteforstudents.com/setup-apache2-userdir-module-on-ubuntu-16-04-lts-servers/)

### Enable userdir

> sudo a2enmod userdir

```
<IfModule mod_userdir.c>
        UserDir laravel/public
        UserDir disabled root

        <Directory /home/*/laravel/public>
                AllowOverride FileInfo AuthConfig Limit Indexes
                Options MultiViews Indexes SymLinksIfOwnerMatch IncludesNoExec
                Require method GET POST OPTIONS
        </Directory>
</IfModule>
```