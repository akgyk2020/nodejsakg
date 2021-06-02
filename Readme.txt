npm install    
 npm install express-flash --save
 npm install express-session --save
 npm install express-validator --save
 npm install method-override --save
 npm install mysql --save

--- make database n table----
CREATE DATABASE IF NOT EXISTS `myapp` DEFAULT CHARACTER SET utf8 COLLATE utf8_general_ci;
USE `nodelogin`;

CREATE TABLE IF NOT EXISTS `users` (
  `id` int(11) NOT NULL,
  `name` varchar(50) NOT NULL,
  `password` varchar(255) NOT NULL,
  `email` varchar(100) NOT NULL
) ENGINE=InnoDB AUTO_INCREMENT=2 DEFAULT CHARSET=utf8;

INSERT INTO `users` (`id`, `name`, `password`, `email`) VALUES (1, 'test', 'test', 'test@test.com');

ALTER TABLE `users` ADD PRIMARY KEY (`id`);
ALTER TABLE `users` MODIFY `id` int(11) NOT NULL AUTO_INCREMENT,AUTO_INCREMENT=2;



Next, you need to create one folder named lib and create a new file name db.js inside lib folder.

Note that, This file is used to connect your node express js app to MySQL db.

lib/db.js
Update the MySQL connection code into your db.js file:

var mysql=require('mysql');
 var connection=mysql.createConnection({
   host:'localhost',
   user:'newpos',
   password:'newpos123',
   database:'myapp'
 });
connection.connect(function(error){
   if(!!error){
     console.log(error);
   }else{
     console.log('Connected!:)');
   }
 });  
module.exports = connection; 



