---
tags: cssi, javascript
level: 1
languages: javascript
---
#Functions
After the lesson, you'll be able to understand:
+ What is a function
+ How and when to call a function
+ function syntax and structure - NICO
+ passing parameters to a function
+ returning a value in a function -what does that mean?
+ Using variables within a function
+ Using conditional statements inside of a function
+ Inputs and outputs

## Functions in Javascript
Like variables, you are probably familiar with functions from math class. Functions in code are similar to those in class - they take some data and transform it in some way. Those transformations are really useful to us - they're the work that we want the computer to do.

Writing functions lets us package code into blocks that we can reuse. This will prevent us from writing the same code over and over again. Secretly, we've been using a handful functions already - all of the operations that we've learned are functions that are built into javascript. This lesson will show how we can write our own functions, and maybe give us some insight into how the other functions we use work!

In programming, a function holds a set of actions that will run when we call that function. This helps us control the flow of our program and allows us to repeat a set of actions multiple times.

## Example
Imagine you are a cashier. Every time a customer checks out, you need to

1. Add the price of all the items
2. Apply any coupons
3. Calculate and add the tax

If you were using the javascript console, this set of actions might look like:
```
> 33 + 19 // add the prices of the items
52
> 52 * .15 // find the value of the 15% off coupon
7.8
> 52 - 7.8 // subtract the coupon from the price
44.2
> 44.2 * .06 // find the sales tax
2.652
> 44.2 + 2.652 // add the sales tax
46.85
```
That process takes time and a lot of steps, and if you do it hundreds of times each day, you are bound to make some mistakes. Instead, we can write a function that will do all the work for us:

```
function checkout(item1, item2, coupon){
    var subtotal = item1 + item2;
    subtotal -= subtotal*coupon;
    total = subtotal + subtotal*.06;
    console.log(total)
};
```
And then we can use the function like this:
```
> checkout(33,19,.15)
46.85
> checkout(12,9.99,.05)
22.14
```
So much easier than going through all of those steps every time!

##Declaration
A function is a set of instructions that we write out once and reuse over and over. We call creating a new set of instructions **declaring a function**.

The syntax for writing JS functions is very specific. It looks like this:

```
function name() {
    // instructions here
};
```
The instructions go inside the curly braces. Let’s add some instructions inside of a function in our my_script.js file and reload our html page to run the program.

```
function goGetLunch() {
    console.log("Close Computer");
    console.log("Stand up");
    console.log("Walk out the door")
};
```

Nothing happened. Why is that? We declared our function - which is like adding the goGetLunch function to the computer’s dictionary - but we didn’t actually tell the computer to execute the function.

## Calling a function
We use a function with its name. The name for this is calling the function. In javascript, we write it like this:

```
goGetLunch();
```

This is the equivalent of telling the computer - do those steps in the goGetLunch function. The parentheses are necessary to let the browser know that we want to run the instructions.

Our instructions are pretty generic right now. What if we wanted to direct them towards a specific student? If a student's name was Joe, we'd have a step that says “hey, Joe”.

##Passing in Parameters
Parameters allow you to pass values into functions - they help make functions reusable. Instead of using the same values every time you use the function, you can use the same set of instructions on different data. Instead of having to write a new goGetLunch function for each student, we can write it once, and then use it on any student we want.
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

## Return Values
So far, the functions we've made have had side effects - printing something out to the console - but they haven't passed results back. When we used the addition function, it didn't just print something - we could store the result in a variable.

To pass results, we **return** a value.
```
function addTwice(x,y){
    return x+x+y+y;
}
```
When we have a return statement, we leave the function and give back that value. By saying return we’re telling the function give us back the answer.

```
> var y = addTwice(3,5);
> console.log(y)
16
```
This is important because most of the time functions don’t live all alone by themselves - they rely on other functions!

##N.I.C.O
We can break down the creation of functions into four things that every function has:
+ **Name** - Decide an appropriate name for the function
+ **Input (Parameters)**  - Figure out what inputs, if any, are needed to accomplish what the name describes
+ **Code** - Put the code inside the function to be run when it is called
+ **Output** - A value that the function can return though it can be undefined

Functions are the building block of any developer. They let you create little machines that you can use and re-use from other parts of your code. This can make life a lot easier and save a ton of typing!
