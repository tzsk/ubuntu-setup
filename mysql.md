# MySQL Installation

In this section we will install `mysql` (MariaDB) in our system. 
This process is similar for all the ubuntu versions.

[update](_update.md ':include')

Run the following command to install mariadb:

```bash
$ sudo apt-get install mariadb-server
```

This will ask you for your root password. I strongly recommend we all keep `secret` as the password for our company internally for consistency. Then, confirm the password and it will move forward with the installation.

After installation is complete please verify the installation:

Run:

```bash
$ mysql --version
```

It should return something like this:
```bash
mysql  Ver 14.14 Distrib 5.7.21, for Linux (x86_64) using  EditLine wrapper
```

It will also give you additiona commands to `start`, `stop` & `restart` your mysql server anytime you want:

```bash
$ sudo service mysql start
$ sudo service mysql stop
$ sudo service mysql restart
```

