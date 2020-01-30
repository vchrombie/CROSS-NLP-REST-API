# NLP-TOOLS-REST-API : README  #
A standalone collection of Natural Language Processing tools for the software engineering exposed by a REST API for the software engineering domain.


## Prerequisites ##

Please ensure that the following are installed on your system and docker is running before following the steps defined below.

	- Maven
	- JDK 8
	- Docker (docker requires at least 6gb of memory) 
	- Git

## Configuration (application.properties)##

The `application.properties` file located in `src/main/resources` enables you to configure numerous properties of the REST API. 

	- **server.address** : allows you to specify the server address you want the REST API to be bound to. At default the is `localhost`.
	
	- **server.port** : allows you to specify the port you want you would like the API to be accesed through. The default value is `8080`.


Full details of all the application properties can be found <a href="https://docs.spring.io/spring-boot/docs/current/reference/html/appendix-application-properties.html" target="_blank">here</a>

**1.** 

## Build Steps: ##

**1.** Open terminal, navigate to your chosen directory and clone the NLP-TOOLS_REST_API Repository using:

	git clone https://github.com/crossminer/NLP-TOOLS-REST-API.git
	
**2**. Open terminal and navigate to the `NLP-TOOLS_REST_API` directory. 

	
**3.** Once inside the directory, run the following command 
	
	mvn -N io.takari:maven:wrapper

This ensures that the Maven build has everything necessary to run (and you dont need to install mutliple versions of Maven).

	
**4.** Next we need to build the `ehu-nlp-rest_api.jar`. To do this run <u>one</u> of the following commands:

	For UNIX based systems run    :      	./mvnw install
	For Windows based systems run : 	mvnw.cmd install

### Deployment Options ###

The REST API can be deployed using as a runnable Jar or via Docker. See below for instructions. 

**Runnable Jar**


**Docker**

**1.** Whilst inside the `NLP-TOOLS_REST_API` directory, Run the following command to build a image 

	docker build -t ehu-rest-api .

**2.** To run the container enter the following command: 
	
	docker run -p <Port>:8080 -t crossminer/ehu-nlp-rest-api --name EHU-NLP-REST-API
	
Replacing  `<Port>` with the port number you would like the container to be accessible on. For example if you want to access the container using via port `2097` then you would run :

	docker run -p 2097:8080 crossminer/ehu-nlp-rest-api --name EHU-NLP-REST-API


## Landing Page ##



## Documentation ##

The documentation of the all the end points and model can be accessed via `<server-address>:<port-number>/swagger-ui.html`. For example (using the default configuration) 

	http://localhost:8080/swagger-ui.html
	

