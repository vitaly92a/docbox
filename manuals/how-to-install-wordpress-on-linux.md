## How to install Wordpress on Linux

### 1. Install LAMP (Linux Apache MySQL PHP) from the terminal

```bash
sudo apt install lamp-server^ --yes
```

Doing the test:

- on the work of PHP\
  `php -v`

- on the work of MySQL\
  `mysql --version`

- Check that Apache is working by opening a browser and typing in the address bar `localhost`
  or by the local IP address, which will be displayed as a result of running the utility
  `ip addr`

_Note_

To restart LAMP, follow these steps:

Stop Apache

```bash
sudo /etc/init.d/apache2 stop
```

Stop MySQL

```bash
sudo /etc/init.d/mysql stop
```

Start Apache

```bash
sudo /etc/init.d/apache2 start
```

Start MySQL

```bash
sudo /etc/init.d/mysql start
```

### 2. Create database

Type in the terminal and enter the password

```bash
sudo mysql -u root -p
```

Creating a database

```mysql
CREATE database wp_db default character set utf8;
```

Next, we create a user

```mysql
CREATE user 'wp_user'@'localhost' identified by 'password';
```

Finally, we give the user the rights to

```mysql
GRAND ALL ON 'wp_db'@'localhost';
flush privileges;
```

### 3. Install PHP components

```bash
sudo apt install php-curl php-gd php-intl php-mbstring php-soap php-xml php-zip php-xmlrpc php-mysql php-cli -y
```

### 4. Download and install Wordpress

Download the archive

```bash
wget -c https://wordpress.org/latest.tar.gz
```

Extract the archive

```bash
tar -xzvf latest.tar.gz
```

Next, move the unpacked Wordpress to the local server folder.
The local LAMP server is located in /var/www/html.
Copying can be done using the utility `rsync`

```bash
sudo rsync -av wordpress/* /var/www/html
```

Устанавливаем права на папку /var/www/html

```bash
sudo chown -R www-data:www-data /var/www/html
```

```bash
sudo chmod -R 755 /var/www/html
```

Rename the Apache index file.

```bash
sudo mv /var/www/html/index.html /var/www/html/.backup.index.html
```

### 5. Normal sing in Wordpress

---

Thanks for manual: [Станислав Кузнецов](https://youtu.be/-ZFdHA8PZ2E)
