# JavaScript
This repository contains a collection of daily JavaScript coding questions or concepts along with their solutions.<br>
And my daily learnings .

In the problem folder, you will find different questions of JavaScript Solved with Questions attached .

<h3>JavaScript Concepts</h3>
<ul>

<li>Implicit Type Coercion</li>
<p>Implicit type coercion in javascript is the automatic conversion of value from one data type to another. It takes place when the operands of an expression are of different data types.</p>
<ul>
	<li>String coercion</li>
	<p>String coercion takes place while using the ‘ + ‘ operator. When a number is added to a string, the number type is always converted to the string type</p>

```javascript
 var x = 3;
 var y = "3";
x + y // Returns "33" 
  ```
<p>When JavaScript sees that the operands of the expression x + y are of different types ( one being a number type and the other being a string type ), it converts the number type to the string type and then performs the operation. Since after conversion, both the variables are of string type, the ‘ + ‘ operator outputs the concatenated string “33” in the first example and “24Hello” in the second example.</p>
<p> ‘ + ‘ operator when used to add two numbers, outputs a number. The same ‘ + ‘ operator when used to add two strings, outputs the concatenated string:</p>

```javascript

var name = "Riya";
var surname = " Kumari";
name + surname     // Returns "Riya Kumari" 
```

<p> Type coercion also takes place when using the ‘ - ‘ operator, but the difference while using ‘ - ‘ operator is that, a string is converted to a number and then subtraction takes place.</p>

```javascript
var x = 3;
Var y = "3";
x - y    //Returns 0 since the variable y (string type) is converted to a number type
```
</ul>


<li>IIFE</li>
<p>An IIFE (Immediately Invoked Function Expression) is a JavaScript function that runs as soon as it is defined</p>

```javascript
	// Regular Function.
	function Greet() {
		console.log("Welcome to the Readme.md");
	};
	// Execution of Regular Function.
	Greet();

	// IIFE creation and execution.
	(function() {
		console.log("Welcome to Readme.md!");
	})();


```
<ul>
	<li>IIFEs have their own scope i.e. the variables you declare in the Function Expression will not be available outside the function.</li>
        <li>Similarly to other functions IIFEs can also be named or anonymous, but even if an IIFE does have a name it is impossible to refer/invoke it.</li>
        <li>IIFEs can also have parameters.</li>
</ul>
<ul>
	<br>
	<b>Use Cases Of IIFE</b>
	<li>Avoid polluting the global namespace </li>
	<li>To create closures</li>
	<li>Avoid conflict of variable names between libraries and programs.</li>
</ul>










<!--   1 -->
  <li><b>Callback Function</b></li><p>A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action.</p>

  
```javascript

    function modifyArray(arr, callback) {
    arr.push(100);
    callback();
  }
  
  var arr = [1, 2, 3, 4, 5];
  
  modifyArray(arr, function() {
    console.log("array has been modified", arr);
  });

  ```

<!--   2-->

<li><b>Slice</b></li>
<!-- <p>The slice() method returns a <b>shallow copy</b>(<span style="color:orange;">A shallow copy of an arrays or object is one where they both have the same reference in memory. That means that if you change the shallow copy, it may or may not change the original copy.</span>) of a portion of an array into a new array object selected from start to end (end not included) where start and end represent the index of items in that array. The original array will not be modified.</p> -->
<p>The Javascript arr.slice() method returns a new array containing a portion of the array on which it is implemented. The original remains unchanged.</p>

```javascript

const a = [1,2,3];
let b = a.slice(0,3);
b[1] = 4;
console.log(b[1]);
console.log(a[1]);

```

<p>To know more about working of Slice method refer these: </p>
<ul>
  <li>
    <a href="https://dev.to/smpnjn/javascript-shallow-copy-what-is-a-shallow-copy-1pc5#:~:text=What%20is%20a%20shallow%20copy%20in%20JavaScript%3F,change%20the%20original%20copy%20too.">More about slice and shallow copy</a>
  </li>
  <li>
    <a href="https://www.freecodecamp.org/news/copying-stuff-in-javascript-how-to-differentiate-between-deep-and-shallow-copies-b6d8c1ef09cd/">https://www.freecodecamp.org/news/copying-stuff-in-javascript</a>
  </li>

  
</ul>
<br>





<!-- 3 -->

<li><b>Higher Order Functions</b></li>
<p>Functions that operate on other functions, either by taking them as arguments or by returning them, are called higher-order functions.</p>

```javascript

function higherOrder(fn) {
  fn();
}
   
higherOrder(function() { console.log("Hello world") });  

```

```javascript
function higherOrder2() {
  return function() {
    return "Do something";
  }
}      
var x = higherOrder2();
x()   // Returns "Do something"
```

<p>To know more about working of HOF refer these: </p>
<ul>
  <li>
    <a href="https://www.freecodecamp.org/news/higher-order-functions-in-javascript-explained/">https://www.freecodecamp.org/news/higher-order-functions-in-javascript-explained</a>
  </li>
  
</ul>

<br>

<!-- 4 -->


<li><b>Currying</b></li>
<p>It is a technique in functional programming, that transforms the function of multiple arguments into several functions of a single argument in sequence. It is a method that takes one argument at a time and returns a new function that expects the next argument.</p>

```javascript

function add (a) {
  return function(b){
    return a + b;
  }
}

add(3)(4)
```
<ul>Why is currying useful in JavaScript?
  <li>It helps us to create a higher-order function</li>
  <li>It reduces the chances of error in our function by dividing it into multiple smaller functions that can handle one responsibility.</li>
  <li>It helps us to avoid passing the same variable multiple times</li>
  <li>It is very useful in building modular and reusable code</li>
</ul>
<br>
<li>Call , Apply , Bind</li>
<ul>
  <li>Call</li>
  <p>It’s a predefined method in javascript.This method invokes a method (function) by specifying the owner object.<b>call()</b> method allows an object to use the method (function) of another object.</p>
  <p>This Concept is called <b>Function Borrowing</b></p>


  ```javascript

var person = {
  age: 23,
  getAge: function(){
    return this.age;
  }
}        
var person2 = {age:  54};
person.getAge.call(person2);      
// Returns 54

```

<p>call() accepts arguments:</p>

```javascript

function saySomething(message){
  return this.name + " is " + message;
}     
var person4 = {name:  "Riya"};     
saySomething.call(person4, "awesome");
// Returns "Riya is awesome"   

```
<h5>After looking at the above codes we can say that in layperson's terms, it helps you replace the value of <b>this</b> inside a function with whatever value you want.</h5>
<p><b>Syntax</b></p>

```javascript
call(objectInstance)
call(objectInstance, arg1, /* …, */ argN)
```

<li>Apply</li>
<p>Apply is very similar to the call function. The only difference is that call() method takes arguments separately whereas, apply() method takes arguments as an <b>array</b>.</p>


```javascript
  function saySomething(message){
  return this.name + " is " + message;
}        
var person4 = {name:  "Riya"};
saySomething.apply(person4, ["awesome"]);
```

<p>The best part about apply is we don’t need to take care of the number of arguments that are passed to the invoking function. Because of its dynamic and versatile nature, we can use it in complicated situations.</p>

<li>Bind</li>
<p>This method returns a new function, where the value of “this” keyword will be bound to the owner object, which is provided as a parameter.</p>

```javascript
function saySomething(message){
  return this.name + " is " + message;
}     
var person4 = {name:  "Riya"};     
let Greet = saySomething.bind(person4, "awesome");
console.log(Greet());
```


<p>The only difference between the call and bind is that it gives you copy of the function which can be invoked later rather than directly invoking it .</p>
</ul>

# <li>Optional chaining (?.)</li>
<p>The ?. operator is like the . chaining operator, except that instead of causing an error if a reference is nullish (null or  undefined), the expression short-circuits with a return value of undefined. When used with function calls, it returns undefined if the given function does not exist.
The <b>optional chaining (?.)</b> operator accesses an object's property or calls a function. If the object accessed or function called using this operator is undefined or null, the expression short circuits and evaluates to undefined instead of throwing an error.</p>


</ul>
