# SublimeText 3 Installation

In this section we will install `SublimeText3` in our system. 
This process is similar for all the ubuntu versions.
This will give us the `subl` command to open files and folders.

[update](_update.md ':include')

Run the following commands step by step to install:

```bash
$ wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -

$ echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```

[update](_update.md ':include')

Now run this:

```bash
$ sudo apt-get install sublime-text
```

You are done.