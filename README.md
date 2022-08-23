# slalab3-asssign-1-1st-question
 
 In this assignm,ent it has been asked to create a website in MYSQL and PhPusing LAMP stack 
 for this we require a apache server ,so i installed that using this commands
 
sudo apt update
sudo apt install apache2
after installing we have to allow trsffic to the firewall so i did that using this commands
sudo ufw allow in "Apache Full"

# installation of mysql
after installtion of aopache we have to install the mysql server
for that i used the below commands
sudo apt install mysql-server
sudo mysql_secure_installation 
after succesfully installing we have to validate it with password.

Now our mysql is also ready 
 # installation of PhP
 PhP will run under apache and it talks with mysql server.
 for installing  i used the command
 sudo apt install php libapache2-mod-php php-mysql
 then we have to tell webserver to refer php files over others with the help of the command
 sudo nano /etc/apache2/mods-enabled/dir.conf
 and writing index.php ahead of all in the above nano file.
 
 # Now we have to setup virtual host in apache
 
 for that we use the following commands
 
 sudo mkdir /var/www/your_domain
sudo chown -R $USER:$USER /var/www/your_domain
sudo chmod -R 755 /var/www/your_domain
sudo nano /var/www/your_domain/index.html

here your domain name will be anything that you want to name
and in the index.html file you ca add your html code.
 now for apache to serve well we are modifying the .conf file with correect names.
 Now use this commands 
 sudo a2ensite your_domain.conf
sudo a2dissite 000-default.conf
sudo apache2ctl configtest  
sudo systemctl restart apache2

after executing the last command the system restarts and you can see the apache serving our domain.


Now for creating a website in php and mysql we have to create a database and domain.
You can see that creation of domain already done

Now we have to create a data base
for that we have to open the mysql 
using 
sudo mysql -u domain -p
command 

then we have to use the command.
 mysql> CREATE DATABASE example_database;
 Now the database will be created.
 after that we have to grant all permissions to that databaseusing the command.
 mysql> GRANT ALL ON example_database.* TO 'example_user'@'%';
 Now we can give data into database using command
 here i created a table so i used 
 CREATE TABLE example_database.todo_list (
	item_id INT AUTO_INCREMENT,
	content VARCHAR(255),
	PRIMARY KEY(item_id)
);
and by using this command 
INSERT INTO example_database.todo_list (content) VALUES ("My first important item");
we can insert data into the database in the table format.
here after we can see the data in the website by http://ip or your_domain/todo_list.php
Now for making the website which is interactive i have created some php files in my domain 
and connected each of them with each other for succesfull executioon.
Here connection means we connect our databases to the PHP page .


 
