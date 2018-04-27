# php-cs-fixer Installation

In this section we will install `php-cs-fixer` in our system. 
This process is similar for all the ubuntu versions.

```bash
$ wget http://cs.sensiolabs.org/download/php-cs-fixer-v2.phar -O php-cs-fixer

$ sudo chmod a+x php-cs-fixer

$ sudo mv php-cs-fixer /usr/local/bin/php-cs-fixer
```

To verify the installation run:

```bash
$ php-cs-fixer
```

It should show information about `php-cs-fixer` command.