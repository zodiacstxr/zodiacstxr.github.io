## How to install the Apache2 Web Server on Ubuntu [No setting up virtual host]

### Step :1 Installing Apache

First, we can upgrade packages or clean packages using this command.

```ruby
sudo apt update
```

Then install Apache2 Web Server using this command.

```ruby
sudo apt install apache2
```

You may see the question ``` "Do you want to continue? [Y/n]" ``` Type ```y``` and press Enter.

### Step :2 Checking Status

After the installation, check status of the Apache2 using this command.

```ruby
sudo systemctl status apache2
```

Your input should be something like this :

```ruby
● apache2.service - The Apache HTTP Server
   Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: enabled)
   Active: active (running) since Tue 2021-01-10 07:06:17 UTC; 10min ago
    Docs : https://httpd.apache.org/docs/2.4/
 Main PID: 3027 (apache2)
    Tasks: 55 (limit: 1164)
   Memory: 6.0M
   CGroup: /system.slice/apache2.service
           ├─3027 /usr/sbin/apache2 -k start
           ├─3029 /usr/sbin/apache2 -k start
           └─3030 /usr/sbin/apache2 -k start
```

This means our apache2 is running properly. 

Then you can open the web browser and type this command. 

```ruby
http://yourIPaddress
```

<img src="apache.png" width="700" height="1000" />

If this **Apache2 Ubuntu Default Page** appeared, you are doing right.

### Step :3 Editing Original File

We can replace the content in file located at /var/www/html/index.html/

To do that, first we can access into that directory using this command.

```ruby
cd /var/www/html/
```

Then use command ```ls``` to check what all files are in this directory.

```ruby
$ ls

Output

index.html  
```

Before beginning to edit our index.html file, I want to make a copy our apache2 original file in order if anything **goes wrong**. So, go ahead and use this command.

```ruby
sudo cp index.html index_new.html 
```
| NOTE :You can replace ```index_new.html``` with any name you prefer. |

Now, use ```ls``` to the files in this directory, you will see that file ```index_new.html``` was created.

```ruby
$ ls

Output

index.html index_new.html
```

Next, you can go ahead and delete our original file as to replace the code line by line would consume a lot of time.

```ruby
sudo rm index.html
```

Now, when you use command ```ls``` again, you will only see index_new.html file in /var/www/html/ directory.

```ruby
$ ls

Output 

index_new.html 
```

Go ahead and create index.html using this command.

```ruby
sudo nano index.html 
```
| NOTE : With ```nano``` command, we can directly **create** and **edit** a new file. |

After editting the file, you can save it by press ```Ctl+O```. It will ask whether you want to save the code in index.html. Press ```Enter```, follow by ```Ctl+X``` to exit.

You can check if the code is saved by using this command ```cat``` to see what the file contains.

```ruby
$ cat index.html

Output

<html>
	<body> 
	<h1> My name is Punthita. </h1>
		<h2> I am a Computer Engieering Student.</h2>
	</body>

</html>
```

That's it!!! Now open your web browser and type down your IP address. ```
http://3.XX.XX.XX   
```

|**My name is Punthita.**

**I am a Computer Engineering Student.**|

 
<!-- blank line -->
----
<!-- blank line -->

Compose by :

Zodiacstxr

E-mail: Punthita298@gmail.com

<a href="https://www.instagram.com/tk_ccb/">Click here for Instagram</a>
 
<a href="https://www.facebook.com/profile.php?id=100014594763804">Click here for Facebook</a>