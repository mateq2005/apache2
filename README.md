# Apache2

### Installing Apache

```
sudo apt-get update
sudo apt-get install apache2 -y
```

```
systemctl start apache2 
systemctl enable apache2 
systemctl status apache2 
```

### Setting Up Virtual Hosts

**Default page:** /var/www/html

```
sudo mkdir /var/www/your_domain
sudo chown -R $USER:$USER /var/www/your_domain
sudo chmod -R 755 /var/www/your_domain
sudo nano /var/www/your_domain/index.html
```

**Default configuration:** /etc/apache2/sites-available/000-default.conf

```
sudo nano /etc/apache2/sites-available/your_domain.conf
```

```
<VirtualHost *:80>
    ServerName your_domain
    ServerAlias www.your_domain
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/your_domain
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

```
nano /etc/apache2/ports.conf
```

```
Listen 80
```

```
/etc/apache2/envvars
```

```
export APACHE_RUN_USER=www-data
export APACHE_RUN_GROUP=www-data
```

### Enabling website
```
sudo a2ensite your_domain.conf
sudo a2dissite 000-default.conf
```

```
sudo systemctl restart apache2
```

**http://your_server_ip**
