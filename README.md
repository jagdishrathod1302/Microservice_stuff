# Microservice_stuff

#Eureka Server :-
How to Register Eureka Server :

Step 1 : First Add Following Dependencies 
1.	Spring Web 
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-web</artifactId>
</dependency>

2.	Eureka Server 
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-netflix-eureka-server</artifactId>
</dependency>

Step 2 : Step 2 : Add Annotation @EnableEurekaServer 
@EnableEurekaServer : this annotation in Spring Cloud Netflix Eureka that is used to turn a spring boot application into a Eureka Server, which acts as a service registry in a microservices architecture.
And you place this annotation on the main application class of a Spring Boot application to make it a Eureka Server

Step 3 : Configuration application. properties
spring.application.name=Eureka-Server
server.port=8761
eureka.client.register-with-eureka=false
eureka-client-fetch-registry=false

Step 4 : Run Project and type in Browser localhost: Port Number

**How to Add Eureka Discovery Client in Project** :

Step 1 : Add Eureka Client Dependency (in pom.xml)

Dependencies : 
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-netflix-eureka-client</artifactId>
</dependency>

Spring Cloud dependencies :
<dependencyManagement>
    <dependencies>
       <dependency>
          <groupId>org.springframework.cloud</groupId>
          <artifactId>spring-cloud-dependencies</artifactId>
          <version>${spring-cloud.version}</version>
          <type>pom</type>
          <scope>import</scope>
       </dependency>
    </dependencies>
</dependencyManagement>

Dependencies 
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-netflix-eureka-client</artifactId>
</dependency>

Spring Cloud dependencies :
<dependencyManagement>
    <dependencies>
       <dependency>
          <groupId>org.springframework.cloud</groupId>
          <artifactId>spring-cloud-dependencies</artifactId>
          <version>${spring-cloud.version}</version>
          <type>pom</type>
          <scope>import</scope>
       </dependency>
    </dependencies>
</dependencyManagement>

Step 2 : the configuration application .properties 
spring.application.name=Job-Service

server.port=8081

#MySQL Connection
spring.datasource.url=jdbc:mysql://localhost:3306/microservice
spring.datasource.username=root
spring.datasource.password=1234
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

#Hibernate Configuration
spring.jpa.database-platform=org.hibernate.dialect.MySQL8Dialect
spring.jpa.generate-ddl=true
spring.jpa.hibernate.ddl-auto=update

#Eureka
#Eureka Server URL
eureka.client.serviceUrl.defaultZone=http://localhost:8761/eureka/

#Register with Eureka
eureka.client.register-with-eureka=true
eureka.client.fetch-registry=true

Step 3 : First Run Eureka Server then Run Eureka Client.







