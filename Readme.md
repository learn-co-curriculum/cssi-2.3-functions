---
tags: cssi, javascript
level: 1
languages: javascript
---
#Functions
After the lesson, you'll be able to understand:
+ What is a function
+ Declaring a function
+ How to call a function
+ Passing parameters to a function
+ Returning values
+ NICO


## What is a function?
A function holds a set of actions that will run when we call that function. This helps us control the flow of our program and allows us to repeat a set of actions multiple times.

Writing functions lets us package code into blocks that we can reuse. This will prevent us from writing the same code over and over again. 

Imagine you are a cashier. Every time a customer checks out, you need to

1. Add the price of all the items
2. Apply any coupons
3. Print out the total

If you were using the JavaScript console, this set of actions might look like:
```
> 33 + 19 // add the prices of the items
52
> 52 * .15 // find the value of the 15% off coupon
7.8
> 52 - 7.8 // subtract the coupon from the price
44.2
```
That process takes time, and if you do it hundreds of times each day, you are bound to make some mistakes. Instead, we can write a function that will do all the work for us:

```
function checkout(item1, item2, coupon){
  var subtotal = item1 + item2;
  var total = subtotal - subtotal*coupon;
  console.log(total);
};
```
And then we can use the function like this:
```
> checkout(33,19,.15)
44.2
> checkout(12,9.99,.05)
20.89
```


##Declaration
A function is a set of instructions that we write out once and reuse over and over. We call creating a new set of instructions **declaring a function**.

The syntax for writing JS functions is very specific. It looks like this:

```
function name() {
    // instructions here
};
```
The instructions go inside the curly braces. 

```
function goGetLunch() {
    console.log("Close Computer");
    console.log("Stand up");
    console.log("Walk out the door")
};
```

## Calling a function
We use a function with its name. The name for this is calling the function. 

```
goGetLunch();
```
This is the equivalent of telling the computer - do those steps in the goGetLunch function. The parentheses are necessary to let the browser know that we want to run the instructions.

##Passing in Parameters
Parameters allow you to pass values into functions - they help make functions reusable. Instead of using the same values every time you use the function, you can use the same set of instructions on different data. 
```
function goGetLunch(student) { 
  console.log('hey, ' + student);
  console.log('close your computer');
  console.log('stand up');
  console.log('walk out the door');
}
```
Then we can call it like this:
```
goGetLunch("Joe");
goGetLunch("Jill");
goGetLunch("Josie");
```
When you call a function like this and pass values to it, those values are called arguments. We can reuse this function, and change the name of the student we address by adding a different student argument.

In the above example, `student` in the function definition is the parameter. But when we actually call the function with a student's name, the strings "Joe", "Jill", "Josie" are arguments.

## Return Values
So far, the functions we've made have had side effects - printing something out to the console - but they haven't passed results back. When we used the addition function, it didn't just print something - we could store the result in a variable.

To pass results, we **return** a value.
```
function addTwice(x,y){
    return x+x+y+y;
}
```
When we have a return statement, we leave the function and give back that value. By saying return we’re asking the function to give us back the answer.

```
> var y = addTwice(3,5);
> console.log(y)
16
```
Most of the time functions don’t live all alone by themselves - they rely on other functions!

##N.I.C.O
We can break down the creation of functions into four things that every function has:
+ **Name** - Decide an appropriate name for the function
+ **Input (Parameters)**  - Figure out what inputs, if any, are needed to accomplish what the name describes
+ **Code** - Put the code inside the function to be run when it is called
+ **Output** - A value that the function can return though it can be undefined

Functions are the building blocks of any developer. They let you create little machines that you can use and re-use in other parts of your code. This can make life a lot easier and save a ton of typing!
