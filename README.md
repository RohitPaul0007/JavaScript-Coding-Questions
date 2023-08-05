# JavaScript
This repository contains a collection of daily JavaScript coding questions or concepts along with their solutions.

<h3>JavaScript Concepts</h3>
<ul>
  <li>Callback Function</li><p>A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action.</p>

  
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


<li>Slice</li>
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


<li>Currying</li>
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

</ul>
