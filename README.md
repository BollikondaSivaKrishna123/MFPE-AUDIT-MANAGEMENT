# CDE21IJ026-POD1-AUDIT-MANAGEMENT
MFPE Project

# AUDIT-MANAGEMENT Application

This is a full-stack MFPE project built as part of Cognizant CDE internship.

Following services are part of the application:
## Frontend:
* Audit management Portal


## Backend:
* Authorization Microservice
* Audit Checklist Microservice
* Audit Benchmark Microservice
* Audit Severity Microservice
* Audit Eureka Server
* Audit Zuul Filter
* Audit ConfigServer


## Requirements
* Java 11
* Angular 12

## Setup

Launch the above mentioned 7 microservices in your IDE. Import the project as `Maven Project` and wait for the dependencies to install. If any port is unavailable in your machine you can change the port for the respective microservice in the `application.properties` file under `Backend/microservice/src/main/resources/application.properties`

After the 7 microservices are up and running launch the ClaimApp angular application using `ng serve`

## Usage

### Initial Launch

On initial launch of application the user is prompted with a home page of the application. In the navigation bar user can click the `Login` button for authentication.


### Login Portal

User has to enter his username and password to login. Following credentials can be used to login:

| Username   | Password| 
| -----------|:--------|
| siva       |siva@123 |
| ravi       |ravi@123 |
| anuj       |aunj@123 |
| vishali    |vishali@123|
|sravan      |sravan@123|

## Logged In

Authenticated users can now access the features of the application from the navigation bar under their username.

## Audit checklist
Audit checklist microservice is a middleware microservice.
This microservice is used to get the list of questions from AWS-RDS database.
The returned list is used by the UI to display question based on the type selected by the user.
Method:  
GET:/AuditCheckListQuestions

## Audit Benchmark
Audit Benchmark is a middleware microservice.
This microservice stores the number of acceptable “No” in the database.
Upon request it returns data as a list in a user-defined AuditBenchmark datatype.
It is used to pass the number of  acceptable “No” or the benchmark, in other words, to audit severity microservice.
Method:
GET:/AuditBenchmark

## Audit Severity
Audit Severity is a middleware microservice.
This microservice invokes audit benchmark microservice and takes number of acceptable “No” from it.
It then checks the project execution status according to the pre set rules.
It returns the status and remedial action to be taken.
Method: 
POST:/ProjectExecutionStatus

## Audit Eureka
Audit Eureka is a  microservice.
Used for Microservices Communication.
Supports Load balancing.
All Microservices registered with Eureka Server –Eureka Discovery Client

## Audit Config Server
Audit Config Server is a microservice.
For storing and serving distributed configurations across multiple applications and environments.
This configuration store is ideally versioned under Git version control and can be modified at application runtime.
	->Like Database properties info , Hibernate config files info… configuration 
  
  ## Zuul
  Zuul is a JVM based router and server side load balancer by Netflix.
  Router and Filter

## Session Expiration
The users's session will be valid for `30 minutes` after which the user will be prompted to login again.

## Deployement 
By using EC2 instance, the microservices are launched on AWS cloud.

## Developers

* [Siva Krishna B](https://github.com/Dhileepchinni/CDE21IJ026-POD2-ClaimsManagement)
* [Vishali P](https://github.com/Dhileepchinni/CDE21IJ026-POD2-ClaimsManagement)
* [Sravan B](https://github.com/Dhileepchinni/CDE21IJ026-POD2-ClaimsManagement)
* [Anuj B ](https://github.com/Dhileepchinni/CDE21IJ026-POD2-ClaimsManagement)
* [Ravi Chandra](https://github.com/Dhileepchinni/CDE21IJ026-POD2-ClaimsManagement)
