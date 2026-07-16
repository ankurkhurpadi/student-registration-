# student-registration-
Student Registration Form Project
AWS EC2 + Nginx + PHP + MariaDB Deployment
Project Overview
This project is a Student Registration Form Web Application hosted on an AWS EC2 instance using Amazon Linux. The frontend is developed using HTML, and the backend is developed using PHP. The application uses the Nginx web server and MariaDB database to store student registration data.
Project Architecture
User Browser
     |
     v
NGINX Web Server
     |
     v
PHP Backend
     |
     v
MariaDB Database
Technologies Used
Technology	Purpose
AWS EC2	Cloud Virtual Server
Amazon Linux	Operating System
NGINX	Web Server
MariaDB 10.5	Database
PHP	Backend
HTML	Frontend
VS Code	Code Editor

Project Goal
•	Create a registration form
•	Host it on AWS Cloud
•	Connect frontend with backend
•	Store form data into a database
Project Setup Steps
1. Create AWS EC2 Instance
Launched an EC2 instance using Amazon Linux. Connected to the instance using SSH.
Example Command
ssh -i my-key.pem ec2-user@<Public-IP>
📷  INSERT SCREENSHOT HERE
Screenshot: EC2 instance launch page
(EC2 Instance Creation)
📷  INSERT SCREENSHOT HERE
Screenshot: terminal showing successful SSH connection
(SSH Connection)
2. Install Nginx, MariaDB and PHP
Installed the required packages for web hosting and database connectivity.
Commands Used
sudo yum install nginx -y
sudo yum install mariadb105-server -y
sudo yum install php php-mysqli -y
📷  INSERT SCREENSHOT HERE
Screenshot: terminal output of install commands
(Installation Commands Output)
3. Start and Enable Services
Started and enabled the Nginx and MariaDB services.
Commands Used
sudo systemctl start nginx
sudo systemctl enable nginx
sudo systemctl status nginx
sudo systemctl start mariadb
sudo systemctl enable mariadb
sudo systemctl status mariadb
📷  INSERT SCREENSHOT HERE
Screenshot: systemctl status output for both services
(Start / Enable / Status Commands)
4. Create Frontend Signup Page
Created the frontend registration form using HTML.
📷  INSERT SCREENSHOT HERE
Screenshot: terminal showing signup.html file created (ls output)
(File Created — signup.html)
5. Add Frontend Code
Added HTML form code inside the signup page.
Features of Form:
•	Student Name
•	Email
•	Mobile Number
•	Course
•	Submit Button
📷  INSERT SCREENSHOT HERE
Screenshot: vim/editor showing the HTML form code
(Frontend HTML Code)
6. Configure Database
Connected to MariaDB and created the database and table.
Login to MariaDB
mysql -u root -p
Create Database
CREATE DATABASE studentdb;
USE studentdb;
Create Table
CREATE TABLE students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    mobile VARCHAR(20),
    course VARCHAR(100)
);
📷  INSERT SCREENSHOT HERE
Screenshot: MariaDB console showing database/table creation
(Database and Table Creation)
7. Configure Backend (PHP)
Created the backend PHP file to connect the form with the database.
Backend File: submit.php
Backend Functionality:
•	Receive form data
•	Connect with MariaDB
•	Insert data into database
📷  INSERT SCREENSHOT HERE
Screenshot: terminal opening submit.php in editor
(PHP Backend Configuration)
8. Save Backend Code
Added PHP code inside submit.php.
📷  INSERT SCREENSHOT HERE
Screenshot: full submit.php code in editor
(Backend PHP Code)
9. Install PHP MySQL Connector and Restart Services
Installed the connector for PHP and MariaDB communication.
Commands Used
sudo yum install php-mysqlnd -y
sudo systemctl restart nginx
sudo systemctl restart mariadb
📷  INSERT SCREENSHOT HERE
Screenshot: terminal output of connector install + restart
(Connector Installation and Restart Services)
10. Access Application Using Public IP
Opened the browser and accessed the application using the EC2 public IP.
URL Format: http://<Public-IP>/signup.html
📷  INSERT SCREENSHOT HERE
Screenshot: browser showing the signup form
(Form Opened in Browser)
11. Verify Data Entry in Database
Checked whether the form data was successfully stored in the database.
Commands Used
USE studentdb;
SELECT * FROM students;
📷  INSERT SCREENSHOT HERE
Screenshot: MariaDB SELECT query output
(Database Entry Verification)
Project Outcome
📷  INSERT SCREENSHOT HERE
Screenshot: browser showing successful form submission result
(Form Submission Result)
Successfully created and deployed a Student Registration Form Application on AWS Cloud using Amazon Linux, Nginx, PHP, and MariaDB.
The project demonstrates:
•	Cloud deployment
•	Web server configuration
•	Database management
•	Frontend and backend integration
Future Improvements
•	Add CSS styling
•	Add login authentication
•	Use a custom domain name
•	Enable HTTPS security
•	Deploy using a CI/CD pipeline
