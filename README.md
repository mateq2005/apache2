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
    ServerAdmin webmaster@localhost
    ServerName your_domain
    ServerAlias www.your_domain
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
sudo a2ensite your_domain.conf
sudo a2dissite 000-default.conf
```

```
sudo systemctl restart apache2
```

**http://your_server_ip**

### Step 4 – Getting Familiar with Important Apache Files and Directories

| <ins>Content</ins>      
| ------------- 
| /var/www/html

| <ins>Server Configuration</ins>
| -------------
| /etc/apache2 
| /etc/apache2/apache2.conf
| /etc/apache2/ports.conf
| /etc/apache2/sites-available/
| /etc/apache2/sites-enabled/

| <ins>Server Logs</ins>
| -------------
| /var/log/apache2/access.log
| /var/log/apache2/error.log

OK
