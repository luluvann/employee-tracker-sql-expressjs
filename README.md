# Employee Tracker

## Description 
An app to view and interact with the employees SQL database from the command line

## Table of Contents

* [Walkthrough Video](#walkthrough-video)
* [Installation](#installation)
* [Usage](#usage)
* [Technologies](#technologies)
* [User Story and Acceptance criteria](#User-Story-and-Acceptance-criteria)

## Walktrough video
[https://drive.google.com/file/d/1V-pXa0SWoqB86whcCL1nWDliNWBY-MS3/view](https://drive.google.com/file/d/1V-pXa0SWoqB86whcCL1nWDliNWBY-MS3/view)

Timeline :
- 0'00 : ***Start the app***
- 0'06 : ***View all departments***
- 0'14 : ***View all roles***
- 0'21 : ***View all employees***
- 0'30 : ***Add a new department*** (Customer Service)
- 0'40 : Check that the new department has been added to db (View all departments)
- 0'50 : ***Add a new role*** (Customer Service Rep)
- 1'14 : Check that the new role has been added to the db (View all roles)
- 1'24 : ***Add a new employee*** (Kelly Kapoor as a Customer Service Rep and reporting to Michael Scott)
- 1'47 : Check that the new employee has been added to the db (View all employees)
- 2'02 : ***Update role of an existing employee*** (Dwight Schrute with the new role of Branch Manager)
- 2'15 : Check that the new role has been changed for that employee (View all employees)
- 2'24 : ***Exit the app***




## Installation
1. Clone the repo 
    ```
    git clone git@github.com:luluvann/employee-tracker-sql.git
    ```
2. Install all the depedencies by running the command
    ```
    npm install
    ``` 
3. Make sure to have [MySQL](https://dev.mysql.com/downloads/mysql/) installed on your machine

4. Create a .env file at the root of the project and write the following in the .env file:
    ```
    MYSQL_PASS=replaceWithYourMySQLpassword
    ```
5. Start the MySQL Shell by entering the following command at the root directory of the project
    ```
    mysql -u root -p
    ```
6. Run the following commands in the MySQL shell to initiate the database (there is dummy data there already)
    ```
    source db/db.sql
    ```
    ```
    USE team;
    ```
    ```
    source db/schema.sql;
    ```
    ```
    source db/seeds.sql;
    ```

## Usage 
1. Open the git bash terminal at the root of the project 
2. To start the app, run the following commande
    ```
    node index.js
    ``` 
3. Follow the prompt instructions and interact with the app!

## Technologies
- [Inquirer](https://www.npmjs.com/package/inquirer) to prompt the user
- [MySQL2](https://www.npmjs.com/package/mysql2) to interact with MySQL local database
- [console.table](https://www.npmjs.com/package/console.table) to display SQL queries results in formatted tables

## User Story and Acceptance criteria
```
AS A business owner

I WANT to be able to view and manage the departments, roles, and employees in my company
SO THAT I can organize and plan my business

GIVEN a command-line application that accepts user input
WHEN I start the application
THEN I am presented with the following options: view all departments, view all roles, view all employees, add a department, add a role, add an employee, and update an employee role

WHEN I choose to view all departments
THEN I am presented with a formatted table showing department names and department ids

WHEN I choose to view all roles
THEN I am presented with the job title, role id, the department that role belongs to, and the salary for that role

WHEN I choose to view all employees
THEN I am presented with a formatted table showing employee data, including employee ids, first names, last names, job titles, departments, salaries, and managers that the employees report to

WHEN I choose to add a department
THEN I am prompted to enter the name of the department and that department is added to the database

WHEN I choose to add a role
THEN I am prompted to enter the name, salary, and department for the role and that role is added to the database

WHEN I choose to add an employee
THEN I am prompted to enter the employee’s first name, last name, role, and manager and that employee is added to the database

WHEN I choose to update an employee role
THEN I am prompted to select an employee to update and their new role and this information is updated in the database 
```