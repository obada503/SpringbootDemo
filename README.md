# SpringbootDemo
 
 Some important Spring Framework Annotations
 
--------------------------------------------

@ServiceAnnotation

@Required

@Autowired

@Configuration

@ComponentScan

@Bean

@Component

@Controller

@Service

@Repository, etc.


Client Side API Layers
-------------

    Layer 1 (GET-POST-PUT-DELETE)- talking to Layer 2 

    Layer 2(Service Layer: For business logic)- giving back data to Layer 1. 
    
    Layer 3(Data access layer: For connecting to the Database)- the goal is to store the student in the database.

Spring Initializer: dependencies used
-------------------------------------
- Spring Web

- Spring Data JPA
                 -->abstracts the complexity needed to interact with databse.

                 -->abstraction on top of JPA and Hibernate.
		 
                 -->hibernate is one implementation of JPA
		 
                 -->reduces boiler plate code, and gives us ability to make a lot of queries.
		 
 PostgreSQL Driver--> To connect to Postgres: 
----------------------------------------------
                                               psql -U postgres

		                               \l- list databases
		       
		                               \c-connect to database	 

@RestController: makes the whole class serve restful endpoints.


@GetMapping package to annotate a block to get something from server.


Will implement a class called student with some attributes, that will then be stored in the database.

Steps:
------
1: create a package called student containing a Student class.

2: the class will have attributes that we will generate getters and setters to manipulate them. (ALT+INSERT) -shortcut

3: StudentController will contain all resources for API instead of default RestController

4: changed localhost:8008 to localhost:8080/apy/v1/student for our student class.

5: now we create a class for the service layer for managing students so the api layer can get some data from it. Service layer will talk to data
   access layer to get information also. 
   
6: studentService class must be a bean, or a class that must be instantiate. 

7: to connect student to database we need @Entity for hibernate and @Table for our db table 

8: in student class-> @Id, @SequenceGenerator, and @GeneratedValue annotations are used.


Output is as follows on http://localhost:8080/api/v1/student

-------------------------------------------------------------

[{"id":1,"name":"Obada","email":"obadahamdan232@gmail.com","dob":"2001-01-22","age":21}]


Debugging

----------
1) error description: Web server failed to start. Port 8080 was already in use.

run cmd as administrator:

Solution-> netstat -ona | findstr :8080 | findstr LISTENING

	-> taskkill /PID 26748 /F 
