### Closures in JavaScript
For more information please read the original article on [**stackoverflow**](http://stackoverflow.com/questions/111102/how-do-javascript-closures-work)

* Ability to reference a specific instance of local variables in an enclosing function is called **Closure**. Simply meaning, a function that _'closes over'_ some local variables.
* A **closure** is a local variable for a function - kept alive after the function has returned.

```
function greet(name){
  return function(msg){
    return msg + " " + name;
  };
}
var greeting = greet("Quincy");
greeting("Hello");// "Hello Quincy"
```

In JavaScript, you can think of a function reference variable as having both a pointer to a function, as well as a hidden pointer to a closure.

The above code has a closure because the anonymous function ```function(msg){return msg +" "+name;``` is _declared_ inside of another function, ```greet()``` in this example. In JavaScript, if you are using a function keyword inside another function, you are creating a **closure.**

In JavaScript, if you declare a function within a function, the local variable will remain accessible after returning from the function you called. 

In **closures**, local variable are not copied - they are kept by reference.
