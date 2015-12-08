Setup PHP environment with Xampp on Windows.
-------------

### Step 1 - Download Apache

- Go to Apache Friend's [website]('https://www.apachefriends.org/index.html') and download Apache for windows


![](.\\img\\Downloads for Apache Friends.png)

### Step 2 - Install Xampp on windows

- _Select components want to setup_

![](.\\img\\select-component.png)

- _Choose folder want to install xampp_

![](.\\img\\choose-folder.png)

### Step 3 - Configuration root folder

* After installed, you can change directory root folder or use default htdocs in Xampp's folder.

![](.\\img\\root-default.png)

> Change directory root folders

- Go to path:\xampp\apache\conf\httpd.conf and change folder to directory you use.

 ![](.\\img\\change-folder.png)

Change to

```
DocumentRoot "D:/projects"
<Directory "D:/projects">
```

Then restart xampp and run file.php in projects folder to test.

 ![](.\\img\\localhost_test.php.png)

 ### Step 4 - Configuration Virtual Host

 - Go to path:\xampp\apache\conf\extra\httpd-vhosts.conf and insert config.

  ![](.\\img\\change-folder.png)

 Insert to file

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


 ![](.\\img\\virtualconfig.com.png)
