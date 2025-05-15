Project Title: 
    INVENTORY TRACKING

Description of what your project does: 
    Database named InventoryTrackingdb with User Table to store user information. 
    Users can manage their own profiles. 
    Also, the users can use the application according to the roles assigned to them.

How to run/setup the project (or import SQL)
To import the database:
    Go to Administrator TAB
    Under Management
        Select Data Import/Restore
        Select Import from Dump Project Folder and navigate to location where the Database Dump is located
        Select Database Object to Import: Inventorytrackingdb
        Start Import

Screenshot or link to your ERD
    https://github.com/dlulanep/InventorytrackingDB_ERD.git


    -- Question 1:
CREATE database inventorytrackingdb;

USE inventorytrackingdb;

-- This Database tracks equipment allocated to each
CREATE TABLE `inventorytrackingdb`.`user` (
  `id` BIGINT NOT NULL AUTO_INCREMENT,
  `roleId` SMALLINT NOT NULL,
  `firstName` VARCHAR(50) NULL DEFAULT NULL,
  `middleName` VARCHAR(50) NULL DEFAULT NULL,
  `lastName` VARCHAR(50) NULL DEFAULT NULL,
  `username` VARCHAR(50) NULL DEFAULT NULL,
  `mobile` VARCHAR(15) NULL,
  `email` VARCHAR(50) NULL,
  `passwordHash` VARCHAR(32) NOT NULL,
  `registeredAt` DATETIME NOT NULL,
  `lastLogin` DATETIME NULL DEFAULT NULL,
  `intro` TINYTEXT NULL DEFAULT NULL,
  `profile` TEXT NULL DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE INDEX `uq_username` (`username` ASC),
  UNIQUE INDEX `uq_mobile` (`mobile` ASC),
  UNIQUE INDEX `uq_email` (`email` ASC) );--

