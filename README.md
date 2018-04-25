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
