---
layout: post
title: "learnXinYminute's javascript article translated to Farsi"
description: ""
category: ""
tags: []
---
{% include JB/setup %}

<p dir='rtl'>
جاوااسکریپت توسط برندن ایش از شرکت NetScape در سال 1995 ساخته شد. در ابتدا به عنوان یک زبان اسکریپت‌نویسی  در کنار جاوا (که برای موارد پیچیده تر در طراحی وب در نظر گرفته میشد) مورد استفاده بود، ولی در پی نفوذ بسیار گسترده آن در وب و همچنین پشتیبانی پیش-ساخته آن در مرورگر ها، امروزه به مراتب بیشتر از جاوا در برنامه نویسی سمت-کاربر در وب به کار برده میشود.
با این حال جاوااسکریپت فقط محدود به مرورگر های وب نمیشود. Node.js پروژه ایست که یک نسخه ی مستقل از اجراکننده ی موتور جاوااسکریپت V8 از گوگل کروم را در اختیار قرار میده که هر روزه درحال محبوب تر شدن نیز هست.
</p>

<p dir='rtl'>
قدر دان نظرات سازنده شما هستم! شما میتوانید از طریق زیر با من تماس بگیرید:
</p>

[@adambrenecki](https://twitter.com/adambrenecki), or
[adam@brenecki.id.au](mailto:adam@brenecki.id.au).

<p dir='rtl'>
// توضیحات همانند C هستند. توضیحات یک خطی با دو خط مورب شروع میشوند.,
</p>

<p dir='rtl'>
/* و توضیحات چند خطی با خط مورب-ستاره شروع،
   و با ستاره-خط مورب ختم میشوند */
</p>

```js
// Comments are like C. Single-line comments start with two slashes,
/* and multiline comments start with slash-star
   and end with star-slash */
```
<p dir='rtl'>
گزاره ها را میتوانید با نقطه ویرگول پایان دهید ;
</p>
```js
doStuff();
```
<p dir='rtl'>
ولی لزومی به این کار نیست. نقطه ویرگول به صورت خودکار در نظر گرفته میشوند.  
</p>
<p dir='rtl'>
وقتی که خط جدیدی شروع میشود. مگر در موارد خاص.
</p>
```js
doStuff()
```
<p dir='rtl'>برای اینگه درگیر آن موارد خاص نشویم، در اینجا از اون ها  </p>
<p dir='rtl'>صرف نظر میکنیم.</p>

<h2 dir='rtl'>1. اعداد، رشته ها و عملگرها</h2>

<p dir='rtl'>جاوااسکریپت فقط یک نوع عدد دارد و آن عدد اعشاری 64 بیتی IEEE 754 است.</p>
<p dir='rtl'>نترسید! و نگران اعداد صحیح نباشید! این اعداد اعشاری دارای 54 بیت مانتیس هستند که قابلیت ذخیره ی </p>
<p dir='rtl'>دقیق اعداد صحیح تا مقدار تقریبی 9x10¹⁵  را دارند.</p>
```js
3; // = 3
1.5; // = 1.5
```
<p dir='rtl'>
تمامی عملگر های محاسباتی آن طوری که انتظارش را دارید عمل خواهند کرد.
</p>
```js
1 + 1; // = 2
8 - 1; // = 7
10 * 2; // = 20
35 / 5; // = 7
```
<p dir='rtl'>و این حتی شامل تقسیم هم میشود.</p>
```js
5 / 2; // = 2.5
```
<p dir='rtl'>عملگر های بیتی هم به همین شکل. وقتی از یک عملگر بیتی استفاده میکنید، عدد اعشاری شما</p>
<p dir='rtl'>به عدد صحیح علامت دار *تا 32 بیت* تبدیل میشود.</p>
```js
1 << 2; // = 4
```
<p dir='rtl'>عملیات داخل پرانتز تقدم بالاتری دارند.</p>
```js
(1 + 3) * 2; // = 8
```
<p dir='rtl'>سه مقدار خاص وجود دارند که در واقع مقادیر عددی نیستند:</p>
```js
Infinity; // result of e.g. 1/0
-Infinity; // result of e.g. -1/0
NaN; // result of e.g. 0/0
```
<p dir='rtl'>مقادیر بولی هم تعریف شده هستند:</p>
```js
true;
false;
```
<p dir='rtl'>رشته ها با آپستروف و یا گیومه تعریف میشوند.</p>
```js
'abc';
"Hello, world";
```
<p dir='rtl'>و منفی کردن شرط با علامت تعجب</p>
```js
!true; // = false
!false; // = true
```
<p dir='rtl'>تساوی دو مقدار با ==</p>
```js
1 == 1; // = true
2 == 1; // = false
```
<p dir='rtl'>و عدم تساوی با !=</p>
```js
1 != 1; // = false
2 != 1; // = true
```
<p dir='rtl'>و سایر عمیلات های مقایسه</p>
```js
1 < 10; // = true
1 > 10; // = false
2 <= 2; // = true
2 >= 2; // = true
```
<p dir='rtl'>رشته ها با علامت جمع به یکدیگر متصل میشوند</p>
```js
"Hello " + "world!"; // = "Hello world!"
```
<p dir='rtl'>و با علامت برگتر و یا کوچکتر با یکدیگر مقایسه میشوند.</p>
```js
"a" < "b"; // = true
```
<p dir='rtl'>نوع متغیر برای عملیات مقایسه تطبیق داده میشود</p>
```js
"5" == 5; // = true
```
<p dir='rtl'>مگر اینکه از سه مساوی استفاده شود!</p>
```js
"5" === 5; // = false
```
<p dir='rtl'>با استفاده از charAt میتوانید به کارکتر های یک رشته دسترسی پیدا کنید.</p>
```js
"This is a string".charAt(0);
```
<p dir='rtl'>از null برای نشان دادن عمدی مقدار هیج استفاده میشود.</p>
<p dir='rtl'>و از undefined برای نشان دادن اینکه در حال حاظر مقدار موجود نمی باشد، هرچند خود undefined یک مقدار محسوب میشود.</p>
```js
null; // used to indicate a deliberate non-value
undefined; // used to indicate a value is not currently present (although undefined
           // is actually a value itself)
```
<p dir='rtl'>false, null, undefined, NaN, 0 و "" مقدار نادرست و هر چیز دیگر مقدار درست طلقی میشوند.</p>
<p dir='rtl'>توجه داشته باشید که 0 نادرست و "0" درست طلقی میشوند حتی در عبارت 0=="0".</p>
```js

///////////////////////////////////
// 2. Variables, Arrays and Objects

// Variables are declared with the var keyword. Javascript is dynamically typed,
// so you don't need to specify type. Assignment uses a single = character.
var someVar = 5;

// if you leave the var keyword off, you won't get an error...
someOtherVar = 10;

// ...but your variable will be created in the global scope, not in the scope
// you defined it in.

// Variables declared without being assigned to are set to undefined.
var someThirdVar; // = undefined

// There's shorthand for performing math operations on variables:
someVar += 5; // equivalent to someVar = someVar + 5; someVar is 10 now
someVar *= 10; // now someVar is 100

// and an even-shorter-hand for adding or subtracting 1
someVar++; // now someVar is 101
someVar--; // back to 100

// Arrays are ordered lists of values, of any type.
var myArray = ["Hello", 45, true];

// Their members can be accessed using the square-brackets subscript syntax.
// Array indices start at zero.
myArray[1]; // = 45

// Arrays are mutable and of variable length.
myArray.push("World");
myArray.length; // = 4

// JavaScript's objects are equivalent to 'dictionaries' or 'maps' in other
// languages: an unordered collection of key-value pairs.
var myObj = {key1: "Hello", key2: "World"};

// Keys are strings, but quotes aren't required if they're a valid
// JavaScript identifier. Values can be any type.
var myObj = {myKey: "myValue", "my other key": 4};

// Object attributes can also be accessed using the subscript syntax,
myObj["my other key"]; // = 4

// ... or using the dot syntax, provided the key is a valid identifier.
myObj.myKey; // = "myValue"

// Objects are mutable; values can be changed and new keys added.
myObj.myThirdKey = true;

// If you try to access a value that's not yet set, you'll get undefined.
myObj.myFourthKey; // = undefined

///////////////////////////////////
// 3. Logic and Control Structures

// The if structure works as you'd expect.
var count = 1;
if (count == 3){
    // evaluated if count is 3
} else if (count == 4) {
    // evaluated if count is 4
} else {
    // evaluated if it's not either 3 or 4
}

// As does while.
while (true) {
    // An infinite loop!
}

// Do-while loops are like while loops, except they always run at least once.
var input
do {
    input = getInput();
} while (!isValid(input))

// the for loop is the same as C and Java:
// initialisation; continue condition; iteration.
for (var i = 0; i < 5; i++){
    // will run 5 times
}

// && is logical and, || is logical or
if (house.size == "big" && house.colour == "blue"){
    house.contains = "bear";
}
if (colour == "red" || colour == "blue"){
    // colour is either red or blue
}

// && and || "short circuit", which is useful for setting default values.
var name = otherName || "default";

///////////////////////////////////
// 4. Functions, Scope and Closures

// JavaScript functions are declared with the function keyword.
function myFunction(thing){
    return thing.toUpperCase();
}
myFunction("foo"); // = "FOO"

// JavaScript functions are first class objects, so they can be reassigned to
// different variable names and passed to other functions as arguments - for
// example, when supplying an event handler:
function myFunction(){
    // this code will be called in 5 seconds' time
}
setTimeout(myFunction, 5000);
// Note: setTimeout isn't part of the JS language, but is provided by browsers
// and Node.js.

// Function objects don't even have to be declared with a name - you can write
// an anonymous function definition directly into the arguments of another.
setTimeout(function(){
    // this code will be called in 5 seconds' time
}, 5000);

// JavaScript has function scope; functions get their own scope but other blocks
// do not.
if (true){
    var i = 5;
}
i; // = 5 - not undefined as you'd expect in a block-scoped language

// This has led to a common pattern of "immediately-executing anonymous
// functions", which prevent temporary variables from leaking into the global
// scope.
(function(){
    var temporary = 5;
    // We can access the global scope by assiging to the 'global object', which
    // in a web browser is always 'window'. The global object may have a
    // different name in non-browser environments such as Node.js.
    window.permanent = 10;
})();
temporary; // raises ReferenceError
permanent; // = 10

// One of JavaScript's most powerful features is closures. If a function is
// defined inside another function, the inner function has access to all the
// outer function's variables, even after the outer function exits.
function sayHelloInFiveSeconds(name){
    var prompt = "Hello, " + name + "!";
    function inner(){
        alert(prompt);
    }
    setTimeout(inner, 5000);
    // setTimeout is asynchronous, so the sayHelloInFiveSeconds function will
    // exit immediately, and setTimeout will call inner afterwards. However,
    // because inner is "closed over" sayHelloInFiveSeconds, inner still has
    // access to the 'prompt' variable when it is finally called.
}
sayHelloInFiveSeconds("Adam"); // will open a popup with "Hello, Adam!" in 5s

///////////////////////////////////
// 5. More about Objects; Constructors and Prototypes

// Objects can contain functions.
var myObj = {
    myFunc: function(){
        return "Hello world!";
    }
};
myObj.myFunc(); // = "Hello world!"

// When functions attached to an object are called, they can access the object
// they're attached to using the this keyword.
myObj = {
    myString: "Hello world!",
    myFunc: function(){
        return this.myString;
    }
};
myObj.myFunc(); // = "Hello world!"

// What this is set to has to do with how the function is called, not where
// it's defined. So, our function doesn't work if it isn't called in the
// context of the object.
var myFunc = myObj.myFunc;
myFunc(); // = undefined

// Inversely, a function can be assigned to the object and gain access to it
// through this, even if it wasn't attached when it was defined.
var myOtherFunc = function(){
    return this.myString.toUpperCase();
}
myObj.myOtherFunc = myOtherFunc;
myObj.myOtherFunc(); // = "HELLO WORLD!"

// When you call a function with the new keyword, a new object is created, and
// made available to the function via this. Functions designed to be called
// like this are called constructors.

var MyConstructor = function(){
    this.myNumber = 5;
}
myNewObj = new MyConstructor(); // = {myNumber: 5}
myNewObj.myNumber; // = 5

// Every JavaScript object has a 'prototype'. When you go to access a property
// on an object that doesn't exist on the actual object, the interpreter will
// look at its prototype.

// Some JS implementations let you access an object's prototype on the magic
// property __proto__. While this is useful for explaining prototypes it's not
// part of the standard; we'll get to standard ways of using prototypes later.
var myObj = {
    myString: "Hello world!",
};
var myPrototype = {
    meaningOfLife: 42,
    myFunc: function(){
        return this.myString.toLowerCase()
    }
};
myObj.__proto__ = myPrototype;
myObj.meaningOfLife; // = 42

// This works for functions, too.
myObj.myFunc(); // = "hello world!"

// Of course, if your property isn't on your prototype, the prototype's
// prototype is searched, and so on.
myPrototype.__proto__ = {
    myBoolean: true
};
myObj.myBoolean; // = true

// There's no copying involved here; each object stores a reference to its
// prototype. This means we can alter the prototype and our changes will be
// reflected everywhere.
myPrototype.meaningOfLife = 43;
myObj.meaningOfLife; // = 43

// We mentioned that __proto__ was non-standard, and there's no standard way to
// change the prototype of an existing object. However, there are two ways to
// create a new object with a given prototype.

// The first is Object.create, which is a recent addition to JS, and therefore
// not available in all implementations yet.
var myObj = Object.create(myPrototype);
myObj.meaningOfLife; // = 43

// The second way, which works anywhere, has to do with constructors.
// Constructors have a property called prototype. This is *not* the prototype of
// the constructor function itself; instead, it's the prototype that new objects
// are given when they're created with that constructor and the new keyword.
MyConstructor.prototype = {
    myNumber: 5,
    getMyNumber: function(){
        return this.myNumber;
    }
};
var myNewObj2 = new MyConstructor();
myNewObj2.getMyNumber(); // = 5
myNewObj2.myNumber = 6
myNewObj2.getMyNumber(); // = 6

// Built-in types like strings and numbers also have constructors that create
// equivalent wrapper objects.
var myNumber = 12;
var myNumberObj = new Number(12);
myNumber == myNumberObj; // = true

// Except, they aren't exactly equivalent.
typeof(myNumber); // = 'number'
typeof(myNumberObj); // = 'object'
myNumber === myNumberObj; // = false
if (0){
    // This code won't execute, because 0 is falsy.
}
if (Number(0)){
    // This code *will* execute, because Number(0) is truthy.
}

// However, the wrapper objects and the regular builtins share a prototype, so
// you can actually add functionality to a string, for instance.
String.prototype.firstCharacter = function(){
    return this.charAt(0);
}
"abc".firstCharacter(); // = "a"

// This fact is often used in "polyfilling", which is implementing newer
// features of JavaScript in an older subset of JavaScript, so that they can be
// used in older environments such as outdated browsers.

// For instance, we mentioned that Object.create isn't yet available in all
// implementations, but we can still use it with this polyfill:
if (Object.create === undefined){ // don't overwrite it if it exists
    Object.create = function(proto){
        // make a temporary constructor with the right prototype
        var Constructor = function(){};
        Constructor.prototype = proto;
        // then use it to create a new, appropriately-prototyped object
        return new Constructor();
    }
}
```

## Further Reading

The [Mozilla Developer
Network](https://developer.mozilla.org/en-US/docs/Web/JavaScript) provides
excellent documentation for JavaScript as it's used in browsers. Plus, it's a
wiki, so as you learn more you can help others out by sharing your own
knowledge.

MDN's [A re-introduction to
JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript)
covers much of the concepts covered here in more detail. This guide has quite
deliberately only covered the JavaScript language itself; if you want to learn
more about how to use JavaScript in web pages, start by learning about the
[Document Object
Model](https://developer.mozilla.org/en-US/docs/Using_the_W3C_DOM_Level_1_Core)

[Javascript Garden](http://bonsaiden.github.io/JavaScript-Garden/) is an in-depth
guide of all the counter-intuitive parts of the language.

In addition to direct contributors to this article, some content is adapted
from Louie Dinh's Python tutorial on this site, and the [JS
Tutorial](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript)
on the Mozilla Developer Network.
