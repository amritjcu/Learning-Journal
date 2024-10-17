
#Learning Activities & Resources

This week I set up a website template based on HTML, CSS, and JavaScript and studied some of the LinkedIn Learning courses and some other online tutorials. I get much help from Bootstrap and W3Schools. https://www.w3schools.com/ https://getbootstrap.com/

#Estimated Hours

I spent about 5 hours doing this week's practical, learning and doing it.

Content Insights

I re-learned that HTML is responsible for structuring the content of a website, such as organizing text, images, and links, while CSS is used to control the visual design and layout, including colours, fonts, and spacing. This separation of form (CSS) and function (HTML) is important because it makes websites easier to maintain and update. It also ensures the design can be adapted for different devices, like desktops, tablets, and smartphones, without affecting the core content structure.

Career/Employ-ability/Learning Insights

I realized that watching too many tutorial videos at once made me lose focus. Instead, breaking them into shorter sessions followed by hands-on practice kept me more engaged and helped me retain what I learned without needing to repeat the videos. This way, I could immediately apply the new skills, reinforcing my understanding. Web developers and designers widely use Bootstrap to make or customize websites without altering the entire template. I understand that using Bootstrap makes styling more efficient and allows changes without worrying about them being overwritten. However, since it focuses on front-end development, I’m not sure if I’ll rely on it much in the future, as it’s not the main area I’m aiming to pursue for my career. It was interesting to explore how front-end developers use tools like Bootstrap and W3Schools, but whether I continue using them depends on where my career path leads.

#week02

Learning Journal: Installing WordPress on Ubuntu
Objective:
Set up a WordPress website on an Ubuntu server using the LAMP stack (Linux, Apache, MySQL, PHP).

Steps:

System Update:
Updated Ubuntu system using:

bash
Copy code
sudo apt update && sudo apt upgrade
LAMP Stack Installation:

Apache: Installed and started Apache web server.
MySQL: Installed MySQL and created a database and user for WordPress.
PHP: Installed PHP along with necessary extensions for WordPress.
Database Setup: Created a MySQL database and user:

sql
CREATE DATABASE wordpress_db;

CREATE USER 'wordpress_user'@'localhost' IDENTIFIED BY 'strong_password';

GRANT ALL PRIVILEGES ON wordpress_db.* TO 'wordpress_user'@'localhost';

FLUSH PRIVILEGES;

WordPress Installation: Downloaded and extracted WordPress into /var/www/html. Set proper file permissions.

Apache Configuration:
Created a virtual host file for WordPress, enabled mod_rewrite, and restarted Apache.

WordPress Configuration:
Edited wp-config.php to include database credentials.

Final Setup:
Accessed the web interface at http://your-server-ip to complete WordPress installation.

Reflection: This process involved understanding server configuration, database management, and file permissions. A successful WordPress setup requires careful attention to system security and LAMP configuration.

#week03

Learning Journal: Installing Joomla on Ubuntu
Objective:

Set up a Joomla website on an Ubuntu server using the LAMP stack (Linux, Apache, MySQL, PHP).

Steps:

System Update:

Updated Ubuntu system using:

bash
sudo apt update && sudo apt upgrade

LAMP Stack Installation:

Apache: Installed and started Apache web server.

MySQL: Installed MySQL, created a database, and user for Joomla.

PHP: Installed PHP and necessary extensions for Joomla.

Database Setup: Created a MySQL database and user:

sql
CREATE DATABASE joomla_db;

CREATE USER 'joomla_user'@'localhost' IDENTIFIED BY 'strong_password';

GRANT ALL PRIVILEGES ON joomla_db.* TO 'joomla_user'@'localhost';

FLUSH PRIVILEGES;

Joomla Installation: Downloaded and extracted Joomla into /var/www/html:

bash

sudo wget https://downloads.joomla.org/latest -O joomla.zip

sudo unzip joomla.zip -d /var/www/html

sudo chown -R www-data:www-data /var/www/html

sudo chmod -R 755 /var/www/html

Apache Configuration:

Created a virtual host file for Joomla and enabled mod_rewrite for URL rewriting. Restarted Apache:

bash

sudo nano /etc/apache2/sites-available/joomla.conf

sudo a2ensite joomla.conf

sudo a2enmod rewrite

sudo systemctl restart apache2

Joomla Configuration: Accessed the web interface at (https://amrit-joomla.zionauto.sg/shebatha/) and followed the steps to configure Joomla, including database setup and admin account creation.

Reflection: This process was similar to WordPress, with additional steps for managing Joomla’s specific file structure. The configuration required attention to Apache settings and security aspects like database permissions.


#week 03
Learning Journal: Installing WordPress on Ubuntu
Objective:
Set up a WordPress website on an Ubuntu server using the LAMP stack (Linux, Apache, MySQL, PHP).

Steps:

System Update:

Updated Ubuntu system using:

bash
sudo apt update && sudo apt upgrade
LAMP Stack Installation:

Apache: Installed and started Apache web server.

MySQL: Installed MySQL and created a database and user for WordPress.

PHP: Installed PHP along with necessary extensions for WordPress.

Database Setup: Created a MySQL database and user:

sql
CREATE DATABASE wordpress_db;

CREATE USER 'wordpress_user'@'localhost' IDENTIFIED BY 'password';

GRANT ALL PRIVILEGES ON wordpress_db.* TO 'wordpress_user'@'localhost';

FLUSH PRIVILEGES;

WordPress Installation: Downloaded and extracted WordPress into /var/www/html. Set proper file permissions.

Apache Configuration:

Created a virtual host file for WordPress, enabled mod_rewrite, and restarted Apache.

WordPress Configuration:

Edited wp-config.php to include database credentials.

Final Setup:

Accessed the web interface at (https://amrit.zionauto.sg/) to complete WordPress installation.

Reflection: This process involved understanding server configuration, database management, and file permissions.WordPress setup requires careful attention to system security and LAMP configuration.
