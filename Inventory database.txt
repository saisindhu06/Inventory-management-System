CREATE DATABASE `inventory` ;
USE `inventory`;

CREATE TABLE `currentstock` (
  `productcode` varchar(45),
  `quantity` int,
  PRIMARY KEY (`productcode`)
) ;

INSERT INTO `currentstock` VALUES ('prod1',146),('prod2',100),('prod3',202),('prod4',172),('prod5',500),('prod6',500),('prod7',10),('prod8',20);

CREATE TABLE `customers` (
  `cid` int NOT NULL AUTO_INCREMENT,
  `customercode` varchar(45),
  `fullname` varchar(45),
  `location` varchar(45),
  `phone` varchar(45),
  PRIMARY KEY (`cid`)
);

INSERT INTO `customers` VALUES (301,'vip1','John Seed','New York','9818562354'),(302,'vip2','Jacob Seed','Texas','9650245489'),(303,'std1','Ajay Kumar','Mumbai','9236215622'),(304,'std2','Astha Walia','Chandigarh','8854612478'),(306,'vip3','Madhu Chitkara','Chandigarh','9826546182');

CREATE TABLE `products` (
  `pid` int NOT NULL AUTO_INCREMENT,
  `productcode` varchar(45),
  `productname` varchar(45),
  `costprice` double,
  `sellprice` double,
  `brand` varchar(45),
  PRIMARY KEY (`pid`),
  UNIQUE KEY `productcode_UNIQUE` (`productcode`)
);

INSERT INTO `products` VALUES (111,'prod1','Laptop',85000,90000,'Dell'),(112,'prod2','Laptop',70000,72000,'HP'),(113,'prod3','Mobile',60000,64000,'Apple'),(114,'prod4','Mobile',50000,51000,'Samsung'),(121,'prod5','Charger',2000,2100,'Apple'),(122,'prod6','Mouse',1700,1900,'Dell'),(128,'prod7','Power Adapter',3000,3500,'Dell'),(129,'prod8','Smart Watch',15000,17000,'Apple');

CREATE TABLE `purchaseinfo` (
  `purchaseID` int NOT NULL AUTO_INCREMENT,
  `suppliercode` varchar(45),
  `productcode` varchar(45),
  `date` varchar(45),
  `quantity` int,
  `totalcost` double,
  PRIMARY KEY (`purchaseID`)
) ;

INSERT INTO `purchaseinfo` VALUES (1001,'sup1','prod1','Wed Jan 14 00:15:19 IST 2021',10,850000),(1002,'sup1','prod6','Wed Jan 14 00:15:19 IST 2021',20,34000),(1003,'sup2','prod3','Wed Jan 14 00:15:19 IST 2021',5,300000),(1004,'sup2','prod5','Wed Jan 14 00:15:19 IST 2021',5,10000),(1005,'sup3','prod2','Wed Jan 14 00:15:19 IST 2021',2,140000),(1006,'sup4','prod4','Wed Jan 14 00:15:19 IST 2021',2,100000),(1009,'sup2','prod3','Wed Sep 01 04:11:13 IST 2021',2,120000),(1010,'sup1','prod7','Wed Sep 01 04:25:06 IST 2021',10,30000),(1011,'sup2','prod8','Fri Sep 03 00:00:00 IST 2021',20,300000);

CREATE TABLE `users` (
  `id` int NOT NULL AUTO_INCREMENT,
  `name` varchar(45),
  `location` varchar(45),
  `phone` varchar(10),
  `username` varchar(20),
  `password` varchar(200),
  `usertype` varchar(45),
  PRIMARY KEY (`id`)
) ;

INSERT INTO `users` VALUES (20,'Admin','Local','9876543210','root','root','ADMINISTRATOR');