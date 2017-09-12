# Vagrant PHP7 

A simple Vagrant LAMP setup running PHP7.

## What's inside?

- Ubuntu 14.04.3 LTS (Trusty Tahr)
- Vim, Git, Curl, etc.
- Apache
- PHP7 with some extensions
- MySQL 5.6
- Node.js with NPM
- RabbitMQ
- Redis
- Composer
- phpMyAdmin

## How to use

- Clone this repository into your project
- Run ``vagrant up``
- Add the following lines to your hosts file:
```
192.168.100.100 app.dev
192.168.100.100 phpmyadmin.dev
```
- Navigate to ```http://app.dev/``` 
- Navigate to ```http://phpmyadmin.dev/``` (both username and password are 'root')

## For Multidomain configuration
The default Ubuntu document root is /var/www/html. You can make your own virtual hosts under /var/www. This is different to previous releases which provides better security.
- vagrant ssh
- sudo ln -fs /vagrant/<website_folder_name>/ /var/www/<website_folder_name>
- sudo vim /etc/apache2/sites-available/default.conf
- and add new VirtualHost: 
```
<VirtualHost *:80>
  DocumentRoot /var/www/<website_folder_name>
  ServerName <website_folder_name>.dev
</VirtualHost>
```
