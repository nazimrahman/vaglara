# vaglara
Vagrant setup for vagrant and laravel

1. vagrant up
Note: Ignore the red colored text created by composer. It just signals that you are using sudo.
2. vagrant ssh
3. cd /etc/apache2/sites-available
4. sudo vi laravel.conf
5. Copy/paste the following in this file 
~~~~
<VirtualHost *:80>
    ServerName localhost

    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/html/marketplace/public

    <Directory /var/www/html/marketplace>
        AllowOverride All
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
~~~~
6. sudo a2dissite 000-default.conf
7. sudo a2ensite laravel.conf
8. sudo a2enmod rewrite
9. sudo service apache2 restart
10. Type 192.168.20.20 to test. You should see Laravel.
