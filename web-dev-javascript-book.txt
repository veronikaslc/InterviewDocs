J2EE and JSP have been refined into JEE and JSF. Projects such as Spring provide additional capabilities geared toward server-side development. 

Ajax == “asynchronous JavaScript and XML,”

AJAX calls cannot be sent to a different domain than the domain from which the HTML page making the AJAX calls is loaded. 


JavaScript Object Notation (JSON) - is a lightweight data format

XML is used for exchanging data, HTML is not.(???)

The core JavaScript language needs to be understood in relation to two distinct APIs: the Browser Object Model (BOM) and the Document Object Model (DOM). The BOM consists of a window and its child objects: navigator, history, screen, location, and document. The document object is the root node of the DOM, a hierarchical tree representation of the contents of the page itself.

• JavaScript has function-level scope rather than block-level scope like other C-like languages. Blocks such as those used by if statements and other language constructs do not create a new scope.

• In JavaScript, null, undefined, and a few other values evaluate to false. 

• The if conditional expression is !x. The exclamation point is a NOT logical operator. Therefore, if x is undefined (or null), this expression if (!x) evaluates to true.

• The var keyword is used to define a local variable. Variables declared without it are global. This definition results in the variable being associated with the scope of the function. 

• A function is being created and assigned to a variable named y. This is particularly strange to Java programmers who deal with methods that only exist attached to a class or object instance. This syntax calls attention to the functional nature of JavaScript.

• functions are fundamental units in JavaScript and are in fact “first-class.”

Closures are functions that have access to variables from another function’s scope. A closure occurs when a function returns an inner function. 

JavaScript is an interpreted language. No compilation is necessary.

In Java, an object is created as an instance of a defined class. In JavaScript, an object is simply a collection of properties.

object is an “unordered collection of properties each of which contains a primitive value, object, or function.”

The Document Object Model (DOM) is an application programming interface (API) for XML that
was extended for use in HTML. The DOM maps out an entire page as a hierarchy of nodes.

JavaScript is a scripting language designed to interact with web pages and is made up of the
following three distinct parts:
-ECMAScript, which is defi ned in ECMA-262 and provides the core functionality
-The Document Object Model (DOM), which provides methods and interfaces for working
with the content of a web page
-The Browser Object Model (BOM), which provides methods and interfaces for interacting
with the browser

the following code causes an error when loaded into a browser: alert(“</script>”); This problem can be avoided easily by escaping the “/” character alert(“<\/script>”);
It’s important to note that a <script> element using the src attribute should not include additional
JavaScript code between the <script> and </script> tags. If both are provided, the script fi le is
downloaded and executed while the inline code is ignored.

However, including all JavaScript files in the <head> of a document means that all of the JavaScript code must be downloaded, parsed, and interpreted before the page begins rendering (rendering begins when the browser receives the opening <body> tag). For pages that require a lot of JavaScript code, this can cause a noticeable delay in page rendering, during which time the browser will be completely blank. Modern web applications typically include all JavaScript references in the <body> element, after the page content.




an attribute named defer for the <script> element, means a script will not be executed until after the browser has received the closing </html> tag. The defer attribute is supported only for external script fi les. This was a clarification made in HTML5.

Also similar to defer, async applies only to external scripts and signals the browser to begin downloading the file immediately. Unlike defer, scripts marked as async are not guaranteed to execute in the order in which they are specified. so it’s important that there are no dependencies between them. Also thats why it’s recommended that asynchronous scripts not modify the DOM as they are loading.

<noscript> element was created to provide alternate content for browsers without JavaScript of with one turned off.

Everything is case-sensitive; (sucks!)

“use strict”; - Strict mode is a different parsing and execution model for JavaScript, when errors are thrown for unsafe activities; this is a pragma that tells supporting JavaScript engines to change into strict mode.

It is possible to define a variable globally by simply omitting the 'var' operator! (by-by closure problem!)
In JavaScript the variable declaration adds a variable into the current execution context ( no block-level scopes!!). There are only two primary types of execution contexts, global and function. When a variable is declared using var, it is automatically added to the most immediate context available. In a function, the most immediate one is the function’s local context; in a 'with' statement, the most immediate is the function context. If a variable is initialized without first being declared (without 'var'), it gets added to the global context automatically. (( If the variable is declared within the {} it can still be accessible, unless {} isn't a function. (!!) - unlike to the block-level scopes languages like C.))
if (true) {
var color = “blue”;
}
alert(color); //”blue” - executes without a problem!

In strict mode, initializing variables without declaration causes an error.

Primitive values are of a fixed size and so are stored in memory on the stack. Reference values are objects and are stored in memory on the heap.


Values that should be primitive types should be checked using typeof, and values that should be objects should be checked using instanceof. The typeof operator determines a value’s primitive type, whereas the instanceof operator is used to determine the reference type of a value.

There are five simple data types (also called primitive types) in ECMAScript: Undefined, Null, Boolean, Number, and String. There is also one complex data type called Object, which is an unordered list of name-value pairs. Because there is no way to define your own data types in ECMAScript, all values can be represented as one of these six.
typeof operator:
[result:string] = typeof [variable] 
alert(typeof 'a'); //”string”
alert(typeof null); //'object'
alert(typeof 95); //”number”

instanceof operator:
[result:boolean] = [variable] instanceof [constructor]
alert(person instanceof Object); //is the variable person an Object?
alert(colors instanceof Array); //is the variable colors an Array?
alert(pattern instanceof RegExp); //is the variable pattern a RegExp?

(Weird!!) The typeof operator returns “undefined” when called on an uninitialized variable, but it also returns “undefined” when called on an undeclared variable,

The value undefined is a derivative of null, so ECMA-262 defi nes them to be superfi cially equal as follows:
alert(null == undefined); //true

alert(NaN == NaN); //false

Number() - casting function. When applied to Boolean values, true and false get converted into 1 and 0, respectively.

\n    New line

--a; When using either a prefi x increment or a prefix decrement, the variable’s value is changed before the statement is evaluated. When used on a string that is a valid representation of a number, convert to a number and apply the change. The variable is changed from a string to a number. (sic!) 

The unary minus operator’s primary use is to negate a numeric value, such as converting 1 into –1.
var num = 25;
num = -num; //becomes -25

The bitwise NOT is represented by a tilde (~) and simply returns the one’s complement of the number. (This is the end effect of the bitwise NOT: it negates the number and subtracts 1. But bitwise operation is much faster)
var num1 = 25;     //binary 00000000000000000000000000011001
var num2 = ~num1; //binary 11111111111111111111111111100110
alert(num2);     //-26

The bitwise XOR operator is represented by a caret (^), it returns 1 only when exactly one bit has a value of 1 (if both bits contain 1, it returns 0). 
var result = 25 ^ 3;

The left shift is represented by two less-than signs (<<) and shifts all bits in a number to the left
by the number of positions given.
var newValue = 2 << 5; // //equal to binary 1000000 which is decimal 64

The logical NOT (!) operator can also be used to convert a value into its Boolean equivalent.

By using two NOT (!!) operators in a row, you can effectively simulate the behavior of the Boolean() casting function.
alert(!!NaN); //false

Logical AND (&&) v.s. Bitwise AND (&)

The logical AND operator is a short-circuited operation, meaning that if the first operand determines the result, the second operand is never evaluated. Same with OR.
var found = false;
var result = (found && someUndeclaredVariable); //no error
alert(result); 					//works

If either of the operands for a multiplication operation isn’t a number, it is converted to a number behind the scenes using the Number() casting function. This means that an empty string is treated as 0, and the Boolean value of true is treated as 1. Same is with substraction, division, modulus.

If Infinity is multiplied by 0, the result is NaN. (Weird!)

If Infinity is divided by Infinity, the result is NaN.

The modulus (remainder) operator is represented by a percent sign (%)
var result = 26 % 5; //equal to 1

'<' relational operator, If the operands are strings, compare the character codes of each corresponding character in
the string.

Use equal (==) and not equal to perform conversion before comparison, and identically equal (===) and not identically equal to perform comparison without conversion:
alert(5 == “5”); //true, the equal operator first converts the string “5” into the number 5
alert(5 === “5”); //false
alert(1 == true); //true
alert(1 === true); //false

Statements such as 'if' automatically convert any value into a Boolean before determining the next step. 

for (;;) { //infinite loop
doSomething();
}

Iterative on enumerated stuff:

for (var propName in window) {
document.write(propName);
}

The switch statement compares values using the identically equal operator (===)
switch (expression) {
case value: statement
break;
case value: statement
break;
...
default: statement
}


No Overloading - last declares shit takes over lol

it is best to rely only on the message property for cross-browser compatibility.
```
try {
window.someNonexistentFunction();
} catch (error){
alert(error.message);
}
```
The optional finally clause of the try-catch statement always runs its code no matter what. The function returns
0 when called no matter what. If the finally clause were removed, the function would return 2.
```
function testFinally(){
try {
	return 2;
} catch (error){
	return 1;
} finally {
	return 0;
}
}
```



Example of custom error handling
```
if (!(values instanceof Array)){
throw new Error(“process(): Argument must be an array.”);
}
```
The best way to think about the difference between throwing errors and catching errors is this: you should catch errors only if you know exactly what to do next. The purpose of catching an error is to prevent the browser from responding in its default manner; the purpose of throwing an error is to provide information about why an error occurred.

You can prevent the default browser error reporting by returning false, as shown here. By returning false, this function effectively becomes a try-catch statement for the entire document, capturing all unhandled runtime errors.
```
window.onerror = function(message, url, line){  //the onerror event handler
alert(message);
return false;
};
```
There is a signifi cant difference between the way browsers handle errors using this event. When the error event occurs in Internet Explorer, normal code execution continues; all variables and data are retained and remain accessible from within the onerror event handler. In Firefox, however, normal code execution ends, and all variables and data that existed prior to the error occurring are destroyed, making it diffi cult to truly evaluate the error.

Images also support an error event. Any time the URL in an image’s src attribute doesn’t return a recognized image format, the error event fi res. In this example, an alert is displayed when the image fails to load.
```
var image = new Image();
EventUtil.addHandler(image, “load”, function(event){
alert(“Image loaded!”);
});
EventUtil.addHandler(image, “error”, function(event){
alert(“Image not loaded!”);
});
image.src = “smilex.gif”; //doesn’t exist
```
To set up a JavaScript error-logging system, you’ll first need a page or entry point on the server that can handle the error data. The page need not do anything more than take data from the query string and save it to an error log. This page can then be used with code such as the following:
function logError(sev, msg){
var img = new Image();
img.src = “log.php?sev=” + encodeURIComponent(sev) + “&msg=” +
encodeURIComponent(msg);
}
An Image object (!!!) is used to send the request because of its flexibility, as the Image object is available in all browsers, even those that don’t support the XMLHttpRequest object. Cross-domain restrictions don’t apply. Often there is one server responsible for handling error logging from multiple servers, and XMLHttpRequest would not work in that situation. There’s less of a chance that an error will occur in the process of logging the eror.

error(message) — Logs an error message to the console
info(message) — Logs an informational message to the console
log(message) — Logs a general message to the console
warn(message) — Logs a warning message to the console

Another option is to use LiveConnect, which is the ability to run Java code from JavaScript (sick!). Firefox, Safari, and Opera all support LiveConnect and may interact with a Java console. It’s possible to write messages to the Java console using JavaScript via the following code:
java.lang.System.out.println(“Your message”);

Determining the type of console :
function log(message){
if (typeof console == “object”){
console.log(message);
} else if (typeof opera == “object”){
opera.postError(message);
} else if (typeof java == “object” && typeof java.lang == “object”){
java.lang.System.out.println(message);
}
}
But the log() function detects which JavaScript console interface is available and uses the appropriate one.

Logging messages to the JavaScript console is helpful in debugging code, but all messages should be removed when code goes to production.

Logging Messages to the Page:
function log(message){
var console = document.getElementById(“debuginfo”);
if (console === null){
console = document.createElement(“div”);
console.id = “debuginfo”;
console.style.background = “#dedede”;
console.style.border = “1px solid silver”;
console.style.padding = “5px”;
console.style.width = “400px”;
console.style.position = “absolute”;
console.style.right = “0px”;
console.style.top = “0px”;
document.body.appendChild(console);
}
console.innerHTML += “<p>” + message + “</p>”;
}

When a reference value is assigned from one variable to another, the value stored on the variable object is also copied into the location for the new variable. The difference is that this value is actually a pointer to an object stored on the heap.
var obj1 = new Object();
var obj2 = obj1;
obj1.name = “Nicholas”;
alert(obj2.name); //”Nicholas”


JavaScript is a garbage-collected language, meaning that the execution environment is responsible for managing the memory required during code execution. It’s possible, though not recommended, to trigger the garbage-collection process in some browsers. In Internet Explorer, the window.CollectGarbage() method causes garbage collection to occur immediately. In Opera 7 and higher, calling window.opera.collect() initiates the garbage-collection process.

When data is no longer necessary, it’s best to set the value to null, freeing up the reference — this is called dereferencing the value. This advice applies mostly to global values and properties of global objects.

Constructor pttern of object creation:
function Person(name, age, job){
this.name = name;
this.age = age;
this.job = job;
this.sayName = function(){
alert(this.name);
};
}
var person1 = new Person(“Nicholas”, 29, “Software Engineer”);
var person2 = new Person(“Greg”, 27, “Doctor”);
alert(person2 instanceof Person); //true (!!)

Major rendering engines: Internet Explorer, Gecko, WebKit, KHTML, and Opera.

The this object is bound at runtime based on the context in which a function is executed: when used inside global functions,
this is equal to window in nonstrict mode and undefined in strict mode, whereas this is equal to the object when called as an object method. Anonymous functions are not bound to an object in this context, meaning the this object points to window unless executing in strict mode (where this is undefined).
