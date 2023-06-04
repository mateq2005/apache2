# Apache2

### Step 1 — Installing Apache

```
sudo apt update
sudo apt install apache2
```

### Step 2 — Adjusting the Firewall

```
sudo ufw app list
sudo ufw allow 'Apache'
sudo ufw status
```

### Step 3 — Checking your Web Server

```
sudo systemctl status apache2
hostname -I
```

**http://your_server_ip**

### Step 4 — Managing the Apache Process

```
sudo systemctl stop apache2
sudo systemctl start apache2
sudo systemctl restart apache2
sudo systemctl reload apache2
sudo systemctl disable apache2
sudo systemctl enable apache2
```

### Step 5 — Setting Up Virtual Hosts

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
sudo a2ensite your_domain.conf
sudo a2dissite 000-default.conf
```

```
sudo systemctl restart apache2
```

**http://your_server_ip**

### Step 6 – Getting Familiar with Important Apache Files and Directories



**Server Logs**
/var/log/apache2/access.log
/var/log/apache2/error.log

| Content       | 
| ------------- | 
| /var/www/html | 

| Server Configuration | 
| ------------- | 
| /etc/apache2
| /etc/apache2/apache2.conf
| /etc/apache2/ports.conf
| /etc/apache2/sites-available/
| /etc/apache2/sites-enabled/

| First Header  | 
| ------------- | 
| Content Cell  | 
| Content Cell  | 



