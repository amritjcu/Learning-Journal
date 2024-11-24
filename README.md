
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


#week04

Report: Setting Up a Local Development Environment on Ubuntu 20.04
Introduction
This report details the process of establishing a local development environment on Ubuntu 20.04 using Apache, MySQL, PHP, HTML, CSS, and JavaScript. The objective is to create a dynamic website capable of interacting with a database.
Local Development Environment Setup
    1. Software Requirements:
        ◦ Apache: Web server to serve the site.
        ◦ MySQL: Database management system to handle data storage.
        ◦ PHP: Server-side scripting language for dynamic content.
        ◦ HTML/CSS/JavaScript: Front-end technologies for building the user interface.
    2. Installation Steps:
        ◦ Update Package Manager:
          sudo apt update
        ◦ Install Apache:
          sudo apt install apache2
            ▪ Check if Apache is running:
          sudo systemctl status apache2
        ◦ Install MySQL:
          sudo apt install mysql-server
            ▪ Secure MySQL installation:
          sudo mysql_secure_installation
        ◦ Install PHP and Required Extensions:

          sudo apt install php libapache2-mod-php php-mysql
        ◦ Restart Apache to Load PHP:
          sudo systemctl restart apache2
    3. Database Setup:
        ◦ Access MySQL:
          sudo mysql
        ◦ Create a Database:
          CREATE DATABASE my_dynamic_site;
        ◦ Create Tables:
          USE site_name;
          CREATE TABLE users (
              id INT AUTO_INCREMENT PRIMARY KEY,
              name VARCHAR(100),
              email VARCHAR(100)
          );
    4. Dynamic Site Development:
        ◦ Create Project Directory:
          sudo mkdir /var/www/html/site_name
        ◦ Set Permissions:
          sudo chown -R $USER:$USER /var/www/html/site_name
        ◦ Create PHP Files:
            ▪ db_connect.php:
              php
              Copy code
              <?php
              $host = 'localhost';
              $db_name = 'XXXXXXX';
              $username = 'XXXXXXXXX'; // or your MySQL username
              $password = 'XXXXXXX'; // your MySQL password
              
              try {
                  $pdo = new PDO("mysql:host=$host;dbname=$db_name", $username, $password);
                  $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
                  echo "Connected successfully";
              } catch (PDOException $e) {
                  echo "Connection failed: " . $e->getMessage();
              }
              ?>
            ▪ index.php:
              
              <?php include 'db_connect.php'; ?>
              <!DOCTYPE html>
              <html lang="en">
              <head>
                  <meta charset="UTF-8">
                  <meta name="viewport" content="width=device-width, initial-scale=1.0">
                  <title>My Dynamic Site</title>
                  <link rel="stylesheet" href="style.css">
              </head>
              <body>
                  <h1>Welcome to My Dynamic Site</h1>
              </body>
              </html>
        ◦ Create Style File: Add basic styles in a file named style.css.
    5. Testing the Site:
        ◦ Access the site via http://localhost/site_name/index.php in a web browser.
Demonstration
    • Site Running in Browser: 
    • phpMyAdmin Access: To manage the database easily, consider installing phpMyAdmin:
      sudo apt install phpmyadmin
      Access it via http://localhost/phpmyadmin.
      
Conclusion
The local development environment is now fully operational, allowing for dynamic web development with PHP and MySQL on Ubuntu 20.04. Future enhancements will include integrating JavaScript for interactivity and exploring deployment options to a production server.

#week05

Created the Child Theme Folder:
I created a folder named twenty-twenty-one-child inside the wp-content/themes/ directory.

Customizing style.css:
I added custom CSS for:

Changing the header background color.
Modifying the body font.
Altering the link hover color.
Increasing padding in the main content.
Resizing the site logo.
Customizing the footer background and text.
Enqueued Styles in functions.php:
I wrote a functions.php file to properly enqueue both the parent and child theme stylesheets, ensuring that the child theme's custom styles were applied.

Activating the Child Theme:
After creating the necessary files, I activated the child theme through the WordPress dashboard.

Outcome:
The child theme was successfully created and activated with all customizations applied as intended. The site reflected the changes immediately, and the customizations were preserved even after activating the child theme.

Insight:
Using child themes is a powerful way to maintain customizations safely in WordPress. They allow for modifications without altering the core files of the parent theme, which is crucial for updating the site without losing changes. I now understand how to structure and use child themes effectively in WordPress development.

Conclusion:
This exercise reinforced the importance of using child themes to safely manage customizations in WordPress, ensuring that future updates to the parent theme won't overwrite them.

#week 06

We set up and managed our CMS Team 2 project across four key platforms: GitHub, Trello, LinkedIn, and Slack.

GitHub:
Created a project repository for version control and code collaboration.
Key takeaway: Essential for distributed coding, but required some learning for team members on version control and pull requests.

Trello:
Used Trello to track tasks with columns like Backlog, To-Do, In Progress, and Completed.
Key takeaway: Great for visual task management, but needed regular updates to stay organized.

LinkedIn:
Connected team members professionally and shared project updates.
Key takeaway: While not central to project work, LinkedIn helped strengthen professional ties.

Slack:
Created dedicated channels for team communication, including integration with GitHub and Trello for real-time updates.
Key takeaway: Slack was crucial for quick communication and team collaboration.

In summary, these tools helped streamline collaboration, task management, and communication, but required some initial setup and discipline for effective use.

#week 07

Project Overview:
For this project, I built a simple hike website using PHP, which includes a list of hiking trails that can be displayed and managed through an admin panel. The website dynamically displays the trails using PHP's echo, performs decisions with if/else statements, uses repetition with loops like foreach, and includes reusable elements such as headers and footers using the include() function.

1. Setting Up the PHP Files:
I started by organizing the project into multiple PHP files:

header.php: This contains the common header with navigation links.
footer.php: This contains the footer that is displayed at the bottom of every page.
functions.php: This contains the functions used to manage hiking trails (like fetching the trails and adding new ones).
index.php: The main page, where the hiking trails are displayed.
admin.php: The admin page, where new hiking trails can be added.
This file structure ensures that common parts of the website (like the header and footer) can be reused across pages, reducing duplication of code.

2. Echoing HTML:
The first concept I practiced was echoing HTML using PHP. This was done in multiple places, such as dynamically generating the list of hiking trails.

echo "<ul>";
foreach ($trail_list as $trail) {
    echo "<li>$trail</li>";
}
echo "</ul>";
I used echo to print out HTML tags like <ul> and <li>, along with dynamic content such as trail names. This allowed me to easily add new trails without modifying the structure of the page directly.

3. Using If/Else Statements:
One of the key features I learned was using if/else statements in PHP to make decisions based on conditions. For example, I used an if/else to check if the list of trails was empty and displayed a different message if no trails were available:

if (count($trail_list) > 0) {
    // Display trails
} else {
    echo "<p>No trails available at the moment. Please check back later!</p>";
}
This helped me handle situations where the data might not be available, providing a better user experience.

Additionally, in the admin panel (admin.php), I validated the form input using an if/else statement to ensure that the user cannot submit an empty trail name:

if (!empty($new_trail)) {
    add_trail($new_trail);
} else {
    echo "<p style='color: red;'>Error: Please provide a trail name.</p>";
}
This made the form more robust by ensuring that the user is prompted to enter a valid trail name.

4. Repetition with Loops:
I learned how to use PHP loops to repeat code for each item in an array. For instance, in index.php, I used a foreach loop to display each hiking trail from an array:


foreach ($trail_list as $trail) {
    echo "<li>$trail</li>";
}
This made the code more efficient since I didn't need to manually type out each trail. Instead, the loop iterated through all the elements in the $trail_list array, generating the list dynamically.

5. Using Functions:
I also created custom functions to manage the data more effectively. For example, I created the get_all_trails() function to return the list of trails and the add_trail() function to add a new trail. By defining these functions in the functions.php file, I was able to reuse them across multiple pages.


function get_all_trails() {
    return [
        "Mountain Peak Trail - 10 miles",
        "River Valley Trail - 5 miles",
        "Forest Adventure Trail - 7 miles",
        "Sunset View Trail - 4 miles"
    ];
}

function add_trail($new_trail) {
    echo "<p>New trail added: $new_trail</p>";
}
By separating logic into functions, I made my code modular and easier to maintain.

6. Using Include:
A key takeaway was learning how to include common elements (like the header and footer) across different pages. Instead of repeating the same code for the header and footer in every page, I used the include() function.

For example, both index.php and admin.php include header.php and footer.php:

<?php include('header.php'); ?>
<!-- Page content -->
<?php include('footer.php'); ?>
This kept the code DRY (Don’t Repeat Yourself) and made it easier to update the website's header and footer in one place without having to change every page.

Challenges Faced:
Form Validation: Initially, I was unsure how to validate form input effectively. However, by using if/else statements to check for empty input fields, I was able to prevent invalid submissions.
Error Handling: The most challenging part was handling cases where no trails are available. I needed to ensure that the user receives a meaningful message instead of just an empty list. This was solved with the if/else statement checking the number of trails.
What I Learned:
PHP Basics: This project reinforced the importance of understanding PHP fundamentals, such as using echo, if/else for decision-making, and looping with foreach.
Reusable Code: By using functions and include(), I learned how to make the code more modular and maintainable.
Form Handling: I got a deeper understanding of handling form submissions and validating user input.
Website Structure: This project showed me the importance of organizing files (e.g., separating functions, header, and footer) to build a clean, scalable website.


#week 08 

Hypothesis:
I hypothesize that using modular coding practices (such as breaking code into functions, using include() for headers/footers, and handling form data separately) will help me learn and retain PHP concepts better than writing everything on a single page. This approach could improve my ability to understand and debug my code more efficiently compared to the traditional monolithic coding style.

Test Methodology:
To test my hypothesis, I set up a simple PHP project: a hiking website with a main page to display trails and an admin panel to add new trails. I divided the project into different PHP files:

header.php - Contains the website header.
footer.php - Contains the website footer.
functions.php - Contains PHP functions to manage data, such as fetching trails and adding a new trail.
index.php - Main page to display the hiking trails.
admin.php - Admin panel to add new hiking trails.
I used modular coding by separating concerns:

The header and footer were included on each page using the include() function.
Functions for managing trails were placed in functions.php and reused across the website.
The test was as follows:

I started by coding everything on a single page to understand how I typically learn PHP.
Then, I refactored the same project to use a modular approach by breaking the code into separate files.
Finally, I compared how long it took me to complete the refactor and whether it made the debugging process easier.
Results:
Initial Coding on a Single Page:

The first approach involved writing everything on the same page (i.e., index.php). This made it hard to read and debug.
It was difficult to reuse code, such as the header and footer, leading to redundancy. Every time I needed to update the header, I had to manually update each page.
Debugging took longer because all logic was handled within the same file, making it harder to pinpoint errors.
Modular Approach:

When I refactored the code into smaller, more manageable files (using include() for the header/footer and placing reusable functions in functions.php), I found that the project was much easier to maintain and expand.
It allowed me to focus on specific parts of the code at a time. For example, modifying the list of trails didn't require touching the rest of the page layout.
Debugging became easier as well. If a function had an issue, I could go directly to the functions.php file and fix it. I no longer needed to search through a large chunk of code on a single page.
I also noticed that I was able to understand and remember concepts better because I was breaking tasks into small, manageable parts.
Analysis of Results:
The modular approach significantly improved my learning experience. The primary benefit was that I could isolate specific issues (like a bug in the trail management function) without sifting through the entire page. The separation of concerns allowed me to stay organized and tackle smaller challenges one at a time. This strategy gave me a clearer understanding of PHP’s capabilities for handling larger projects.

Additionally, the use of functions and include() made my project scalable. I could easily add more pages or features (such as adding new trail categories) without modifying the entire structure. The ability to reuse code (like the header/footer) saved time and reduced redundancy, which was a huge advantage.

Learning Insights:
Modular Coding Improves Focus and Debugging: The process of breaking the code into smaller, isolated parts helped me stay focused on each task and debug more efficiently. When everything was in a single file, I found myself overwhelmed, but with modular coding, it was easier to manage.

Reusability Helps Retention: Using reusable components like functions and include() helped me understand PHP's functionality better. I also felt more confident working with external files and organizing code in a more structured way.

Scalability and Maintenance: A modular approach makes a project easier to scale and maintain. As I added more features (like form validation and conditionally displaying data), it was easy to plug in new functionalities without changing the entire codebase.

Clearer Learning Path: By using functions and separating code into different files, I was able to learn new concepts gradually. I wasn’t trying to grasp everything all at once, which made the process less intimidating and more manageable.

Conclusion:
The results of this experiment confirm my hypothesis: modular coding practices, such as breaking code into functions and using include() for reusable components, significantly improve my learning process. It made the code more understandable, manageable, and easier to debug. I now have a clearer understanding of PHP’s capabilities and how to approach larger projects in a scalable and organized manner.

I will continue using this modular approach in future projects to reinforce these concepts and improve my PHP development skills.
