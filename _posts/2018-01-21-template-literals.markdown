---
layout: post
title:  "Making console.log() Messages More Meaningful With ES6/ES2015 Template Literals"
date:   2018-01-21 16:30:00 +0000
categories: jekyll update
---
Whilst working through a JavaScript code exercise with one of the [CodeYourFuture](https://codeyourfuture.io/) students yesterday, I thought it would be a nice little enhancement to show them how to make their `console.log()` messages a little more interesting.

## Why are they useful?
If you're anything like me,`console.log()` messages tend to be a bit basic when it comes to conveying something meaningful, as you tend to need them in the moment as you're debugging, and then they get stripped out later once they've served their purpose. In the early days of learning JavaScript though, the more meaningful messages you can make your messages, the easier it will be to understand what's going on.

According to the [Moz://a Developer Network](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/)
> Template Literals are string literals allowing embedded expressions.

...but what does that mean and why are they useful in the messages we're logging out to the console?

At their simplest, [Template Literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) are an alternative to single (`''`) and double (`""`) quotes, with the added benefit that they can have an expression evaluated inside them at runtime. Used in a `console.log()` statement, we can output a string that includes values that have been updated at the time the statement gets run.

## Getting ready
To use template literal, you will first need to find out where the 'back-tick' (\` \`) or ([grave accent](https://en.wikipedia.org/wiki/Grave_accent)) lives on your keyboard.  On most UK keyboards (full-size and laptop), it can be found at the left-end of the number row, on Apple keyboards it can be found to the left of the 'Z' key.

## How are they used?
Used in this example, the back-tick is used as a direct replacement for our usual single and double quotes.

```js
var myText = `This text was created using a back-tick`;

console.log(myText);

// "This text was created using a back-tick"
```

Let's add the clever bit then, the one we really want. It uses the following syntax _inside_ our back-ticks
```js
${expression}
```
The expression could be a variable or any longer JavaScript statement, like so...
```js
var a = 5;
var b = 10;
console.log(`Variable a is: ${a}`);
console.log(`Variable b is: ${b}`);
console.log(`a + b equals ${a + b}`);
// Variable a is: 5
// Variable b is: 10
// a + b equals 15
```

In this next example, we're getting a little more complex and using our Template Literals inside a function containing an `if/else` code block. The `console.log()` function is being used to output the properties of an object passed into an `isAllowedToDrive()` function, based on whether or not the person it contains information about is old enough to drive (you have to be 17 or over to drive a car in the UK).

```js
const john = {
  name: "John",
  age: 16,
  pronoun: "he"
}

const jane = {
  name: "Jane",
  age: 17,
  pronoun: "she"
}

function isAllowedToDrive(person) {
  if (person.age >= 17) {
    console.log(`${person.name} is ${person.age} so ${person.pronoun} is allowed to drive`);
  } else {
    console.log(`${person.name} is ${person.age} so ${person.pronoun} is NOT allowed to drive`);
  }
}

isAllowedToDrive(john);
isAllowedToDrive(jane);

// John is 16 so he is NOT allowed to drive
// Jane is 17 so she is allowed to drive
```

## Summary
You should be able to see that Template Literals are a useful way in which a `console.log()` message can be used to convey a more meaningful message about the code that has run it, with variables and expressions being evaluated dynamically at runtime. Give them a go and see how many ways they can be used to enliven your messages - you'll be seeing them a lot.

## Notes about Template literals
Template Literals have good support in modern browsers, with [support in almost 80% of browsers used globally, and almost 90% in those used within the UK](https://caniuse.com/#search=template%20literals) at time of writing. Coverage is lower across mobile browsers, and non-existent in Internet Explorer.

They are also supported by NodeJS and have been since [version 4.8.7](http://node.green/#ES2015-syntax-template-literals).
<br>
<br>
