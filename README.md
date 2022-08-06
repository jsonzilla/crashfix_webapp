# Crashfix WebApp

[![Maintainability](https://api.codeclimate.com/v1/badges/ccde55326c7afd78fb10/maintainability)](https://codeclimate.com/github/jsonzilla/crashfix_webapp/maintainability)
[![Test Coverage](https://api.codeclimate.com/v1/badges/ccde55326c7afd78fb10/test_coverage)](https://codeclimate.com/github/jsonzilla/crashfix_webapp/test_coverage)

This is a service that runs the Crashfix server and provides a webapp tha interacts with the [Crashfix Daemon](https://github.com/jsonzilla/crashfix_webapp).

### Installing Apache HTTP Server and PHP 5 (Debian/Ubuntu)

From a command shell, you will run the following commands:
```bash
sudo apt-get install apache2
sudo apt-get install php
sudo apt-get install libapache2-mod-php php-gd
sudo apt-get install php-sqlite3
sudo service apache2 restart
```

Note that if apache is already installed you can omit the first line.
Your web files will now be found in /var/www/http

### Installing sendmail:

```bash
sudo apt-get install sendmail
```

### Installing Pear:
```bash
sudo apt-get install php-pear
```

### Installing PHPUnit:
```bash
sudo apt-get install phpunit
```

### Installing Composer:
```bash
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
# optional php -r "if (hash_file('sha384', 'composer-setup.php') === '55ce33d7678c5a611085589f1f3ddf8b3c52d662cd01d4ba75c0ee0459970c2200a51f492d557530c71c15d8dba01eae') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
```

### Installing Selenium extension:
```bash
sudo apt-get install php-curl
php composer.phar require --dev phpunit/phpunit
php composer.phar require --dev phpunit/phpunit-selenium=1.2.9
```

### Installing Phing:
```bash
php composer.phar require --dev phing/phing
```

## Running Unit Tests
Goto protected/tests directory and type in command line:
```
cd protected/tests
phpunit --stderr unit
```

This will run all unit tests in unit subfolder. The --stderr key
should be used to avoid sending headers befor session is created.

To avoid Code Coverage low memory PHP error, increase memory limit
in php.ini from 128M to 256M and restart Apache.
