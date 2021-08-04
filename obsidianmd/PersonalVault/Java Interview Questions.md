# Java Interview Questions
## Java Core Concepts
- Constructors? 2 Types
- Singleton and how to make one?
- Difference between == and equals()
- Access modifiers?
	- used to apply accessibility to classes, methods, other members.
- Constructor vs method?
- this() vs super()
- String vs StringBuilder vs StringBuffer?
- What is collection class in Java? 
- method overriding vs method overloading?

- What is JDBC Driver?
- What are the steps to connect to a database in Java?
- What is Spring
- Constructor Injection vs Setter Injection 
- What is Hibernate
- What is difference between Error and Exception?
- How to handle Java Exceptions
- Checked vs Unchecked Exceptions
- throw vs throws
- Exception hierarchy 
- What is a thread?
- heap vs stack?
## Java Strings
## Objects and Classes
## Java OOPS
Advantages of OOPs
- Modularity
	- each object forms a separate entity whose internal state or logic is decoupled from other objects
- Simplicity
	- Easier to model real world objects to reduce complexity
- Extendable 
	- add new features or make modifications to the class or logic with out changing the method name
Procedural vs OOP
- Easily model real world objects
- holds state and behavior
- encapsulates data
Core concepts of OOP
- PIE. A ACA
compile time polymorphism - binding is resolved in compile time.
## Java Collections
- Hash Map
	- 
## Java Programs
## Advanced Java
## SQL 
- https://www.wikiwand.com/en/Join_(SQL)
- https://en.wikibooks.org/wiki/Structured_Query_Language
- https://www.wikiwand.com/en/SQL_syntax
- Database
	- organized collection of data 
- RDBMS
	- CRUD
- Primary Key
	- a column or a set of columns that uniquely identify a row or a record in a table
- Foreign Key
	- a column or set of columns that references the primary key of another table establishing a link between them
- Join (5)
	- used to combine rows from two or more tables based on a related column
	- Inner Join
		- 
	- Outer Join
		- Left Outer
		- Right Outer
		- Full Outer
	- Cross
		- Cartesian product of rows from tables in the join (n x n rows)
		- rows which combine each row from the first table with each row from the second table
		```sql
			// explicit
			SELECT * 
			FROM EMPLOYEE CROSS JOIN DEPARTMENT;
			
			// implicit
			SELECT * 
			FROM EMPLOYEE, DEPARTMENT;
		```



## Java Spring
- open source Java based application framework
- Main advantage of spring
	- layered architecture, you only use what you need and
		- If a web app only add dependencies for building web app. Spring Boot makes it easier.
	- JDBC, ORM
- IOC (Inversion of Control) vs Dependency Injection
	- At the center of spring is the container. The container creates objects, wires them together, configures and manage their complete life cycle.
	- The container receives instructions for which objects to instantiate by reading metadata in xml, Java annotations, and Java code.
	- Benefits
		- minimize amount of code
		- promotes loose coupling
- 2 types of IOC
	- BeanFactory
	- ApplicationContext
- Dependency of Injection
	- you do not have to create object directly, just describe how they should be created. The IOC container will wire them together.
	- There are 3 types of DI:
		- Constructor Injection
		- Setter Injection
		- Interface Injection
	- Spring only uses Setter and Constructor Injections
- Constructor Injection vs Setter Injection
- Auto Wiring
- Component vs Controller vs Repository vs Service annotations
	- Controller (server; accepts requests), Service (business logic), Repository (persisting data) are all Components
	- Component 
		- marks Java class as a bean.
	- Controller
		- marks class as a Spring Web MVC controller.  Automatically imported into the DI container.
	- Service
		- l
- RequestMapping
