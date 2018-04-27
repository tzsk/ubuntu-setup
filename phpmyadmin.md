# PHP My Admin Installation

In this section we will install `PhpMyAdmin` outside the Webroot inside `www` folder.
Process is similar for all Ubuntu Versions.

Run the following commands step by step:

```bash
$ cd /var/www

$ wget https://files.phpmyadmin.net/phpMyAdmin/4.8.0.1/phpMyAdmin-4.8.0.1-english.zip

$ unzip phpMyAdmin-4.8.0.1-english.zip

$ sudo rm phpMyAdmin-4.8.0.1-english.zip

$ sudo mv phpMyAdmin-4.8.0.1-english phpmyadmin
```

We should configure our phpmyadmin:

```bash
$ subl phpmyadmin/libraries/config.default.php
```

It will open the file in `SublimeText`. 

1. Search for: `$cfg['Servers'][$i]['auth_type']`, change its value to `config`.

2. Search for: `$cfg['Servers'][$i]['password']`, change its value to your password: `secret`.

Now, we have to create an alias for phpmyadmin,

To do that Run:

```bash
$ subl /etc/apache2/mods-enabled/alias.conf
```

Now, place this alias there after `icons` alias:

```code
Alias /phpmyadmin "/var/www/phpmyadmin/"

<Directory "/var/www/phpmyadmin/">
    Options Indexes FollowSymLinks
    Order allow,deny
    Allow from all
</Directory>
```

> NOTE: Make sure you indent the file properly. And leave one line gap after the `icons` alias block.

Once that is done it will ask you to put your password to save the change. 
After that, restart the `apache` server: `sudo service apache2 restart` 

Now, visit: [http://localhost/phpmyadmin](http://localhost/phpmyadmin) you should see it's working.