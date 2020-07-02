# DVWA
How to intall dvwa in linux

Step 1. Download DVWA
Go to the apache2 folder.
cd /var/www/html/
sudo git clone https://github.com/ethicalhack3r/DVWA.git

Change permissions for DVWA
sudo chmod -R 777 DVWA/
cd DVWA/config/
cp config.inc.php.dist config.inc.php
sudo nano /var/www/html/DVWA/config/config.inc.php

Step 2. Install MySQL
The next component for Setting up DVWA is Installing MySQL.
To install MySQL, type the following:
sudo apt-get install mariadb-server
sudo service mysql start
sudo mysql -u root

To create a database, type the following command:
CREATE DATABASE dvwadbs;
SHOW DATABASES;
To create a database user, type the following command
CREATE USER 'dvwauser'@localhost IDENTIFIED BY 'dvwa@123';
SELECT User FROM mysql.user;
GRANT ALL PRIVILEGES ON dvwadbs.* TO 'dvwauser'@localhost IDENTIFIED BY 'dvwa@123';
to remove user 
DROP USER 'user1'@localhost;

Once done, exit the application by typing either of the following commands:
exit

sudo service apache2 start

Step 3. Install PHP5
To install PHP, simply type the following command:
sudo apt install php
sudo service apache2 restart

test the PHP software that you just installed.
cd /var/www/html
sudo gedit info.php
Inside this file, copy paste the following:
<?php phpinfo(); ?>
Save your changes by entering:
:wq!

You can remove this file if you want by typing the following command:
sudo rm /var/www/html/info.php

sudo gedit /etc/php/7.3/apache2/php.ini
Enable Allow_url_fopen
Enable Allow_url_include

to install gedit
sudo apt install gedit
