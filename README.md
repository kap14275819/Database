# Database

## Entity Relationship Diagram:
#### An Entity Relationship Diagram (ERD) is a type of flowchart that illustrates how “entities” such as people, objects or concepts relate to each other within a system. ER Diagrams are most often used to design or debug relational databases.ERDs or ER Models use a defined set of symbols such as rectangles, diamonds, ovals and connecting lines to depict the interconnectedness of entities, relationships and their attributes.


![ERD](https://github.com/kap14275819/Database/blob/master/ERD.jpg)

## Data Dictionary:
#### Data dictionaries allow viewers to understand the type of input the database will have, for example some areas in the data dictionary will have "text" next to them whereas other will have "float". This is there so that it can indicate whether there will be some type of text within that area or a numerical value. Data dictionaries are important as they can keep the database consistent from the start by giving it a set point as it allows viewers to look onto a clear view of what the database is going to be like and can always be referred back to when stuck.

#### ![Data Dictionary](https://github.com/kap14275819/Database/blob/master/data%20dictionary.jpg)

#### This data dictionary shows how my database will consist of and what value types it will also have within the database. Using a spreadsheet this will help me in having a layout of that database. This will be helpful in case i mistakenly add an extra value within the database so i can refer back to it to avoid any complications that could occur.

## User Stories
#### As a user I would like to be able to look up my heroes level
#### As a user I would like to be able to look up my enemies level
#### As a user I would like to be able to look up my heroes current health
#### As a user I would like to be able to look up my enemies current health
#### As a user I would like to see how much damage my attacks do
#### As a user I would like to see the range of my different attacks
#### As a user I would like to see how much damage the enemy does
#### As a user I would like to see the name of my enemies
#### As a user I would like to add new enemies using a form
#### As a user I would like to delete data entries using a form
#### As a user I would like to add new heroes using a form
#### As a user I would like to create a report
#### As a user I would like to use SQL code to add new tables to the database

## Test Plan
#### ![testplan](https://github.com/kap14275819/Database/blob/master/images/test%20plan.PNG)
#### This test plan was to test different elements of the database in order to make sure that all elements of the database worked after it was completed.

## Evidence Screenshots
#### Here is a list of screenshots that show the evidence of the database that i created. More can be searched through by clicking onto the database file which can be downloaded.
### Hero Report
#### ![HeroReport](https://github.com/kap14275819/Database/blob/master/images/hero%20report.PNG)
### Enemy Report
#### ![EnemiesReport](https://github.com/kap14275819/Database/blob/master/images/enemy%20report.PNG)
### Hero Table
#### ![HeroTable](https://github.com/kap14275819/Database/blob/master/images/hero%20table.PNG)
### Enemy Table
#### ![EnemiesTable](https://github.com/kap14275819/Database/blob/master/images/enemy%20table.PNG)
### Hero Form
#### ![HeroForm](https://github.com/kap14275819/Database/blob/master/images/hero%20form.PNG)
### Enemy Form
#### ![EnemiesForm](https://github.com/kap14275819/Database/blob/master/images/enemy%20form.PNG)
### Hero Skills
#### ![HeroSkills](https://github.com/kap14275819/Database/blob/master/images/hero%20skill.PNG)
### Enemy Skills
#### ![EnemiesSkills](https://github.com/kap14275819/Database/blob/master/images/enemy%20skill.PNG)
### Skills
#### ![Skills](https://github.com/kap14275819/Database/blob/master/images/skills.PNG)

### Validation
#### ![Validation](https://github.com/kap14275819/Database/blob/master/images/validation1.PNG)
#### ![Validation](https://github.com/kap14275819/Database/blob/master/images/validation2.PNG)
#### Here shows some errors that occur if the user attempts to input an invalid type of data into the form which does not connect with the rest of the database.

## SQL Commands
#### Below are some of the SQL code snippets that I used to create my databse, they come under the following types:

### Insert
#### This command is used to insert values and data into tables.
```html 
INSERT INTO ENEMIES VALUES( 1, 50,'DROID', 150,'30' );
INSERT INTO HEROES VALUES( 2, 20,'CLONE', 150,'50' );
INSERT INTO SKILLS VALUES( 1, 50,'LASER', '150' );
```
### Create

#### This command is used to create new tables with new values.
```html 
CREATE TABLE ENEMIES( ID INT NOT NULL PRIMARY KEY, LEVEL INT NOT NULL, NAME VARCHAR(50) NOT NULL, DAMAGE FLOAT NOT NULL, HP FLOAT NOT NULL );
CREATE TABLE HEROES( ID INT NOT NULL PRIMARY KEY, LEVEL INT NOT NULL, NAME VARCHAR(50) NOT NULL, CLASS VARCJAR(50) NOT NULL, HP FLOAT NOT NULL );
CREATE TABLE SPELLS( ID INT NOT NULL PRIMARY KEY, DAMAGEHEALING INT NOT NULL, NAME VARCHAR(50) NOT NULL, RANGE INT NOT NULL,
);
CREATE TABLE ENEMY_SKILLS( ENEMY_ID INT NOT NULL PRIMARY KEY, SPELL_ID INT NOT NULL PRIMARY KEY, LEVEL INT NOT NULL,
);
CREATE TABLE HERO_SKILLS( HERO_ID INT NOT NULL PRIMARY KEY, SPELL_ID INT NOT NULL PRIMARY KEY, LEVEL INT NOT NULL,
);
```
### Update

#### This command is used to update the value of data within a table without having to create a new table.
```html 
UPDATE HEROES SET LEVEL = 4 WHERE ID = 1;
UPDATE HEROES SET DAMAGE = 12.4 WHERE NAME = CLONE;
UPDATE SKILLS SET RAGE = 4 WHERE ID = 4;
UPDATE SKILLS SET DAMAGEHEALING = 4 WHERE NAME = LASER;
```
### Delete

#### This command is used to delete values from tables, the type of data can be specified.
```html 
DELETE FROM ENEMIES WHERE ID=2 LEVEL > 2 AND NAME='STORM TROOPER';
DELETE FROM ENEMIES WHERE NAME = 'DROID';
DELETE FROM SKILLS WHERE RANGE = 50 ;
```
### Select

#### This command is used to search the database for any data that matches the paramaters you inpud into the command, it will then return any found data that fits these paramaters to you.
```html 
SELECT H.CLASS, H.LEVEL, S.NAME, HS.LEVEL FROM HERO H, SKILLS S, HERO_SKILLS HS WHERE HS.HERO_ID = H.ID AND HS.SKILL_ID = S.ID AND S.NAME LIKE 'Fire%';
SELECT * FROM HERO;
SELECT LEVEL, CLASS FROM HERO WHERE ID = 2;
SELECT MAX(H.LEVEL), MIN(H.LEVEL) FROM HERO H;
SELECT AVG(H.LEVEL) FROM HERO H;
```

## User and Technical Documentation

## 1. System Overview

#### The database systems main purpose is to hold information in the different types of characters that will appear in the game. In the database it will have tables showing the statistics of the Heros and Enemies that will be in the game, there will be also other tables that will relate to the skills that each of those Heros and Enemies will have relating to that character. Some of the values that the character will have within the table such as Name, ID, Health and Damage. These values can be updated in real time for gameplay purposes.

### 1.1 The Role Of Database Systems As…

#### Nowadays database systems can be used for a wide range of things. Below a list will be provided showing the different uses of a database system and what purpose this system serves.

### 1.1a Back-end Systems
#### A Back-end system is a database that allows different users using a third-party application to access it rather than using an application program which is stored within the database itself or by the manipulation of the data.

### 1.1b E-Commerce

#### In E-Commerce, the main purpose of a database is to store information about the customer transactions, customer care, and inventory. This is much easier when programming a dynamic E-commerce website as you are using a database also this allows you to only focus on the design and behaviour of the website while all the interactions are being managed by the system.


### 1.1c Data Mining Applications
#### Data mining is the process of discovering patterns in large sets of data using different methods. This process is essential as it allows intelligent methods that are applied to data mining to then extract these data patterns. Whilst the process is running of the data mining, the database(s) are then searched through so they can then uncover new patterns or sequences in the data.

### 1.2 Tools Used

#### The following tools were used in the design and creation of the database system:

#### -  draw.io 
#### Used to create the Entity Relationship Diagram

#### -  Microsoft Excel
#### Used to create the data dictionary and the test plan documentation

#### -  Microsoft Access
#### Used to create the database system

#### -  Microsoft Word
#### Used to create the user and technical documentation
## 2. System Summary

### 2.1 What Is An Object Oriented Database?

#### An object-oriented database is a system which allows data to be represented in a form of objects similar in design to object oriented programming. These database systems are different from relational databases as they are table-oriented. The object-relational databases are a mic of both approaches.  

#### Object-oriented management systems combine the database capabilities with object oriented programming language capabilities. This type of design can allow object-oriented programmers to create a product, store them as objects, then duplicate and finally edit the existing objects to then have new objects. Since this type of database is connected together with the programming language, the programmer is able to maintain a high level of consistency in both object-oriented management systems and the programming language that will use the same model to represent themselves. Relational database management system projects maintain a clearer division between the database model and the application.

### 2.2 What Is The System For?

#### The system was designed to hold data on the status of different characters and skills within the game, this system will allow the game to be able to hold multiple bits of data in order to complete it's task.

## 3.0 Risks/contingencies

### 3.1 Risks

#### The risks of this database are in the design and development stage, a few possible risks for this database are:
#### - The database not updating reports from forms and having the data stay the same.
#### - The forms having different characters and integers entered within them that they are programmed for.
#### - The tables not updating with each other when new information has been changed.
#### - Having any of the forms not show the information that the tables have

### 3.2 Contingencies

#### The risks can be managed by planning contincies in order to help risks be prevented, some of the contingencies that we used were:
#### - Keeping multiple saves in case a change ruined the database.
#### - Having an ERD so that the database would keep to a specific design.
#### - Keeping code saved in order to inspect it if anything went wrong.
#### - Testing every bit of code after it was executed to make sure it all worked well.

## 4.0	Design Decisions

#### The decision of the design was thought of during the planning phase of the database. The creation of the ERD allowed to plan and figure out what would be a good layout for the database. This also means that tests can be made to make sure that the tables that are connected with each other would work well when running together.
#### When creating the ERD the requirements were looked at for the database and the functionality on it. This included on how it would work, what it would be used for and why is it being made. When looking at these questions this then allowed the creation of the template suite all of the needs that needed to be addressed within the database.

### 4.1 Key Factors Influencing Design

#### The key factors for the design was the functionality of the database, since it was being made for a game to hold data on the characters and their skills, it meant that designing it would have to revolve around that, keeping to this meant that we were able to keep a key design in mind.

### 4.2 Functional Design Decisions

#### Since it is being created for a game, this means that the functionality must server the games needs. For example the database was designed to hold data on the heros, enemies and the skills that they both have, so for this it meant that all parts of needed to be addressed. This database was made to function at a point where it can hold all the data and then you are also able to change it around if you want to update some part of the skills or the other aspects of the heros and enemies.

### 4.3 Database Management System Decisions

#### The database was managed by Microsoft access, this software has all the tools that was needed to design and create the database that was planned, this also included having SQL queries integrated within it. Also this allowed the creation of the design document as well as forms and it also can have real time updating used for the reports. Having these tools allowed us to create a successful website that fulfilled the requirements for the game.

### 4.4 Security and Privacy Design Decisions

#### The database is a private database, this means that the only people that can access it are the people that are on the file that it is created on, this means that only the creator and anyone that they want to share it with have access to the database. This also means that there cannot be any breaches of the data at this point in time.

### 4.5 Performance and Maintenance Design Decisions

#### The database is not as big as it sounds and only has a few requirements, also the scope of the whole project was not majorly huge. This means that the performance of the database extremely quick and the maintenance of the database will not be difficult. The scale of the database did not need to be extended as it does not need to hold huge amount of data within it, this meant that there was no need to have any big decisions on the performance of the database.

## 5.0	Detailed Database Design

#### The database was designed to help out the game. The database has 5 tables within it, only 5 tables were needed as it will cover all the aspects of the databases functionality, this also kept the performance fast and also allowed the maintenance to be only it small amounts. The five tables that were created were Heros, Enemies, Hero_Skills, Enemies_Skills and Skills. These were enough in order to cover all points of the game within the database. The forms of the database make sure that the data that is stored on there is clear and has a place to update the reports more. The reports that are included are made in order for people to view the data currently stored in the tables, this data will update in real time from when the forms are changed.

### 5.1 Data Software Objects and Resultant Data Structures

#### For the forms, we have created buttons that allow the creator to change the data that is stored within the tables, these allow the data to be updated from the forms easily, as well as this there is a delete or remove button that can also be used in order to remove part of the database. The data is structured so that the data can be updated and edited from anywhere other than the reports, this means that the reports are easier to see and collect information from and can be focused on viewing the data rather than editing it.
