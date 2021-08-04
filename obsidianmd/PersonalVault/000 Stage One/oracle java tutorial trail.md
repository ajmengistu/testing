# Oracle Java Tutorial Trail
## Road Map
- [x] Subsection1 (due 12)
- [x] Subsection2 (due 13)
- [x] Subsection3 (due 14)
- [x] Subsection4 (due 15)
- [x] Subsection5 (due 16)
- [x] Subsection6 (due 17)
- [x] Subsection7 (due 18)
- [ ] Subsection8 (due 19)
- [ ] Subsection9 (due 20)
- [ ] Subsection10 (due 21)
- [ ] Subsection11 (due 22)
- [x] Subsection12 (due 23)
- [x] Subsection13 (due 24)
- [x] Subsection14 (due 25)

## Tutorial
- Getting started, intro to Java
	- software development process 
		- ![java compilation process](https://docs.oracle.com/javase/tutorial/figures/getStarted/getStarted-compiler.gif)
		- 1. source code is written in plain text files ending with `.java`	 extension
		- 2. source files compiled to `.class` files by `javac`
			- `.class` file does not contain code that is native to your processor, it contains _bytecodes_-- the machine language of the JVM.
		- 3. The java launcher tool then runs the app with an instance of the JVM.
		- Java has automatic garbage collection to help you avoid memory leaks

- [Object-Oriented Programming Concepts](https://docs.oracle.com/javase/tutorial/java/concepts/index.html)
    - [What Is an Object?](https://docs.oracle.com/javase/tutorial/java/concepts/object.html)
		- an instance of class with a ==state and behavior==
		- software objects are conceptually similar to real-world objects: consisting of state and behavior
		- an object stores its state in fields/variables and exposes its behavior through methods/functions
		- methods operate on an object's internal state and primary mechanism for object-to-object communication.
		
    -   [What Is a Class?](https://docs.oracle.com/javase/tutorial/java/concepts/class.html)
			- A blueprint or prototype from which individual objects are created and models the state and behavior of a real-world object.

    -   [What Is Inheritance?](https://docs.oracle.com/javase/tutorial/java/concepts/inheritance.html)
			- provides a natural mechanism for organizing and structuring your software.
			- different kinds of objects have a certain amount in common with each other, yet each has features that makes them unique
				- Mountain bike, road bike, and tandem bikes.
			- OOP allows classes to inherit commonly used state and behavior from other classes.
    -   [What Is an Interface?](https://docs.oracle.com/javase/tutorial/java/concepts/interface.html)
			- an interface is a ==contract== between a class and the outside world.
			- when a class implements an interface, it promises to implement all the abstract methods in that interface.
    -   [What Is a Package?](https://docs.oracle.com/javase/tutorial/java/concepts/package.html)
    -   [Questions and Exercises: Object-Oriented Programming Concepts](https://docs.oracle.com/javase/tutorial/java/concepts/QandE/questions.html)
		- Q & A: In Java programming language...
			- Real-world objects contain **state and behavior**
			- A software object's state is stored in **fields/variables**
			- A software object's behavior is exposed through **methods/functions**
			- Hiding internal data from the outside world, and accessing it only through publicly exposed methods is known as data **encapsulation**. 
			- A blueprint for a software object is called a **class**.
			- A common behavior can be defined in a **superclass** and inherited into a **subclass** using the **extends** keyword.
			- A collection of methods with no implementation is called an **interface**.
			- A namespace that organizes classes and interfaces by functionality is called a **package**.
			- The term API stands for **Application Programming Interface**.
-   [Language Basics](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/index.html)
	- NOTE: Google two's complement and 1's complement #researchlater 
	- NOTE: Read [Cornell two's complement](https://www.cs.cornell.edu/~tomf/notes/cps104/twoscomp.html), [Wiki](https://www.wikiwand.com/en/Two%27s_complement) #researchlater 
	- operators are used in building expressions, which compute a value.
	- expressions are the core components of statements and statements may be grouped into blocks.
    -   [Variables](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/variables.html)
		- instance variables (non-static fields)
			- unique to each instance of a class
		- class variables (static fields)
			- tells the compiler there is exactly one copy of this variable in existence, regardless how many times the class has been instantiated.
		- local variables
			- only visible to the methods in which they are declared.
		- parameters
			- variables to parameter-excepting methods and constructors 
		- Java naming rule:
			- variables are case-sensitive
				- can begin with a letter, "$", or "_"	only
					- subsequent characters can be letters, digits, "$", or underscore chars.
					- however, by convention use camel Case variables. 
        -   [Primitive Data Types](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html)
			-  8 primitive ==data types== supported by Java programming language 
				- __boolean__
					- size
						 - 1-bit data type, however the "size" isn't something that's precisely defined
					 - range:
						- two possible values: `true` or `false`
						- motivation:
							- simple flags that track true/false conditions 
				-  __byte__
					- size
						- 8-bit signed two's complement integer.
					- range:
						- minimum value: -128 (inclusive)
						- maximum value: 127 (inclusive)
					- motivation :
						- useful for saving memory in large arrays
						- code clarification via documentation
							- can be also be used in place of `int`, where the size limit helps to clarify your code; 
								- the fact that a variable's range is limited can serve as a form of documentation.
				-  __short__
					- size
						- 16-bit signed two's complement integer.
					- range:
						- minimum:  -32,768 (2^15)
						- maximum: 32,767 (2^15) - 1
					- motivation
						- to save memory in large arrays, in situations where the memory savings actually matters
				-  __char__
					- size
						- 16-bit "__unsigned__" Unicode character.
					- range:
						- min: '\u000'  or 0
						- max: `\uffff` (65,535 inclusive) (2^16) - 1
				-  __int__
					- size
						- 32-bit signed two's complement integer
					- range:
						- signed
							- min: (-2^31)
							- max: (2^31) - 1
						- unsigned
							- Since Java 8, you can use the `Integer ` class to represent __unsigned__ 32-bit integer
								- min: 0
								- max: (2^32) - 1
							- Use Integer class static methods such as `compareUnsigned` and `divideUnsigned` to support operations for unsigned integers
				- __long__
					- size
						- 64-bit two's complement integer.
					- range:
						- signed
							- min: (-2^63)
							- max: (2^63) - 1
						- unsigned
							- Since Java 8, you can use `Long` class to represent __unsigned__ 64-bit integers
								- min: 0
								- max: (2^64) - 1
							- Use Integer class static methods such as `compareUnsigned` and `divideUnsigned` to support operations for unsigned integers
				-  __float__
					-  size
						-  32-bit __single-precision__ floating point value. 
					-  why use decimal values?
						-  allows accuracy and precision
					-  range:
						-  min: 1.4E-45
						-  max: 3.40E38
					- motivation:
						- expressing:
							- currency (dollar & cents)
							- measurements (feet & inches)
							- time (hours, minutes, seconds)
						- use
							- when you need to save memory in large arrays of floating point numbers.
							- __NEVER USE__:
								- never be used for precise values: 
									- currency
								- Use `java.math.BigDecimal` class instead.
				-  __double__
					- size
						- 64-bit double-precision floating point value. 
					- range:
						- min: 4.9E-324 ![Java Primitive Default Values](https://4.bp.blogspot.com/-KviSh6mjDrs/VqoNwwxeWhI/AAAAAAAABao/46T-QGCGdyk/s1600/Primitive-Data-Types-in-Java-Programming-Language.png)
						- max: 1.79E308
					- use
						- for decimal values, this data type is generally the default choice
						- __NEVER USE__:
							- never be used for precise values: 
								- currency
							- Use `java.math.BigDecimal` class instead.
			- ![Java Primitive Default Values](https://4.bp.blogspot.com/-KviSh6mjDrs/VqoNwwxeWhI/AAAAAAAABao/46T-QGCGdyk/s1600/Primitive-Data-Types-in-Java-Programming-Language.png)
			- __Literals__
				- literals
					- syntactic representations of boolean, character, integer, string data.
					 ```java
					 	boolean result = true; // true is a boolean literal
						char capitalC = 'C';
						byte b = 100;
						short s = 1_000
						int i = 1_000_000
					 ```
					 
					- 5 types of literal values:
						- Boolean Literals
							- `true` and `false`
						- Integer Literals
							- `byte`, `short`, `int`, `long`
							- Integer literals are expressed byte these number systems:
								- Note: for general-purpose programming, the decimal system is likely to be the only number system you'll ever use.
								- Decimal
									- Base 10
									- digits consists of the numbers 0 through 9; number system we use every day.
									- `int x = 4 // 4 in decimal`
								- Octal
									- Base 8
									- digits consists of the numbers 0 through 7
									- `byte y = 011 // 9 in decimal`
								- Hexadecimal
									- Base 16
									- digits consists of the numbers 0 through 9 and the letters a to f or A to F.
									- `long z = 0x11 // 17 in decimal`
								- Binary
									- Base 2
									- digits consists of the numbers 0 to 1.
									- `int b = 0b11 // 3 in decimal`
						- Floating-Point Literals
							- A floating-point literal is of type `float`, if it ends with the letter ends with the letter `F` or `f`; otherwise its type is `double` and can optionally end with the letter `D` or `d`.
							- The default is `double` unless explicitly specified as `float` via `F` or `f`.
						- Character and String Literals
							- literals of type `char` and `String` may contain any Unicode (UTF-16) characters.
							- `char` literals
								- always use 'single quotes'
							- `String` literals
								- always use "double quotes"
								- `null` literal
									- `null` literal can be used as a value for any reference type. 
									- `null` can be assigned for any variable, except for primitive types.A
									- use: 
										- there's little you can do with `null`  value beyond testing for its presence.
										- to indicate some object is unavailable.
							- Class literal
								- formed by taking a class name and appending ".class"
									- `String.class`
										- This refers to the object of type Class that represents the type itself.
			- __Using Underscore Characters in Numeric Literals__
				```java
					long creditCardNumber = 1234_5678_9012_3456L;
					long socialSecurityNumber = 999_99_9999L;
					float pi =  3.14_15F;
					long hexBytes = 0xFF_EC_DE_5E;
					long hexWords = 0xCAFE_BABE;
					long maxLong = 0x7fff_ffff_ffff_ffffL;
					byte nybbles = 0b0010_0101;
					long bytes = 0b11010010_01101001_10010100_10010010;
				```
				- Valid syntax
					- you can place underscore only between digits; you __cannot__ place underscores in the following places:
						- At the beginning or end of a number
						- Adjacent to a decimal point in a floating point literal
						- Prior to an `F` or `L` <span id=anki-id>`<!--id:12312341234--!>`</span>
						- In positions where a string of digits is expected
					```java
					int x3 = 5____2; // valid
					int x1 = 3._14F; // invalid
					int x2 = 3.13_456; // valid
					int x6 = 0x_52; // invalid
					int x7 = 0x5_2; // valid
					int x7 = 0x52_; // invalid
					```
        -   [Arrays](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html)
			- The length of an array is established when the array is created. After creation, its fixed.
			- element
				- each item in an array and each element is accessed by its numerical index.
        -   [Summary of Variables](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/variablesummary.html)
			- Java programming languages uses both "fields" and "variables"
				- instance variables (non-static fields)
					- unique to each instance of a class
				- class variables (static fields)
					- declared with the `static` modifier
					- exactly one copy of a class variable, regardless of how many times the class has been instantiated 
				- local variables
					- store temporary state inside a method
				- parameters
					- variables that provide extra information to a method
			- Data types
				- the compiler will assign reasonable default value for fields
					- However, for local variables default value is never assigned
				- a literal
					- source code representation of a fixed value.
				- array
					- container object that holds a fixed number of values of a single type
					- length is established at creation time and after creation, its length is fixed.
    -   [Questions and Exercises: Variables](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/QandE/questions_variables.html)
		- Q&A: In Java programming language...
			- The term "instance variable" is another name for 
				- non-static field
			- The term "class variable" is another name for
				- static field
			- A local variable stores temporary state; it is declared inside a 
				- method
			- A variable declared within the opening and closing parenthesis of a method signature is called a
				- parameter 
			- What are the eight primitive data types supported by the Java programming language?
				- `boolean, byte, char, short, int, float, long, double`
			- Character strings are represented by the class
				- `java.lang.String`
			- An ___ is a container object that holds a fixed number of values of a single type.
				- array
    -   [Operators](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/operators.html)
		- operators with higher precedence are evaluated before operators with relatively lower precedence
		- ![Java Operator precedence](https://ucarecdn.com/4860994e-105d-456b-a98e-f3c51854830f/-/crop/478x539/214,123/-/preview/)
		- Unary operators
			- require only one operand
			- perform various operations such as incrementing/decrementing a value by one, negating an expression, or inverting the value of a boolean.
        -   [Assignment, Arithmetic, and Unary Operators](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/op1.html)
        -   [Equality, Relational, and Conditional Operators](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/op2.html)
        -   [Bitwise and Bit Shift Operators](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/op3.html)
        -   [Summary of Operators](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/opsummary.html)
    -   [Questions and Exercises: Operators](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/QandE/questions_operators.html)
    -   [Expressions, Statements, and Blocks](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/expressions.html)
		- expression
			- a construct made up of variables, operators, and method invocations that evaluates into a single value
			- `int cadence = 0`, `"hi " + 2`, `if (value1 == value2)`
			- compound expression
				- `1 * 2 * 2` 
		- statement
			- equivalent to sentences in natural languages
			- forms a complete unit of execution and terminates with a semicolon (`;`)
		- block 
			- a group of zero or more statements between balanced braces (`{}`).
		- Q&A:
			- `aValue = 8933.234; **// assignment statement**`
			- `aValue++; // **increment statement**`
			- `System.out.println("Hello World!"); **// method invocation statement**`
			- `Bicycle myBike = new Bicycle(); **// object creation statement**`
    -   [Questions and Exercises: Expressions, Statements, and Blocks](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/QandE/questions_expressions.html)
    -   [Control Flow Statements](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/flow.html)
		- Generally, statements are executed in your source files from top to bottom, in the order they appear.
		- control flow statements
			- break up the flow of execution by employing decision making, looping, and branching
		- 3 control flow statements in Java
			- decision-making statements
				- `if-then, if-then-else, switch`
			- looping statements
				- `for, while, do-while` 
			- branching statements
				- `break, continue, return`
        -   [The if-then and if-then-else Statements](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/if.html)
        -   [The switch Statement](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/switch.html)
        -   [The while and do-while Statements](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/while.html)
        -   [The for Statement](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/for.html)
			- infinite loop
				- `for ( ; ; ) { }`
				- `while(true){}`
				- the three expressions in a `for` loop are optional.
        -   [Branching Statements](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/branch.html)
			- `break` statement
				- two forms:
					- labeled 
						- terminates a labeled outer most statement
						- example
							- use a nested `for` loops to search for a value in a 2D array. When value is found,  a labeled `break` terminates the outer `for` loop (labeled "search")
								```java
								 search:
										for (i = 0; i < arrayOfInts.length; i++) {
											for (j = 0; j < arrayOfInts[i].length;
												 j++) {
												if (arrayOfInts[i][j] == searchfor) {
													foundIt = true;
													break search;
												}
											}
										}
								```
					- unlabeled
						- terminates the innermost `switch, for, while, do-while` statements
			- `continue` statement
				- skips the current iteration of a `for, while, or do-while` loop
				- two forms:
					- labeled
						- skips the current iteration of an outer loop marked with the given label
							```java						
							test:
									for (int i = 0; i <= max; i++) {
										int n = substring.length();
										int j = i;
										int k = 0;
										while (n-- != 0) {
											if (searchMe.charAt(j++) != substring.charAt(k++)) {
												continue test;
											}
										}
										foundIt = true;
											break test;
									}
									System.out.println(foundIt ? "Found it" : "Didn't find it");
							```
					- unlabeled
						- skips to the end of the innermost loop's body and evaluates the `boolean` expression that controls the loop.
        -   [Summary of Control Flow Statements](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/flowsummary.html)
    -   [Questions and Exercises: Control Flow Statements](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/QandE/questions_flow.html)
		-   Q&A:
					-   The most basic control flow statement supported by the Java programming language is the __if-then__ statement.
					-   The __switch__ statement allows for any number of possible execution paths.
					-   The __do-while__ statement is similar to the `while` statement, but evaluates its expression at the __bottom__ of the loop.
					-   How do you write an infinite loop using the `for` statement?
								```
										for ( ; ; ) {
										}
								```
					-    How do you write an infinite loop using the `while` statement?
								```
									while (true) {
									}
								```
-   [Classes and Objects](https://docs.oracle.com/javase/tutorial/java/javaOO/index.html)
	- nested
		- static nested classes
		- inner classes 
			- anonymous inner classes
		- local classes
		- lambda expressions
	- enum types
		- specialized classes that tallow you to define and use sets of constants
    -   [Classes](https://docs.oracle.com/javase/tutorial/java/javaOO/classes.html)
		-   anatomy of a class
        -   [Declaring Classes](https://docs.oracle.com/javase/tutorial/java/javaOO/classdecl.html)
			- In general, class declarations can include these components, in order:
				- Modifiers such as *public*, *private*, and a number of others that you will encounter later.
				- The class name, with the initial letter capitalized by convention.
				- The name of the class's parent (superclass), if any, preceded by the keyword *extends*. A class can only *extend* (subclass) one parent.
				- A comma-separated list of interfaces implemented by the class, if any, preceded by the keyword *implements*. A class can *implement* more than one interface.
				- The class body, surrounded by braces, {}. 
        -   [Declaring Member Variables](https://docs.oracle.com/javase/tutorial/java/javaOO/variables.html)
			- 3 type of variables:
				- fields
					- member variables in a class
				- local variables
					- variables in a method or block of code
				- parameters
					- variables in method declarations
			- access modifiers
				- let you control what other classes have access to a class member
			- variable types
				- All variables must have a type
					- primitive type or reference type
			- variable names
				- the first letter of a class name should be capitalized
				- the first (or only) word in a method name should be a verb
		-   [Defining Methods](https://docs.oracle.com/javase/tutorial/java/javaOO/methods.html)
			- More generally, method declarations have six components, in order: (6)
				- Modifiers
					- such as `public`, `private`, and others you will learn about later.
				- The return type
					- the data type of the value returned by the method, or `void` if the method does not return a value.
				- The method name
					- the rules for field names apply to method names as well, but the convention is a little different.
				- The parameter list in parenthesis
					- a comma-delimited list of input parameters, preceded by their data types, enclosed by parentheses, `()`. If there are no parameters, you must use empty parentheses.
				- An exception list
				- The method body, enclosed between braces
					- the method's code, including the declaration of local variables, goes here.
			- method signature
				- ```calculateAnswer(double, int, double, double)```
				- two of the components of a method declaration
					- method's name
					- parameter types
			- naming a method
				- by convention
					- verb in lowercase or multi-word name that begins with a verb in lowercase
					- followed by adjectives, nouns.
					- In multi-word names, the first letter of each of the second and following words should be capitalized
						- `run`
						- `runFast`
						- `getBackground`
						- `getFinalData`
						- `compareTo`
						- `setX`
						- `isEmpty`
			- typically, a method has a unique name within its class, unless it is overloaded
				- however, _method signatures_ are unique within a class
			- method overloading
				- Java programming language supports _overloading_ methods and Java can distinguish between methods with different _method signatures_.
			- overloaded methods are differentiated by the ==number and the type== of the arguments passed into the method
			- The compiler does not consider ==return type== when differentiating methods, 
				- so you CANNOT declare two methods with the same signature even if they have a different return type.
			- NOTE:
				- ==Overloaded methods== should be used ==sparingly==, as they can make code much ==less readable==.  
		-   [Providing Constructors for Your Classes](https://docs.oracle.com/javase/tutorial/java/javaOO/constructors.html)
			- What is the difference between a constructor and a method?
				- method
					- defines a behavior for a class
					- has a return type
					- method overloading 
				- constructor
					- invoked to create objects from the class blueprint
					- no return type
					- must use the name of the class
					- constructor overloading
			- constructor supports method overloading
				- Java compiler differentiates constructors on the basis of 
					- the number of arguments in the list
					- the type 
			- what is the result if two constructors have the same  number and type of arguments fro the same class
				- compile-time error
        -   [Passing Information to a Method or a Constructor](https://docs.oracle.com/javase/tutorial/java/javaOO/arguments.html)
			- parameters
				- the list of variables in a method or constructor declaration
			- arguments
				- the actual values that are passed in when the method or constructor is invoked
			- When you invoke a method or constructor
				- the arguments used must match the declaration's parameters in __type and order__
			- parameter types
				- can use any data type for a constructor or method
				- ==if you want to pass a method, then use==
					- lambda expressions
					- method reference
			- arbitrary number of arguments
				- use a _varargs_ construct to pass an arbitrary number of values to a method
				- use _varargs_
					- when you do not know how many of a particular type of argument will be passed to the method
				- to use _varargs_
					- follow the type of the last parameter by an ellipsis (three dots "..."), then a space, and the parameter name
				- the parameter will be treated as an array.
			- parameter names
				- parameter name must be unique in its scope
					- cannot be the same name as a local variable within the scope
				- however, parameter ==can have same name as one of the class's fields==.
					- In this case, the parameter is said to _shadow_ the field.
						- shadowing fields arbitrary 
							- con
								- make your code difficult to read
							```java
							public class Circle {
								private int x, y, radius;
								public void setOrigin(int x, int y) {
									...
								}
							}
							```
							- using `x and y` within the body of the method refers to the parameter, NOT the field.
							- to access the field, you must use a `this` keyword
			- passing primitive and reference data types as arguments
				- both primitive and referenced data types are passed into methods by value.
				- primitives
					- any change to the values of the parameters exist only within the scope of the method
				- referenced 
					- when the method returns, the passed-in reference still references the same object as before
					- however the state of the object can be modified, if they have proper access level.
    -   [Objects](https://docs.oracle.com/javase/tutorial/java/javaOO/objects.html)
        -   [Creating Objects](https://docs.oracle.com/javase/tutorial/java/javaOO/objectcreation.html)
			- a class provides the blueprint for objects
				- you create an object from a class.
			- creating an object involves
				- declaration
					- associating a variable name with an object type
					- `type name`
				- instantiation
					- creating an object by creating an instance of a class
					- `new` keyword is a Java operator that create the object
						- by allocating memory on the heap for a new object and returning a reference to that memory address
					- "instantiating a class" means
						- "creating an object" or creating an "instance" of a class
				- initialization
					- `new` keyword operator is followed by a call to a constructor, which initializes the new object.
			- a class has at least one constructor
				- if it does not explicitly declare any,
					- the Java compiler automatically provides a no-argument constructor, called the default constructor. 
						- ==This default constructor calls the class parent's no-argument constructor, or the Object constructor if the class has no other parent.==
						- ==If the parent has no explicit constructor (Object does have one), the compiler will reject the program.==
        -   [Using Objects](https://docs.oracle.com/javase/tutorial/java/javaOO/usingobject.html)
			- the garbage collector
				- managing memory explicitly is tedious and error-prone. 
					- some object-oriented languages require that you keep track of all the objects you create and that you explicitly destroy them when they are no longer needed.
					- google: oop programming languages that explicitly manage memory, like C++ #researchlater 
				- garbage collection
					- automatically deletes objects when it determines that they are no longer being used or referenced
					- An object is eligible for garbage collection 
						- when there are no more references to that object. 
				- de-referencing objects
					- references that are held in a variable are usually dropped when
						- the variable goes out of scope. 	
					- you can explicitly drop an object reference by 
						- setting the variable to the special value null. 
    -   [More on Classes](https://docs.oracle.com/javase/tutorial/java/javaOO/more.html)
        - [Returning a Value from a Method](https://docs.oracle.com/javase/tutorial/java/javaOO/returnvalue.html)
			- A method returns to the code that invoked it when the following occurs first
				- completes all the statements in the method,
				- reaches a return statement, or
				- throws an exception (covered later),
			- returning a class or interface
				- When a method uses a class name as its return type, 
					- the class of the type of the returned object must be either a subclass of, or the exact class of, the return type.
				- covariant return type
					- the return type is allowed to vary in the same direction as the subclass
				- you can use interface names as return types, 
					- in this case, the object must implement the
						- specified interface
        - [Using the this Keyword](https://docs.oracle.com/javase/tutorial/java/javaOO/thiskey.html)
			- Within an instance method or a constructor, this is a reference to the 
				- current object 
					- the object whose method or constructor is being called.
			- You can refer to any member of the current object from within 
				- an instance method or 
				- a constructor by using `this`
			- using `this` with a field
			- The most common reason for using the `this` keyword is
				- a field is shadowed by a method or constructor parameter
					```java
						public class Point {
							public int x = 0;
							public int y = 0;

							public Point(int a, int b) {
								x = a;
								y = b;
							}
						}	

						// but, it can have been written like this:
						public class Point{
							public int x = 0;
							public int y = 0;

							public Point(int x, int y) {
								this.x = x; // if x = x; or y = y;, then field values will not be modified
								this.y = y; // because, x and y refer to the local variables.
							}
						}
					```
				- each argument to the constructor shadows one of the object's fields.
					- `x` in the constructor refers to the local copy of the constructor's first argument. 
					- to refer to the field `x`, then the constructor must use `this.x`
			- using `this` with a constructor
				```java
					Public class Rectangle {
						private int x, y;
						private int width, height;

						public Rectangle() {
							this(0, 0, 1, 1);
						}

						public Rectangle(int width, int height) {
							this(0, 0, width, height);
						}
						...
					}
				```
				- explicit constructor invocation
					- from within a constructor, you can also use the `this` keyword to call another constructor in the same class. 
				- If present, the invocation of another constructor must be the first line in the constructor.
				- the compiler determines which constructor to call, based on 
					- the number and 
					- the type of arguments. 
        -   [Controlling Access to Members of a Class](https://docs.oracle.com/javase/tutorial/java/javaOO/accesscontrol.html)
			- tips when choosing an access level modifier
				- use the most restrictive access modifier that makes sense. 
					- use `private` unless you have a good reason not to
				- avoid `public` fields excepts for constants
        -   [Understanding Class Members](https://docs.oracle.com/javase/tutorial/java/javaOO/classvars.html)
			-  `static` keyword to create fields and methods that belong to the 
				- class, rather than to an instance of the class.
			- why use static fields and methods
				- sometimes, you want to have variables that are common to all objects.
				- every instance of the class shares a class variable, which is in one fixed location in memory. 
			- Not all combinations of instance and class variables and methods are allowed:
				- Instance methods can access instance variables and instance methods directly.
				- Instance methods can access class variables and class methods directly.
				- Class methods can access class variables and class methods directly.
				- Class methods __CANNOT__ access instance variables or instance methods directly
					- they must use an object reference. 
					- class methods cannot use the `this` keyword as there is no instance for `this` to refer to.
			- compile-time constant
				- If a primitive type or a string is defined as a constant and the value is known at compile time, 
					- the compiler replaces the constant name everywhere in the code with its value.
					- if the constant value changes, 
						- you must recompile classes that use this constant to get the current value
        -   [Initializing Fields](https://docs.oracle.com/javase/tutorial/java/javaOO/initial.html)
			```java
				public class BedAndBreakfast {
					public static int capacity = 10;
					private boolean full = true;
				}
			```
			- normally, initialization can be done in one line (see above code).
				- disadvantage 
					- this form of initialization has limitations because of its simplicity
						-  If initialization requires some logic (for example, error handling or a for loop to fill a complex array), 
							- simple one-line assignment is inadequate
			- initializing fields
				- static fields (2)
					- __static initialization block__
						- normal block of code enclosed in braces `{}` preceded by the `static` keyword
							```java
								static {
									// logic code to initialize static variables
								}
							```
							- a class can use any number of __static initialization blocks__ and they can appear anywhere in the class body.
							- The runtime system guarantees that static initialization blocks are called in the order that they appear in the source code.
					- private static method
						 ```java
						 	class Whatever {
								public static int[] nums = initializeGreeting();
								
								private static int[] initializeGreeting() {
									int[] nums = new int[5];
									for (int i = 0; i < 5; i++) { nums[i] = i; }
									return nums;
								}
							}
						 ```
						- advantage of private static methods
							- they can be reused later if you need to reinitialize the class (`static`) variable
				- instance fields (3)
					- constructor
						- normally, instance variables are initialized in constructors
							- where error handling or other logic can be used
					- initializer blocks
						- looks just like __static initializer blocks__, but without the `static` keyword:
							```java
								{
									// whatever code is needed for initialization goes here 
								}
							```
							- the Java compiler copies initializer blocks into every constructor. 
								- therefore, this approach can be used to share a block of code between multiple constructors.
					- final methods
						- A final method cannot be overridden in a subclass
							```java
								public class Animal 
									private Dog name = initializeDog();
									
									protected final Dog initilizeDog() {
										// initialize Dog object here
									}
								}
							```
							- advantage of using final methods to initialize instance fields
								- if sub-classes might want to reuse the initialization method.
							- why is the method final?
								- calling non-final methods during instance initialization can cause problems.
			- it is not necessary to declare fields at the beginning of the class definition, 
				- although this is the most common practice.
				- It is only necessary that they be 
					- declared and initialized before they are used. 
        -   [Summary of Creating and Using Classes and Objects](https://docs.oracle.com/javase/tutorial/java/javaOO/summaryclasses.html)
			- 
    -   [Questions and Exercises: Classes](https://docs.oracle.com/javase/tutorial/java/javaOO/QandE/creating-questions.html)
    -   [Questions and Exercises: Objects](https://docs.oracle.com/javase/tutorial/java/javaOO/QandE/objects-questions.html)
    -   [Nested Classes](https://docs.oracle.com/javase/tutorial/java/javaOO/nested.html)
        -   [Inner Class Example](https://docs.oracle.com/javase/tutorial/java/javaOO/innerclasses.html)
        -   [Local Classes](https://docs.oracle.com/javase/tutorial/java/javaOO/localclasses.html)
        -   [Anonymous Classes](https://docs.oracle.com/javase/tutorial/java/javaOO/anonymousclasses.html)
        -   [Lambda Expressions](https://docs.oracle.com/javase/tutorial/java/javaOO/lambdaexpressions.html)
            -   [Method References](https://docs.oracle.com/javase/tutorial/java/javaOO/methodreferences.html)
        -   [When to Use Nested Classes, Local Classes, Anonymous Classes, and Lambda Expressions](https://docs.oracle.com/javase/tutorial/java/javaOO/whentouse.html)
    -   [Questions and Exercises: Nested Classes](https://docs.oracle.com/javase/tutorial/java/javaOO/QandE/nested-questions.html)
    -   [Enum Types](https://docs.oracle.com/javase/tutorial/java/javaOO/enum.html)
    -   [Questions and Exercises: Enum Types](https://docs.oracle.com/javase/tutorial/java/javaOO/QandE/enum-questions.html)
-   [Annotations](https://docs.oracle.com/javase/tutorial/java/annotations/index.html)
    -   [Annotations Basics](https://docs.oracle.com/javase/tutorial/java/annotations/basics.html)
    -   [Declaring an Annotation Type](https://docs.oracle.com/javase/tutorial/java/annotations/declaring.html)
    -   [Predefined Annotation Types](https://docs.oracle.com/javase/tutorial/java/annotations/predefined.html)
    -   [Type Annotations and Pluggable Type Systems](https://docs.oracle.com/javase/tutorial/java/annotations/type_annotations.html)
    -   [Repeating Annotations](https://docs.oracle.com/javase/tutorial/java/annotations/repeating.html)
    -   [Questions and Exercises: Annotations](https://docs.oracle.com/javase/tutorial/java/annotations/QandE/questions.html)
-   [Interfaces and Inheritance](https://docs.oracle.com/javase/tutorial/java/IandI/index.html)
    -   [Interfaces](https://docs.oracle.com/javase/tutorial/java/IandI/createinterface.html)
        -   [Defining an Interface](https://docs.oracle.com/javase/tutorial/java/IandI/interfaceDef.html)
        -   [Implementing an Interface](https://docs.oracle.com/javase/tutorial/java/IandI/usinginterface.html)
        -   [Using an Interface as a Type](https://docs.oracle.com/javase/tutorial/java/IandI/interfaceAsType.html)
        -   [Evolving Interfaces](https://docs.oracle.com/javase/tutorial/java/IandI/nogrow.html)
        -   [Default Methods](https://docs.oracle.com/javase/tutorial/java/IandI/defaultmethods.html)
        -   [Summary of Interfaces](https://docs.oracle.com/javase/tutorial/java/IandI/summary-interface.html)
    -   [Questions and Exercises: Interfaces](https://docs.oracle.com/javase/tutorial/java/IandI/QandE/interfaces-questions.html)
    -   [Inheritance](https://docs.oracle.com/javase/tutorial/java/IandI/subclasses.html)
        -   [Multiple Inheritance of State, Implementation, and Type](https://docs.oracle.com/javase/tutorial/java/IandI/multipleinheritance.html)
        -   [Overriding and Hiding Methods](https://docs.oracle.com/javase/tutorial/java/IandI/override.html)
        -   [Polymorphism](https://docs.oracle.com/javase/tutorial/java/IandI/polymorphism.html)
        -   [Hiding Fields](https://docs.oracle.com/javase/tutorial/java/IandI/hidevariables.html)
        -   [Using the Keyword super](https://docs.oracle.com/javase/tutorial/java/IandI/super.html)
        -   [Object as a Superclass](https://docs.oracle.com/javase/tutorial/java/IandI/objectclass.html)
        -   [Writing Final Classes and Methods](https://docs.oracle.com/javase/tutorial/java/IandI/final.html)
        -   [Abstract Methods and Classes](https://docs.oracle.com/javase/tutorial/java/IandI/abstract.html)
        -   [Summary of Inheritance](https://docs.oracle.com/javase/tutorial/java/IandI/summaryinherit.html)
    -   [Questions and Exercises: Inheritance](https://docs.oracle.com/javase/tutorial/java/IandI/QandE/inherit-questions.html)
-   [Numbers and Strings](https://docs.oracle.com/javase/tutorial/java/data/index.html)
    -   [Numbers](https://docs.oracle.com/javase/tutorial/java/data/numbers.html)
        -   [The Numbers Classes](https://docs.oracle.com/javase/tutorial/java/data/numberclasses.html)
        -   [Formatting Numeric Print Output](https://docs.oracle.com/javase/tutorial/java/data/numberformat.html)
        -   [Beyond Basic Arithmetic](https://docs.oracle.com/javase/tutorial/java/data/beyondmath.html)
        -   [Summary of Numbers](https://docs.oracle.com/javase/tutorial/java/data/numbersummary.html)
    -   [Questions and Exercises: Numbers](https://docs.oracle.com/javase/tutorial/java/data/QandE/numbers-questions.html)
    -   [Characters](https://docs.oracle.com/javase/tutorial/java/data/characters.html)
    -   [Strings](https://docs.oracle.com/javase/tutorial/java/data/strings.html)
        -   [Converting Between Numbers and Strings](https://docs.oracle.com/javase/tutorial/java/data/converting.html)
        -   [Manipulating Characters in a String](https://docs.oracle.com/javase/tutorial/java/data/manipstrings.html)
        -   [Comparing Strings and Portions of Strings](https://docs.oracle.com/javase/tutorial/java/data/comparestrings.html)
        -   [The StringBuilder Class](https://docs.oracle.com/javase/tutorial/java/data/buffers.html)
        -   [Summary of Characters and Strings](https://docs.oracle.com/javase/tutorial/java/data/stringsummary.html)
    -   [Autoboxing and Unboxing](https://docs.oracle.com/javase/tutorial/java/data/autoboxing.html)
    -   [Questions and Exercises: Characters and Strings](https://docs.oracle.com/javase/tutorial/java/data/QandE/characters-questions.html)
-   [Generics (Updated)](https://docs.oracle.com/javase/tutorial/java/generics/index.html)
    -   [Why Use Generics?](https://docs.oracle.com/javase/tutorial/java/generics/why.html)
    -   [Generic Types](https://docs.oracle.com/javase/tutorial/java/generics/types.html)
        -   [Raw Types](https://docs.oracle.com/javase/tutorial/java/generics/rawTypes.html)
    -   [Generic Methods](https://docs.oracle.com/javase/tutorial/java/generics/methods.html)
    -   [Bounded Type Parameters](https://docs.oracle.com/javase/tutorial/java/generics/bounded.html)
        -   [Generic Methods and Bounded Type Parameters](https://docs.oracle.com/javase/tutorial/java/generics/boundedTypeParams.html)
    -   [Generics, Inheritance, and Subtypes](https://docs.oracle.com/javase/tutorial/java/generics/inheritance.html)
    -   [Type Inference](https://docs.oracle.com/javase/tutorial/java/generics/genTypeInference.html)
    -   [Wildcards](https://docs.oracle.com/javase/tutorial/java/generics/wildcards.html)
        -   [Upper Bounded Wildcards](https://docs.oracle.com/javase/tutorial/java/generics/upperBounded.html)
        -   [Unbounded Wildcards](https://docs.oracle.com/javase/tutorial/java/generics/unboundedWildcards.html)
        -   [Lower Bounded Wildcards](https://docs.oracle.com/javase/tutorial/java/generics/lowerBounded.html)
        -   [Wildcards and Subtyping](https://docs.oracle.com/javase/tutorial/java/generics/subtyping.html)
        -   [Wildcard Capture and Helper Methods](https://docs.oracle.com/javase/tutorial/java/generics/capture.html)
        -   [Guidelines for Wildcard Use](https://docs.oracle.com/javase/tutorial/java/generics/wildcardGuidelines.html)
    -   [Type Erasure](https://docs.oracle.com/javase/tutorial/java/generics/erasure.html)
        -   [Erasure of Generic Types](https://docs.oracle.com/javase/tutorial/java/generics/genTypes.html)
        -   [Erasure of Generic Methods](https://docs.oracle.com/javase/tutorial/java/generics/genMethods.html)
        -   [Effects of Type Erasure and Bridge Methods](https://docs.oracle.com/javase/tutorial/java/generics/bridgeMethods.html)
        -   [Non-Reifiable Types](https://docs.oracle.com/javase/tutorial/java/generics/nonReifiableVarargsType.html)
    -   [Restrictions on Generics](https://docs.oracle.com/javase/tutorial/java/generics/restrictions.html)
    -   [Questions and Exercises: Generics](https://docs.oracle.com/javase/tutorial/java/generics/QandE/generics-questions.html)
 

[Packages](https://docs.oracle.com/javase/tutorial/java/package/index.html)
[Creating and Using Packages](https://docs.oracle.com/javase/tutorial/java/package/packages.html)
[Creating a Package](https://docs.oracle.com/javase/tutorial/java/package/createpkgs.html)
[Naming a Package](https://docs.oracle.com/javase/tutorial/java/package/namingpkgs.html)
[Using Package Members](https://docs.oracle.com/javase/tutorial/java/package/usepkgs.html)
[Managing Source and Class Files](https://docs.oracle.com/javase/tutorial/java/package/managingfiles.html)
[Summary of Creating and Using Packages](https://docs.oracle.com/javase/tutorial/java/package/summary-package.html)
[Questions and Exercises: Creating and Using Packages](https://docs.oracle.com/javase/tutorial/java/package/QandE/packages-questions.html)

Basic card `::`
Basic (reverse) card (`:?:`) or `?...`
- Java Programming Language:
	- Object Oriented Principle (OOP)(4)
		- What does `PIE.A ACA` stand for?::What is the best Mneumonic device to remember (Polymorphism, Inheritance, Encapsulation, Abstraction, Association, Composition, Aggregation) OOP?
	- Data Types:
		- __int__:
			- size(bits):: 32-bit signed two's complement integer ![Java Primitive Default Values](https://4.bp.blogspot.com/-KviSh6mjDrs/VqoNwwxeWhI/AAAAAAAABao/46T-QGCGdyk/s1600/Primitive-Data-Types-in-Java-Programming-Language.png)` <-{ID:identifier}->`
			- range: signed:: min: (-2^31), max: (2^31) - 1 <-{ID:identifier}->
			- range: unsigned:: Since Java 8, you can use the `Integer ` class to represent __unsigned__ 32-bit integer, min: 0, max: (2^32) - 1 <-{ID:identifier}->
			- Which `Integer` class methods support operations for unsigned integers?:: Use Integer class static methods such as `compareUnsigned` and `divideUnsigned` to support operations for unsigned integers <-{ID:identifier}->
		- __long__:
			- size(bits):: 64-bit two's complement integer.
			- range: signed:: min: (-2^63), max: (2^63) - 1
			- range: unsigned:: Since Java 8, you can use `Long` class to represent __unsigned__ 64-bit integers, min: 0, max: (2^64) - 1
			- Which `Integer` class methods support operations for unsigned `Long` integers?:: Use Integer class static methods such as `compareUnsigned` and `divideUnsigned` to support operations for unsigned integers
	- Generics:
		- Classes:
			- What is one __advantage__ of Java Generics?:: Runtime errors moved to compile time.
			- What is one example of Java Generics?::
				```java
					public static void main(String ...args){
						System.out::println();
					}
				```
---
- dadfadsf
- asdfads
	- asdfasdf
	- adf asdfasdfasdf
	 - asdfasdf 
