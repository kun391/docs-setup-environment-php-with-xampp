Setup PHP environment with Xampp on Windows.
-------------

### Step 1 - Download Apache

- Go to Apache Friend's [website](https://www.apachefriends.org) and download Apache for windows

![](https://github.com/kun391/setup-environment-php-docs-with-xampp/blob/master/img/Downloads%20for%20Apache%20Friends.png?raw=true)

### Step 2 - Install Xampp on windows

- _Select components want to setup_

![](https://github.com/kun391/setup-environment-php-docs-with-xampp/blob/master/img/select-component.png?raw=true)

- _Choose folder want to install xampp_

![](https://github.com/kun391/setup-environment-php-docs-with-xampp/blob/master/img/choose-folder.png?raw=true)

### Step 3 - Configuration root folder

* After installed, you can change directory root folder or use default htdocs in Xampp's folder.

![](https://github.com/kun391/setup-environment-php-docs-with-xampp/blob/master/img/root-default.png?raw=true)

> Change directory root folders

- Go to path:\xampp\apache\conf\httpd.conf and change folder to directory you use.

 ![](https://github.com/kun391/setup-environment-php-docs-with-xampp/blob/master/img/change-folder.png?raw=true)

Change to

```
DocumentRoot "D:/projects"
<Directory "D:/projects">
```

Then restart xampp and run file.php in projects folder to test.

 ![](https://github.com/kun391/setup-environment-php-docs-with-xampp/blob/master/img/localhost_test.php.png?raw=true)

 ### Step 4 - Configuration Virtual Host

 - Go to path:\xampp\apache\conf\extra\httpd-vhosts.conf and insert config.

 ```
<VirtualHost *:80>
DocumentRoot D:/projects/theright
<Directory D:/projects/theright>
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
        Order allow,deny
        allow from all
</Directory>
ServerName virtualconfig.com
</VirtualHost>
 ```
 > **Note:** You can learn more config on [Apache Docs](https://httpd.apache.org/docs/2.2/en/vhosts/)

Add server name
```
127.0.0.1 virtualconfig.com
```
to file hosts on windwows:
> *C:\Windows\System32\drivers\etc*

Then restart xampp and run to view result.


 ![](https://github.com/kun391/setup-environment-php-docs-with-xampp/blob/master/img/virtualconfig.com.png?raw=true)
