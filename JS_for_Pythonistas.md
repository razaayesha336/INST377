# Javascript for Pythonistas (and C people)

If you are in this class, it's assumed you've been introduced to a couple of programming languages already, and achieved a minimum grade of C in working with those languages. For the purposes of this class, we'll be assuming you have working knowledge of the following:

*   SQL, from INST327
*   Python, from INST 126 or similar

In our class, we'll be working primarily with Javascript, the language of choice for the Web. Concepts from Object Oriented Programming will be useful here, but we will be relying on functional programming for the balance of the class solutions.

## Not Java

Javascript was introduced in the mid -1990s as a scripting language specifically for use in the browser. It does not have a lot in common with Java, and they are not the same environment at all.  Javascript is a C-flavoured language with provisions for some elements of object-oriented programming and a lot of room for functional or "lambda" programming, which should be familiar to you from Excel and similar environments. It is a **dynamic** language, which is not (usually) compiled before use.

Javascript's popularity on both the server and the browser side stems from one key feature. Designed to be used in the browser, an always-on environment that basically waits around for a user to do something at any given moment, Javascript is designed to be _asynchronous_ by default. That means that the language contains a lot of grammar and functional power for dealing with unexpected user events - mouseovers, for example, or server requests that arrive out of order and need to be organized. The second reason for its massive popularity is that Javascript alone focuses on being useful for programming in a primarily visual environment. Learning Javascript to do sick graph animations? Cool, you can use those same asynchronous animation principals to make your server more robust, and to understand event ordering.

Javascript is powerful and quite expressive, but its strange history means that its main design philosophy is the opposite of Python's "There should be one way to do something right" - instead, there are _many_ correct answers in a Javascript implementation. This makes it powerful and simple to use, but often complex to understand.  

Here are some pointers for how to move from thinking in Python to thinking in Javascript.

## Embedded Scripts

Javascript can run on both the client and server side of a web application, thanks to Node.js, but it is primarily _learned_ on the client side. This can be confusing for Python developers used to programming once and seeing effects in the terminal. A lot of work has gone into making JS useful on the front end. To begin working with a JS script, it can be helpful to embed it into an HTML page, and load that into a browser.  [You can learn how to include JS into your HTML pages at the W3Schools](https://www.w3schools.com/js/js_whereto.asp)

## Basic Syntax

Most JS syntax is "C-like," and you can rely on familiar operators to work normally here. 

The following work as expected in Javascript:

If you are in this class, it's assumed you've been introduced to a couple of programming languages already, and achieved a minimum grade of C in working with those languages. For the purposes of this class, we'll be assuming you have working knowledge of the following:
```
*   comments (both /* C */ style and // C++ style)
*   if / then / else
*   switch / case / break / default
*   while / do / break / continue
*   for / break / continue  
```

## Optional Operators

Semi-colons are optional in Javascript. They are not optional in this class, please use semi-colons to end your statements.

Variables & Declarations

In JS, you do not declare variable types. A variable is a named reference to an object, which has certain properties. The object you have referred to will have a type, which affects what you can do with it.  In order to work with a variable, it must be declared explicitly, as so:  

```
let x = "";   // an empty string variable  
const y = "bears"; // a defined constant string  
let z; // an undefined variable
```

If you do not define your variables explicitly, javascript will assume they are available globally. If you forget to declare a variable, the code will still run - right up until it calls the variable and discovers that it is undefined. Therefore, it is considered best practice to define your variables at the start of your script, so you can check that they are in fact present.  

## Functions and Quirks

Javascript has two flavours of function, which are slightly different than C. The first is the "named" function, and the second are "anonymous" functions.  

In basic JS named function, there are no return types - rather than declaring your expected returned value, you use the **function** keyword, as so: 

```
function temperatureConversion (cel) {
  const far = (cel * (9 / 5)) + 32; 
  return far
}
```

Here, `cel` is being passed in to the function from an external scope or context.

Anonymous functions are similar to named functions, and show up in a number of places to help supplement "lambda" or "functional" programming. This is how you write an anonymous function:

```
  function(arg1, arg2){
    statements
  }
```

Anonymous functions are primarily useful in returned statements, and can be used anywhere in the language, including to do variable assignment. 

Below, I use the alternate syntax for declaring an anonymous function, the "fat arrow" syntax:

```
const fahrenheit = (c) => {
  return (cel * (9 / 5)) + 32; 
}
```

The above is functionally identical to declaring a named function "fahrenheit", but it will not list the function name out in stack traces. If that sentence doesn't make sense to you, just know that all three ways of describing JS are valid.

## Types, Comparisons, and Coercions

Javascript only supports one type of number, the float. You can sometimes import type libraries to get more variety, but by default: only the float. Strings in javascript work almost the same way as in other CS languages, but there are some differences in how "type coercion" works.

#### "type coercion" is the process of converting one simple data type to another - ie: a number to a string, or a string to a boolean.

Sample output in console:
```
  let num = 2;
  console.log(num + num);
  4

  let str = "2"
  console.log(num + str);
  22

  console.log(num * str);
  4
```

Javascript's `+` operator is used for both addition and string concatenation. When used with at least one string parameter, it will coerce the other types to strings as well, and concatenate. With all other math operations, the string will be coerced into a number. 

This means that, combined with "brackets first" operator precedence, math can get wacky in Javascript fast.

Our chief defence against this is the use of the tight comparison operator. In other languages, just using `==` is fine. In Javascript, it really ups the odds of something not working properly... in a detailed way.

Please use `===` and `!==` instead of `==` and `!=`  in your code, it will make your life easier.

## Arrays, Lists and Hashmaps

Arrays, or "lists," are built directly into Javascript, as are hashmaps. They are called, respectively, "arrays" and "objects", which can be confusion. Their syntax is identical to Python - square braces for arrays, curly for a hashmap (an object). 

```
const arr = [1, 2, 3, 4, 5];
const obj = {'key': 'value', 'key2': 'value2'};
```

Both can be indexed using square brackets:

```
console.log(arr[2]) 
3
console.log(obj['key']);
value
```

In addition, objects can be navigated using _dot notation_, as follows:

```
console.log(obj.key);
value
```

Any combination of data types is valid as the contents of either an array or an object. Object keys are required to be strings, and will be coerced to them if they are originally defined as numbers. 

```
  obj["key"] = value // js
  myDict[repr(fred)] = value // Python
```

You can remove items from both types of storage with the same syntax, `delete`.

```
delete arr[3];
true;

delete obj["key2"];
true;
```

"true" here just means that the function returned with no error, it does not guarantee that the key existed to begin with, which means that deletion in more serious programs should be handled slightly differently, typically by setting a value to zero or splicing it out of the array. This is to counterbalance that deleting an item from an array at a specific index only sets that index to `undefined`, it does not change the array's length.

It is preferred to use `array.splice()` to add or remove arbitrary keys from your arrays. `splice` returns the new array with the new values, no harm done.

```
arr = [1,2,3];
arr.splice(1, 2.5);
console.log(array);
[1, 2, 2.5, 3];
```

Arrays will automatically grow when values are added to them, and always have a method called `length` which you can use to check positions.

## Loops

While Python appears to make a lot of use of `for...in` loops, these are only recently preferred in JS - there have been a lot of syntax changes in the last three years, but before that, loops were tricky. As a consequence, while JS _has_ `while`, `break`, `try`, etc. the usual looping method is a simple `for` loop, set to run a pre-determined number of times.

```
const arr = [1, 2, 3, 4, 5];
for(var i = 0; i < arr.length; i ++){
  console.log(arr[i]);
}

1
2
3
4
5
```

## Conclusion

Javascript is a straightforward language with some serious gaps in it around data types. It makes up for these gaps by being extremely permisssive for new learners, who only need to pick up seven primitives, a for loop, and an if statement to get started. Good luck!

