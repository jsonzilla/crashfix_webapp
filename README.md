# Crashfix WebApp

### Installing Apache HTTP Server and PHP 5 (Debian/Ubuntu)

From a command shell, you will run the following commands:
```bash
sudo apt-get install apache2
sudo apt-get install php5
sudo apt-get install libapache2-mod-php5 php5-gd
sudo apt-get install php5-sqlite
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
sudo apt-get install php-pear`
```

### Installing PHPUnit:
```bash
sudo apt-get install phpunit
```

### Installing Selenium extension:
```bash
sudo pear channel-update pear.phpunit.de
sudo apt-get install php5-curl
sudo pear install phpunit/PHPUnit_Selenium-1.2.5
```

### Installing Phing:
```bash
sudo pear channel-discover pear.phing.info
sudo pear install phing/phing
```

## Running Unit Tests
Goto protected/tests directory and type in command line:
```
phpunit --stderr unit
```

This will run all unit tests in unit subfolder. The --stderr key
should be used to avoid sending headers befor session is created.

To avoid Code Coverage low memory PHP error, increase memory limit
in php.ini from 128M to 256M and restart Apache.