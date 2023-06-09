# Taxi Service

 - The Taxi Service is a training project for the development of Http Servlet and MySQL.
 - Once authenticated, users can perform CRUD operations (create, update and delete)
on manufacturers, cars, and drivers.
 - User can assign drivers to specific vehicles.
 - It is possible to view all vehicles of the current user,
as well as a list of all registered manufacturers, cars and drivers.

## Features

<ul>
<li>Authentication</li>
<li>View all cars, drivers, manufacturers</li>
<li>Create, edit(update) and delete car manufacturer</li>
<li>Create, edit(update) and delete cars</li>
<li>Create, edit(update) and delete drivers</li>
<li>Add drivers to specific cars</li>
<li>View all cars belonging to the current driver</li>
</ul>

## Deployment

This project has been deployed on AWS. You can find it here: http://taxiservice-env.eba-bhumgqze.eu-north-1.elasticbeanstalk.com/

## Getting Started

<ul>
<li>Clone the project repository to your local machine</li>
<li>Run the SQL script located in <code>src/main/resources/init_db.sql</code> to initialize the database</li>
<li>Replace the values of the <code>URL</code>, <code>USERNAME</code>, <code>PASSWORD</code> and <code>JDBC_DRIVER</code> properties 
with the appropriate values for your database setup</li>
<li>Build the project using Maven: <code>mvn clean install</code></li>
<li>Deploy the generated WAR file to servlet container such as Tomcat</li>
</ul>

## Project structure

- Controller:
    - Car controllers:
        - AddDriverToCarController to adding driver to car
        - CreateCarController to create new car
        - DeleteCarController to deleting car
        - EditCarController to updating car
        - GetAllCarsController to getting all cars
    - Driver controllers:
        - CreateDriverController to create new driver
        - DeleteDriverController to deleting driver
        - EditDriverController to updating driver
        - GetAllDriversController to getting all drivers        
        - GetMyCurrentCarsController to getting existed cars for current driver
    - Manufacturer controllers:
        - CreateManufacturerController to create new manufacturer
        - DeleteManufacturerController to deleting manufacturer
        - EditManufacturerController to updating manufacturer
        - GetAllManufacturersController to getting all manufacturers
    - IndexController navigation, used on all pages header 
    - LoginController login(authentication) current driver(user)
    - LogoutController logout current driver(user)
- DAO:
    - CarDaoImpl handler of car model to DB
    - DriverDaoImpl handler of driver model to DB
    - ManufacturerDaoImpl handler of manufacturer model to DB
- Exception:
    - AuthenticationException class for handling checked exceptions during Authentication
        process
    - DataProcessingException class for handling checked exceptions during rest processes    
- Model:
    - Car model class
    - Driver model class
    - Manufacturer model class
- Service:
    - AuthenticationServiceImpl class
    - CarServiceImpl class
    - DriverServiceImpl class
    - ManufacturerServiceImpl class
- Util:
    - ConnectionUtil class for instance connection to DB
    - PasswordHashing clas for create hash password, salt and checked correct password user in DB
- Web/filter:
    - AuthenticationFilter class for handle Authentication process
- resources: 
    - init_db.sql configuration files and database scripts
- webapp:
  - WEB-INF web resources such as CSS and JSP files used as views in the application for
    cars, drivers, manufacturers, authentication and include css files
    (that contains CSS files used in the application)
  - web.xml configuration files web application

## Used technologies:

<ul>
<li>Java <code>16.0.2</code></li>
<li>Maven <code>3.8.1</code></li>
<li>JDBC <code>4.2</code></li>
<li>MySql <code>8.0.32</code></li>
<li>Java Servlets <code>4.0.1</code></li>
<li>JSTL <code>1.2</code></li>
<li>Bootstrap css <code>5.0.2</code></li>
<li>Tomcat <code>9.0.73</code></li>
</ul>

## Authors
[Maksym Horielikov](https://www.linkedin.com/in/maksym-horielikov-738347275/)
