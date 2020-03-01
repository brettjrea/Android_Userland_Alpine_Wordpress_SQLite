# Android_Userland_Alpine_WP_SQLite

A setup script and breakdown to install Wordpress CMS with a SQLite flat file database on Android using Alpine Linux in the Userland app good for quick development. Haven't tested it on Alpine for WSL or VM but probably would work. Docker definitely needs docker specific commands.

# Installing quickly with a script.

```
su -
wget https://raw.githubusercontent.com/brettjrea/Scripts_Fix/master/fixscripts.sh
wget https://raw.githubusercontent.com/brettjrea/Android_Userland_Alpine_WP_SQLite/master/setupwp.sh
bash fixscripts.sh && bash setupwp.sh
```

### Install by doing what the script does snip by snip.

`su -`

`apk update && apk upgrade && apk autoremove`

`apk add php7-common php7-iconv php7-json php7-gd php7-curl php7-xml php7-mysqli php7-imap php7-cgi fcgi php7-pdo php7-pdo_mysql php7-soap php7-xmlrpc php7-posix php7-mcrypt php7-gettext php7-ldap php7-ctype php7-dom php-phar php7-sqlite3 php7-pdo_sqlite`

`wget https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar`

`chmod +x wp-cli.phar`
 
`mv wp-cli.phar /usr/local/bin/wp`

`wp cli update`

`wp core download --path=/wp/ --allow-root`

`mv /wp/wp-config-sample.php /wp/wp-config.php`

`cd /wp/wp-content/`

`wget https://raw.githubusercontent.com/brettjrea/wp-sqlite-db/master/src/db.php`

`cd /wp`

`php -S localhost:3000`
