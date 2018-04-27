# Apache Installation

In this section we will install `apache2` in our system. This process is similar for all the ubuntu versions.

[update](_update.md ':include')

Run the following command to install apache:

```bash
$ sudo apt-get install apache2
```

After installation is complete please verify the installation:

Run:

```bash
$ apache2 -v
```

It should return something like this:
```bash
Server version: Apache/2.4.27 (Ubuntu)
Server built:   2018-04-18T14:20:05
```

It will also give you additiona commands to `start`, `stop` & `restart` your apache server anytime you want:

```bash
$ sudo service apache2 start
$ sudo service apache2 stop
$ sudo service apache2 restart
```

Then, in your terminal go to `cd /var` folder. Then run:

```bash
$ sudo chmod -R 777 www
```

This will give write permission to the `WebRoot` folder. Remember Webroot is: `/var/www/html`

Now in your browser visit: [http://localhost](http://localhost) and you should see it's working.

> NOTE: By default `mod_rewrite` is not enabled. To properly set it up follow the below steps.

Enable Module & Open apache site config file:

```bash
$ sudo a2enmod rewrite

$ subl /etc/apache2/sites-enabled/000-default.conf
```

It will open the file in `SublimeText`, now just after the `DocumentRoot /var/www/html` line place this block:

```bash
<Directory /var/www/html>
    Options Indexes FollowSymLinks MultiViews
    AllowOverride All
    Order allow,deny
    allow from all
</Directory>
```

> NOTE: Make sure your indent the file properly. And leave one line gap after `DocumentRoot /var/www/html`