# PHP Installation

In this section, I will explain the ways to install `php7.1` in Ubuntu 14 & 16 and Ubuntu 17.

[update](_update.md ':include')

And also Run:

```bash
$ sudo apt-get install python-software-properties
```

## Ubuntu 14 & 16

For this we have to add seperate `repository` provider to install `php7.1`. Rest of the flow is the same as Ubuntu 17.

Run the following command to add the repository provider:

```bash
$ sudo add-apt-repository ppa:ondrej/php
```

> Now, follow the Ubuntu 17 guide below. You have to `update the repository` again.

## Ubuntu 17

[update](_update.md ':include')

Run this command to install `php7.1`

```bash
$ sudo apt-get install php7.1 libapache2-mod-php7.1 php7.1-cli php7.1-common php7.1-mysql
```

Also install necessary extensions:

```bash
$ sudo apt-get install php7.1-mbstring php7.1-gd php7.1-xml php7.1-mcrypt php7.1-zip
```

After installation is complete please verify the installation:

Run:

```bash
$ php -v
```

It should return something like this:

```bash
PHP 7.1.15-0ubuntu0.17.10.1 (cli) (built: Mar 14 2018 22:30:42) ( NTS )
Copyright (c) 1997-2018 The PHP Group
Zend Engine v3.1.0, Copyright (c) 1998-2018 Zend Technologies
    with Zend OPcache v7.1.15-0ubuntu0.17.10.1, Copyright (c) 1999-2018, by Zend Technologies
```

> NOTE: This only verifies that the PHP is running in your Command Line. To check the web do the following:

First, restart the apache server: `sudo service apache2 restart`

Now run the follwong commands step by step:

```bash
$ touch /var/www/html/info.php

$ subl /var/www/html/info.php
```

It will open the file in SublimeText, place this line inside that file and save: `<?php phpinfo(); ?>`

Now, visit the page from the browser: [http://localhost/info.php](http://localhost/info.php)

If you see the `PHP Information` your php installation is working with apache.