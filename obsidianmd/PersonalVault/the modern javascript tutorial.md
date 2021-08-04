# The JavaScript language
- [x] Subsection1 (due 12)
- [x] Subsection2 (due 13)
- [x] Subsection3 (due 14)
- [x] Subsection4 (due 15)
- [ ] Subsection5 (due 16)
- [ ] Subsection6 (due 17)
- [ ] Subsection7 (due 18)
- [ ] Subsection8 (due 19)
- [ ] Subsection9 (due 20)
- [ ] Subsection10 (due 21)
- [ ] Subsection11 (due 22)
- [ ] Subsection12 (due 23)
- [ ] Subsection13 (due 24)
- [ ] Subsection14 (due 25)

Here we learn JavaScript, starting from scratch and go on to advanced concepts like OOP.
We concentrate on the language itself here, with the minimum of environment-specific notes.

- [An introduction](https://javascript.info/getting-started)
	- [An Introduction to JavaScript](https://javascript.info/intro)
		- https://www.wikiwand.com/en/Ajax_(programming) #researchlater 
		- https://www.wikiwand.com/en/Comet_(programming) #researchlater 
		- ECMAScript Wikipedia
			- https://www.google.com/search?q=javascript+code+name+engines&client=ubuntu&hs=HGJ&channel=fs&source=lnms&tbm=isch&sa=X&ved=2ahUKEwjZ8arKvunrAhU2mnIEHWrvDI8Q_AUoAXoECBAQAw&biw=960&bih=942#imgrc=2C59GwQe26t7gM #researchlater 
			- different version of JavaScript on Wikipedia #researchlater 
		- _JavaScript_ was initially created to “make web pages alive”.
		- The programs in this language are called _scripts_. They can be written right in a web page’s HTML and run automatically as the page loads.
			- Scripts are provided and executed as plain text. They don’t need special preparation or compilation to run.
		- Why is it called JavaScript?
			- When JavaScript was created, it initially had another name: “LiveScript”. 
			- But Java was very popular at that time, so it was decided that positioning a new language as a “younger brother” of Java would help.
		- Where can JavaScript be executed?
			- Today, JavaScript can execute (3 locations)
				- in the browser, on the server, or any device that has a special program called [the JavaScript engine](https://en.wikipedia.org/wiki/JavaScript_engine).
		- What is another name for the embedded engine in the browser?
			-  “JavaScript virtual machine”.
		- Different run-time engines have different code names
			- V8
				- Google Chrome
				- Microsoft Edge
			- Spider Monkey
				- Mozilla Firefox
			- JavaScriptCore
				- Apple Safari
			- Chakra
				- Internet Explorer
		- How do engines work?
			- Engines are complicated. But the basics are easy.
			1.  The engine (embedded if it’s a browser) reads (“parses”) the script.
			2.  Then it converts (“compiles”) the script to the machine language.
			3.  And then the machine code runs, pretty fast.
		- [What can in-browser JavaScript do?](https://javascript.info/intro#what-can-in-browser-javascript-do)
			- Modern JavaScript is a “safe” programming language. why? 
				- It does not provide low-level access to memory or CPU, because it was initially created for browsers which do not require it.
			- In-browser JavaScript can do everything related to webpage manipulation, interaction with the user, and the webserver.
			- For instance, in-browser JavaScript is able to:
				-   Add new HTML to the page, change the existing content, modify styles.
				-   React to user actions, run on mouse clicks, pointer movements, key presses.
				-   Send requests over the network to remote servers, download and upload files (so-called [AJAX](https://en.wikipedia.org/wiki/Ajax_(programming)) and [COMET](https://en.wikipedia.org/wiki/Comet_(programming)) technologies).
				-   Get and set cookies, ask questions to the visitor, show messages.
				-   Remember the data on the client-side (“local storage”).
		- [What CAN’T in-browser JavaScript do?](https://javascript.info/intro#what-can-t-in-browser-javascript-do)
			- JavaScript’s abilities in the browser are limited for the sake of the user’s safety. How?
				- The aim is to prevent an evil webpage from accessing private information or harming the user’s data.
			- Examples of such restrictions include:
				- JavaScript on a webpage ==may not== read/write arbitrary files on the hard disk, copy them or execute programs. 
					- It has no direct access to OS functions.
					- Modern browsers allow it to work with files, but the access is limited and only provided if the user does certain actions, like “dropping” a file into a browser window or selecting it via an `<input>` tag.
					- There are ways to interact with camera/microphone and other devices, but they require a user’s explicit permission.
						- So a JavaScript-enabled page may not sneakily enable a web-camera, observe the surroundings and send the information to the [NSA](https://en.wikipedia.org/wiki/National_Security_Agency).
				- Different tabs/windows generally do not know about each other.
					-  Sometimes they do, for example when one window uses JavaScript to open the other one.
						- But even in this case, JavaScript from one page may not access the other if they come from different sites (from a different domain, protocol or port).
					- This is called the “Same Origin Policy”. 
						- To work around that, _both pages_ must agree for data exchange and contain a special JavaScript code that handles it. We’ll cover that in the tutorial.
						- This limitation is, again, for the user’s safety. 
							- A page from `http://anysite.com` which a user has opened must not be able to access another browser tab with the URL `http://gmail.com` and steal information from there.
				- JavaScript can easily communicate over the net to the server where the current page came from. 
					- But its ability to receive data from other sites/domains is crippled. 
					- Though possible, it requires explicit agreement (expressed in HTTP headers) from the remote side. Once again, that’s a safety limitation.
				- Such limits do not exist if JavaScript is used outside of the browser, for example on a server.
					- Modern browsers also allow plugin/extensions which may ask for extended permissions.
		- [What makes JavaScript unique?](https://javascript.info/intro#what-makes-javascript-unique)
			- There are at least _three_ great things about JavaScript:
				- Full integration with HTML/CSS.
				- Simple things are done simply.
				- Support by all major browsers and enabled by default.
			- JavaScript is the only browser technology that combines these three things.
			- That’s what makes JavaScript unique. That’s why it’s the most widespread tool for creating browser interfaces.
			- That said, JavaScript also allows to create servers, mobile applications, etc.
		- [Languages “over” JavaScript](https://javascript.info/intro#languages-over-javascript)
			- So recently a plethora of new languages appeared, which are _transpiled_ (converted) to JavaScript before they run in the browser.
			- Modern tools make the transpilation very fast and transparent, actually allowing developers to code in another language and auto-converting it “under the hood”.
			- Examples of such languages:
				- [CoffeeScript](http://coffeescript.org/)
					- is a “syntactic sugar” for JavaScript. It introduces shorter syntax, allowing us to write clearer and more precise code. Usually, Ruby devs like it.
				- [TypeScript](http://www.typescriptlang.org/) 
					- is concentrated on adding “strict data typing” to simplify the development and support of complex systems. It is developed by Microsoft.
				- [Flow](http://flow.org/)
					- also adds data typing, but in a different way. Developed by Facebook.
				- [Dart](https://www.dartlang.org/)
					- is a standalone language that has its own engine that runs in non-browser environments (like mobile apps), but also can be transpiled to JavaScript. Developed by Google.
				- [Brython](https://brython.info/)
					- is a Python transpiler to JavaScript that allow to write application in pure Python without JavaScript.
		- [Summary](https://javascript.info/intro#summary)
			- JavaScript was initially created as a browser-only language, but is now used in many other environments as well.
			- Today, JavaScript has a unique position as the most widely-adopted browser language with full integration with HTML/CSS.
			- There are many languages that get “transpiled” to JavaScript and provide certain features. It is recommended to take a look at them, at least briefly, after mastering JavaScript.
	- [Manuals and specifications](https://javascript.info/manuals-specifications)
		- [Specification](https://javascript.info/manuals-specifications#specification)
			- Specifications
				- https://www.ecma-international.org/publications/standards/Ecma-262.htm
					- detailed, formalized information on JavaScript
				- https://github.com/tc39/proposals
					- a new specification version is released every year.
			- Manuals
				- One can find it at https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference.
			- Compatibility Tables
				- [can i use](https://caniuse.com)
				- [can i use cryptography](https://caniuse.com/cryptography)
				- https://kangax.github.io/compat-table
					- a table with language features and engines that support those or don’t support.
	- [Code editors](https://javascript.info/code-editors)
	- [Developer console](https://javascript.info/devtools)
- [JaaScript Fundamentals](https://javascript.info/first-steps)
	- [Hello, world!](https://javascript.info/hello-world)
		- `<script>`
			- used to add JavaScript code to an HTML page <sup style="color:grey; font-size: 10px">id:234234</sup>
			- only the simplest scripts are put into HTML
				- more complex ones reside in separate files
				- pros
					- the browser will download the separate file and store it in its cache
						- wiki search web cache #researchlater 
							- other web pages that reference that same script will take it from the cache instead of downloading it,
								- so the file is actually downloaded only once.
									- thus, ==reduces traffic and makes pages faster==
			- `type` and `language` attributes are not required
			- `src` attribute
				- a single `<script>` tag CANNOT have both the `src` attribute and code inside
				- if `src` is set, the script content inside will be ignored
					- will not work:
						```html 
								<script src="file.js">
								alert(1); // the content is ignored, because src is set
								</script>
						```
					- must choose either an external `<script src="..">` or regular `<script>` tag with code
					- will work when split into two scripts
						 ```html 
								<script src="file.js"></script>
								<script>
								  alert(1);
								</script>
						 ```
	- [Code structure](https://javascript.info/structure)
		- statements
			- syntax constructs and commands ("lines of code, that often end in semicolons") that perform actions
			- separated often with a semicolon
			- usually, written on separate lines
				- to make code more readable
		- semicolons
			- maybe omitted in most cases when a line break exists
				- this works
					```js	
						 alert('Hello')
						 alert('World')
					```
			- automatic semicolon insertion
				- JavaScript interprets the line break as an "implicit" semicolon
				- In __most cases__, a new line implies a semicolon, 
					- but, "in most cases" does not mean "always"
						- there are cases when a newline does not mean a semicolon.
							```js
								alert(3 + 
								1
								+ 2
								); // output 6
							```
						- no error 
							 ```js
							 	[1, 2].forEach(alert) // alerts 1, then 2
							 ```
						- error
							```javascript
								alert("There will be an error") // alerts "There will be an error"
								[1, 2].forEach(alert) // error
								
								// the above code is treated as a single ling statement, such as
								// this how the JS engines sees it:
								alert("There will be an error")[1, 2].forEach(alert)
								
								alert("This will be fine!"); // alerts "This will be fine"
								[1, 2].forEach(alert) // alerts 1, then 2
							```
		- comments
			- describes what the code does and why
			- the JS engines ignores comments
			- one-line comment
				- "//''
			- multiple-line comment
				- `"/* like this */"`
			- nested comments are NOT supported
			- cons
				- increase the overall code footprint
					- however, there are tools which _minify_ code before publishing to a production server. how?
						- they remove comments, so they DONOT appear in the working scripts.
							- therefore, comments DO NOT have a negative effect on production.
	- [The modern mode, "use strict"](https://javascript.info/strict-mode)
		- "use strict"
			- a string directive
			- When it is located at the top of a script, the whole script works the “modern” way.
				```js
					"use strict";
					// this code works the modern way
				```
			- Modern JavaScript supports “classes” and “modules” 
				- that enable `use strict` automatically. 
				- So we don’t need to add the `"use strict"` directive, if we use them.
	- [Variables](https://javascript.info/variables)
		- there are two limitations on variable names in JavaScript:
			- The name must contain only 
				- letters
				- digits 
				- or the symbols `$` and `_`.
			- The first character must not be a digit.
		- valid
			- `let userName;`
			- `let test123;`
		- convention
			- if the variable name contains multiple words
				- `camelCase`
			- dollar sign `$` and the underscore `_` can both be used as variables
				```js
					let $ = 1;
					let _ = 2;
					alert($ + _); // 3
				```
			- invalid variable names
				```js
					let 2a // cannot start with a digit
					let my-name; // hyphens '_' aren't allowed in the name 
				```
			- case matters
				```js
					// two variable below are 
					let apple; 
					let Apple;
				```

		- An assignment without `use strict`
			- Normally, we need to define a variable before using it.
			- But in the old times, it was technically possible to create a variable by a mere assignment of the value WITHOUT using `let`. 
			- This still works now if we don’t put `use strict` in our scripts to maintain compatibility with old scripts.
			 ```js
				// by default note: no "use strict"; in this example
				num = 5; // the variable num is created, if it does not exist
				alert(num); // 5

				// bad practice and would cause an error in strict mode
				"use strict";
				n = 5; // error: n is not defined
			 ```
		- A variable name should have a clean, obvious meaning, describing the data that it stores.
		- Variable naming is one of the most important and complex skills in programming. 
		- A quick glance at variable names can reveal which code was written by a beginner versus an experienced developer.
		- In a real project, most of the time is spent 
			- modifying and extending an existing code base 
			- rather than writing something completely separate from scratch. 
		- Some good-to-follow rules are:
			- Use human-readable names like 
				- `userName` or `shoppingCart`.
			- Stay away from abbreviations or short names like 
				- `a`, `b`, `c`, unless you really know what you’re  doing.
			- Make names maximally descriptive and concise. 
				- Examples of bad names are `data` and `value`. 
					- Such names say nothing. 
					- It’s only okay to use them if the context of the code makes it exceptionally obvious which data or value the variable is referencing.
			- Agree on terms within your team and in your own mind.
				- If a site visitor is called a “user” then we should name related variables 
					- `currentUser` or `newUser` instead of `currentVisitor` or `newManInTown`.
		- An extra variable is good, not evil.
		- there are 3 ways to declare variables in JS
			- `let`
			- `const`
			- `var`
		- Always use variable types
			- `let` and `const`
			- NOT
				- `var`
		- variable scope
			- ![scopes](https://res.cloudinary.com/practicaldev/image/fetch/s--UoVTH7K7--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/tgk6utfxmxmifss08wab.png)
			```js
				// var variables are function scoped, 
				// visible not only within the declared block
				function foo() {
					if (true) { var x = 5; }
					console.log(x); // 5
				}
				
				// let and const are block scoped (within curley brasis {})
				// only visible in the block declared
				function foo() {
					if (true) { let x = 5; }
					console.log(x) // error as x is not defined here
				}
				
				// let and var have the same scope function level (blocked).
				function foo() {
					let x = 5;
					if (true) console.log(x); // 5
				}
			```
	- [Data types](https://javascript.info/types)
		- latest ECMAScript standard defines 9 types: [JavaScript data types and data structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
			- 7 primitive data types, checked by `typeof` operator
				- 1 special primitive type: `null`, `typeof null === "object" // NOT "null"`
			- structural type:
				- object
				- function
		- JavaScript is dynamically typed similar to Python
			- A declared variable can store any type of value, `string`, `number`
		- primitive data type in JavaScript
			- data that is NOT an object and has NO methods
			- 6 primitive data types
				- `boolean`
					- `true` and `false`
				- `number` 
				- `bigint`
				- `string`
				- `symbol`
				- `null`
					- has exactly one value
						- `null`
				- `undefined`
					- has exactly one value
						- `undefined`
		- 8 basic data types in JavaScript
			- `boolean` 
				- for `true` and `false`.
			- `number` 
				- max value
					- `(2^53) - 1 = 9007199254740991` 
				- min value
					- `-(2^53) - 1`
				- for numbers of any kind
					- integer or floating-point numbers
				- special numeric values that belong to this data type
					- `Infinity`
						- represents the mathematical infinity
						- a special value that's greater than any number
						- `alert(1 / 0) // Infinity`
						- `alert(Infinity (* or +) Infinity) // Infinity`
						- `alert(Infinity (/ or -) Infinity) // NaN`
					- `-Infinity`
					- `NaN`
						- represents computational error
						- result of incorrect or an undefined mathematical operation
						- `alert("hello " (* or / or -) 2) // NaN`
						- `alert("hello" + 2) // hello2, not a NaN`
						- 
			- `bigint` 
				- is for integer numbers of arbitrary length.
				- created by appending `n` at the end of an integer, NOT a floating-point integer
				- `const bigInt = 234234234234234234234123n`
			- `string` 
				- for strings. 
					- a string may have zero or more characters,
						- there's NO separate single-character type, such `char` in Java or C programming languages
					- no difference between single and double quote strings
					- 3 type of `string` quotes
						- double quotes
							- "hello"
						- single quotes
							- 'hello'
						- back tick quotes
							- `hello`
							- allow us to embed __variables__ and __expressions__ into a string by wrapping them in `${}`
								```js
									let name = "John";
									alert(`Hello, ${name}`); // Hello, John!
									alert(`the result is ${1 + 2}`); // the result is 3
								```
			- `object` 
				- for more complex data structures.
					- store collections of data
			- `symbol` 
				- to create unique identifiers for objects
			- `null` 
				- for unknown values, "nothing", "empty", or "value unknown"
					- `let age = null;`
					- a standalone type that has a single value `null`.
			- `undefined`
				- for unassigned values, "value is not assigned"
				- a standalone type that has a single value `undefined`.
				- if a variable is declared, but not assigned, then its value is `undefined`
					```js
						let age;
						alert(age); // shows "undefined"
						
						let age = undefined; // not recommended
						let age = null // recommended
					```
		- `typeof` operator 
			- one value purpose
				- allows us to check which data type is stored in a variable
			- for object data types such `Array, Object, Map, Set` use:
				- `instanceof` keyword
					- proper way to check what sort of Object we are using
			- two ways:
				- `typeof x` 
				- `typeof(x)`
			- returns a string with the name of the type, like "string"
			- for `null` returns "object"
				- this is an error in the language, `null` is not actually an object.
	- [Interaction: alert, prompt, confirm](https://javascript.info/alert-prompt-confirm)
		- deadline.
	- [Type Conversions](https://javascript.info/type-conversions)
	- [Basic operators, maths](https://javascript.info/operators)
	- [Comparisons](https://javascript.info/comparison)
	- [Conditional branching: if, '?'](https://javascript.info/ifelse)
	- [Logical operators](https://javascript.info/logical-operators)
	- [Nullish coalescing operator '??'](https://javascript.info/nullish-coalescing-operator)
	- [Loops: while and for](https://javascript.info/while-for)
	- [The "switch" statement](https://javascript.info/switch)
	- [Functions](https://javascript.info/function-basics)
	- [Function expressions](https://javascript.info/function-expressions)
	- [Arrow functions, the basics](https://javascript.info/arrow-functions-basics)
	- [JavaScript specials](https://javascript.info/javascript-specials)
- [Code quality](https://javascript.info/code-quality)




[An introduction](https://javascript.info/getting-started)

[An Introduction to JavaScript](https://javascript.info/intro)
 https://www.wikiwand.com/en/Ajax_(programming) #researchlater 
 https://www.wikiwand.com/en/Comet_(programming) #researchlater 
 
ECMAScript Wikipedia
 https://www.google.com/search?q=javascript+code+name+engines&client=ubuntu&hs=HGJ&channel=fs&source=lnms&tbm=isch&sa=X&ved=2ahUKEwjZ8arKvunrAhU2mnIEHWrvDI8Q_AUoAXoECBAQAw&biw=960&bih=942#imgrc=2C59GwQe26t7gM #researchlater 
 
different version of JavaScript on Wikipedia #researchlater 

 _JavaScript_ was initially created to “make web pages alive”.
The programs in this language are called _scripts_. 
They can be written right in a web page’s HTML and run automatically as the page loads.
 Scripts are provided and executed as plain text. They don’t need special preparation or compilation to run.
 
Why is it called JavaScript?
When JavaScript was created, it initially had another name: “LiveScript”. 

But Java was very popular at that time, so it was decided that positioning a new language as a “younger brother” of Java would help.
Where can JavaScript be executed?

Today, JavaScript can execute (3 locations)
in the browser, on the server, or any device that has a special program called [the JavaScript engine](https://en.wikipedia.org/wiki/JavaScript_engine).

Different run-time engines have different code names:
	V8
	Google Chrome
	Microsoft Edge
	Spider Monkey
	Mozilla Firefox
	JavaScriptCore
	Apple Safari
	Chakra
	Internet Explorer
