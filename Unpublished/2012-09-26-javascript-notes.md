---
Date: 2012-09-26 11:45
Title: Javascript Notes
Published: false
---


####Data types

#####numbers
12342, 3324.2
#####strings
"what"

#####boolean

true or false

	> Greater than
	< Less than
	<= Less than or equal to
	>= Greater than or equal to
	=== Equal to
	
	
	
####Statement
	if (this condition is true) 
	{
    	// do this code
	}
	else // "otherwise"
	{
    	// do this code instead
	}
{{more}}	
	
	
####Math

	1. ( ): control order of operations
	2. * and /: multiplication and division
	3. - and +: subtraction and addition
	
#####Modulo
	23 % 10 evaluates to 3
	
#####Substrings
	"some word".substring(x, y)
	
####Variables
	var varName = data type;
	
####For loop

	for (var i=1; i<=5; i++) 
	{
  	// Everything in the code block starting with '{' 	and
   	// ending with '}' will run exactly five times.
    console.log(i);
	}
	
####Function
	var hello = function (parameter) {
  	// Print hello on the console.
  	console.log("i am saying hello");
	};
	hello(parameter);
	
**Check variable type**

	typeof(x) != 'number'
	
####Switch
	switch(){
	case "":
	console.log("");
	break;
	default:
	console.log("");}
	
####Primitive data types

	1.numbers
	2.string
	3.boolean
	
#####Generate random numbers
	Math.floor(Math.random ( ) * X + 1)
	
####Objects
	var name = {property:value, property:value};
	
	ObjectName.PropertyName or
	ObjectName["PropertyName"]
	
	The keyword this acts as a placeholder, and will refer to whichever object called that method when the method is actually used.
	
#####Constructors
	function Person(name,age) {
    this.name = name;
    this.age = age;
	}
	var bob = new Person("Bob Smith", 30);
	var susan = new Person("Susan Jordan", 25);
	
#####hasOwnProperty
	ObjectName.hasOwnProperty('') = true or false

#####for in loop
	for(var property in dog) {
	console.log(property);
	}

####Class (constructor)
	function Person(name,age) {
    this.name = name;
    this.age = age;
	};

	// Let's make bob again, using our constructor
	var bob = new Person("Bob Smith", 30);
	var susan = new Person("Susan Jordan", 35);
	
#####Class prototype
	className.prototype.newMethod =
	function() {
	statements; 
	};
	
#####Inherit
	subclass.prototype = new Class();
	
#####Private properties
	function Person(first,last,age) {
    this.firstname = first;
    this.lastname = last;
    this.age = age;
    var bankBalance = 7500;
    var returnBalance = function() {
    return bankBalance;
    }
	
	
####Table
	var table = [
    ["Person",  "Age",  "City"],
    ["Sue",     22,     "San Francisco"],
    ["Joe",     45,     "Halifax"]
	];
	
####Arrays
#####adding and removing elements
	myArray.push("some item");
	myArray.splice(starting index, numbers to be removed);
#####array copying
	var b = a.slice(1,3)
	
#####associative arrays
	var myAssoc = {"key1":"val1","key2":"val2"}
	
**confirm("");**

**"".length;**

**prompt("");** for input

**console.log()**: take whatever is inside the parentheses and log it to the console below your code

	console.log(2 * 5) console.log("Hello")