# What I Learned In Week 8 At Code Immersives

&nbsp;

## Break/Continue

Having worked with JavaScript for a long while now, there are times when you will find the need to break out of a loop when a certain condition is met, or just skip the current iteration to the next iteration for one reason or another.

These situations can be solved by using the following statements:

1. break statement
2. continue statement

Break Statement

The break statement is used to terminate a loop and get out of it. Then, the code following the loop code block will be executed next (if any).

It is usually used inside a conditional statement whereby when a condition is met, for one reason or another, it stops the loop and gets out of it. How it is done is by simply writing break.

Syntax:

    break;

Example:

    for (let i = 0; i < 8; i++) {
    if (i === 4) { break; }
    console.log("Iteration i: " + i);
    }

    // Output:
    Iteration i: 0
    Iteration i: 1
    Iteration i: 2
    Iteration i: 3

Without the break statement, the output will typically appear as follow:

    // Output:
    Iteration i: 0
    Iteration i: 1
    Iteration i: 2
    Iteration i: 3
    Iteration i: 4
    Iteration i: 5
    Iteration i: 6
    Iteration i: 7

### The break statement "jumps out" of a loop.

&nbsp;

The continue statement is used to skip an iteration of the loop.

This statement too, can be used in the switch statements.

The continue statement basically breaks one iteration of the loop, if a specified condition is met, and continues with the next iteration of the loop. How it is written is similar to the break statement.

Syntax:

    continue;

Example:

    for (let i = 0; i < 8; i++) {
    if (i === 4) { continue; }
    console.log("Iteration i: " + i);
    }

    // Output:
    Iteration i: 0
    Iteration i: 1
    Iteration i: 2
    Iteration i: 3
    Iteration i: 5
    Iteration i: 6
    Iteration i: 7

Using the example above, we can see that the iteration 4 is skipped because we wrote that when it is 4, we will continue to the next iteration. Thus, its turn is skipped from being printed out.

### The continue statement "jumps over" one iteration in the loop.

&nbsp;

## Switch Statements

The switch statement is used to perform different actions based on different conditions.

Syntax:

    switch(expression) {
    case x:
        // code block
        break;
    case y:
        // code block
        break;
    default:
        // code block
    }

This is how it works:

- The switch expression is evaluated once.
- The value of the expression is compared with the values of each case.
- If there is a match, the associated block of code is executed.
- If there is no match, the default code block is executed.

The switch statement evaluates an expression, matching the expression's value to a case clause, and executes statements associated with that case, as well as statements in cases that follow the matching case.

    const expr = 'Papayas';
    switch (expr) {
    case 'Oranges':
        console.log('Oranges are $0.59 a pound.');
        break;
    case 'Mangoes':
    case 'Papayas':
        console.log('Mangoes and papayas are $2.79 a pound.');
        // expected output: "Mangoes and papayas are $2.79 a pound."
        break;
    default:
        console.log(`Sorry, we are out of ${expr}.`);
    }

    // Log: "Mangoes and papayas are $2.79 a pound."

&nbsp;

## .reduce / .filter / .map

Map, filter and reduce are essentially just some of the most well-known, easy to use, higher-order functions that run provided callback on each element of an array.

Map, reduce, and filter are all array methods in JavaScript. Each one will iterate over an array and perform a transformation or computation. Each will return a new array based on the result of the function.

&nbsp;

The .map() method is used for creating a new array from an existing one, applying a function to each one of the elements of the first array.

syntax:

    var new_array = arr.map(function callback(element, index, array) {
    // Return value for new_array
    }[, thisArg])

In the following example, odd numbers are "filtered" out, leaving only even numbers.

    const numbers = [1, 2, 3, 4];
    const doubled = numbers.map(item => item * 2);
    console.log(doubled); // [2, 4, 6, 8]

&nbsp;

The .filter() method takes each element in an array and it applies a conditional statement against it. If this conditional returns true, the element gets pushed to the output array. If the condition returns false, the element does not get pushed to the output array.

syntax:

    var new_array = arr.filter(function callback(element, index, array) {
        // Return true or false
    }[, thisArg])

In the following example, odd numbers are "filtered" out, leaving only even numbers.

    const numbers = [1, 2, 3, 4];
    const evens = numbers.filter(item => item % 2 === 0);
    console.log(evens); // [2, 4]

In the next example, filter() is used to get all the students whose grades are greater than or equal to 90.

    const students = [
    { name: 'Quincy', grade: 96 },
    { name: 'Jason', grade: 84 },
    { name: 'Alexis', grade: 100 },
    { name: 'Sam', grade: 65 },
    { name: 'Katie', grade: 90 }
    ];

    const studentGrades = students.filter(student => student.grade >= 90);
    return studentGrades; // [ { name: 'Quincy', grade: 96 }, { name: 'Alexis', grade: 100 }, { name: 'Katie', grade: 90 } ]

&nbsp;

The reduce() method reduces an array of values down to just one value. To get the output value, it runs a reducer function on each element of the array.

syntax:

    arr.reduce(callback[, initialValue])

The callback argument is a function that will be called once for every item in the array. This function takes four arguments, but often only the first two are used.

- accumulator - the returned value of the previous iteration
- currentValue - the current item in the array
- index - the index of the current item
- array - the original array on which reduce was called
- The initialValue argument is optional. If provided, it will be used as the initial accumulator value in the first call to the callback function.

The following example adds every number together in an array of numbers.

    const numbers = [1, 2, 3, 4];
    const sum = numbers.reduce(function (result, item) {
    return result + item;
    }, 0);
    console.log(sum); // 10

&nbsp;

## .split() / .join()

The split() method splits a String object into an array of strings by separating the string into substrings.

    let a = "asdasd|dasd|rttewrtert";

    let b = a.split('|');
    // ["asdasd", "dasd", "rttewrtert"]

The join() method joins all elements of an array into a string.

    let a = ["dasd", "rttewrtert"];

    let c = c.join('');
    // dasdrttewrtert

&nbsp;

## Objects

In JavaScript, almost "everything" is an object.

- Booleans can be objects (if defined with the new keyword)
- Numbers can be objects (if defined with the new keyword)
- Strings can be objects (if defined with the new keyword)
- Dates are always objects
- Maths are always objects
- Regular expressions are always objects
- Arrays are always objects
- Functions are always objects
- Objects are always objects

All JavaScript values, except primitives, are objects.

JavaScript Primitives

A primitive value is a value that has no properties or methods.

A primitive data type is data that has a primitive value.

JavaScript defines 5 types of primitive data types:

- string
- number
- boolean
- null
- undefined

Objects are variables too. But objects can contain many values.

The values are written as name : value pairs (name and value separated by a colon).

    let person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};

The named values, in JavaScript objects, are called properties.

- **Property** Value
- **firstName** John
- **lastName** Doe
- **age** 50
- **eyeColor** blue

&nbsp;

## Dot Notation, Bracket notation

There are two ways to access properties on an object:

1.  Dot Notation
2.  Bracket Notation

Dot notation is used most frequently.

This is the syntax:

    objectName.propertyName;

Here’s the syntax:

    objectName["propertyName"].


    let obj = {
    cat: 'meow',
    dog: 'woof'
    };
    let sound = obj.cat;
    console.log(sound);
    // meow

&nbsp;

Here’s an example of bracket notation.

    objectName["propertyName"].


    let obj = {
    cat: 'meow',
    dog: 'woof'
    };
    let sound = obj['cat'];
    console.log(sound);
    // meow

&nbsp;

## Object looping

The JavaScript for...in statement loops through the properties of an object.

syntax:

    for (variable in object) {
    // code to be executed
    }


    const object = { a: 1, b: 2, c: 3 };

    for (const property in object) {
    console.log(`${property}: ${object[property]}`);
    }

    // expected output:
    // "a: 1"
    // "b: 2"
    // "c: 3"

&nbsp;

## Object Mutation

Mutations happen when we change a JavaScript object or array without creating a new variable or reassigning an existing one:

    const puppy = {
    name: 'Dessi',
    age: 9
    };

    puppy.age = 10;

Here we’re mutating the original puppy object by changing its age property.

Some of the problems with mutation:

- Mutation may lead to unexpected and hard-to-debug issues, where data becomes incorrect somewhere, and you have no idea where it happens.
- Mutation makes code harder to understand: at any time, an array or object may have a different value, so we need to be very careful when reading the code.
- Mutation of function arguments makes the behavior of a function surprising.

&nbsp;

## Array Mutation

JavaScript offers several ways to add, remove, and replace items in an array – but some of these ways mutate the array, and others are non-mutating; they produce a new array.

Array mutation is basically changing the array itself instead of returning a new array with the new changes.

The mutating methods for adding to an array are

    array.push()

    array.ushift().

There are two ways to add new items to an array without mutating the original array.

First, there is

    array.concat().

The second way to add to an array without mutating the original involves using JavaScript's spread operator. The spread operator is three dots (...) preceding an array.

    // since we will not be mutating,
    // use const

    const arr1 = ['a', 'b', 'c', 'd', 'e'];

    const arr2 = [...arr1, 'f']; // ['a', 'b', 'c', 'd', 'e', 'f']
    const arr3 = ['z', ...arr1]; // ['z', 'a', 'b', 'c', 'd', 'e']
