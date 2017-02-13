# Java Script style-guide

## Code Formatting Guidelines

### Indentation

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use four spaces for indentation.

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Try to keep lines to 120 characters or less.

Think of this guideline as a recommendation not a rule. Do not sacrifice expressiveness in a favor of line length.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Mix indentation styles within a project.

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Enforce indentation rules at compile time with JSHint.

How to configure? [Awaits to be discussed]
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: When wrapping lines, indent to line up with a related item on the previous line.

Right
 
```javascript 
var result = prompt(
    aMessage,
    aInitialValue,
    aCaption);
```
    
Right
 
```javascript
$('.navigation-menu')
    .find('li')
    .css('background-color', 'red')
    .show();
```

## Whitespacing

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Put trailing spaces at the end of the lines, even after binary operators, commas or semicolons.

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Separate binary operators with spaces.
 	
 Right
```javascript
var y = (10 + x) / 12;
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Put spaces after commas and semicolons, but not before.
 	
 Right
```javascript 
 function f(a, b, c, d) {
 
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Put spaces after keywords, e.g.
 	
 Right
```javascript
if (x > 0)
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Put one (or two) blank lines between block definitions.
 	
 Right
```javascript
function f() {
    var contextWidth = getContextWidth();
    var contextHeight = getContextHeight();
 
    var contextSquare = contextWidth * contextHeight;
    var contextPerimeter = (contextHeight + contextWidth) * 2;
 
    var factor = contextSquare / contextPerimeter;
 
    return factor;
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Breaking up large code blocks with blank lines.

### Comments

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Rewrite tricky code, instead of commenting it.

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Write comments in US English.

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Indent comments to the same level as code that it aimed to clarify.
 	
 Right
```javascript
ko.exportSymbol = function (koPath, object) {
    var tokens = koPath.split(".");
 
    // In the future, "ko" may become distinct from "koExports" (so that non-exported objects are not reachable)
    // At that point, "target" would be set to: (typeof koExports !== "undefined" ? koExports : ko)
    var target = ko;
 
    for (var i = 0; i < tokens.length - 1; i++) {
        target = target[tokens[i]];
    }
 
    target[tokens[tokens.length - 1]] = object;
};
```

 Wrong
```javascript
ko.exportSymbol = function (koPath, object) {
    var tokens = koPath.split(".");
 
// In the future, "ko" may become distinct from "koExports" (so that non-exported objects are not reachable)
// At that point, "target" would be set to: (typeof koExports !== "undefined" ? koExports : ko)
    var target = ko;
 
    for (var i = 0; i < tokens.length - 1; i++) {
        target = target[tokens[i]];
    }
 
    target[tokens[tokens.length - 1]] = object;
};
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Write comments to explain a purpose of code blocks, but not what is does.
 	
 Right
```javascript
// Internally, all KO objects are attached to koExports (even the non-exported ones whose names will be minified by the closure compiler).
// In the future, the following "ko" variable may be made distinct from "koExports" so that private objects are not externally reachable.
var ko = typeof koExports !== 'undefined' ? koExports : {};
```
```javascript
 Wrong
// Declare variable foo as an integer and set it to three.
var foo = 3;
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: When wrapping lines, indent to line up with a related item on the previous line.

DO NOT
Icon
Write comments for every single line of code.
DO
Icon
Start sentences with a properly capitalized word, and end them with punctuation.
 	
 Right
// Google Closure Compiler helpers (used only to make the minified file smaller).
ko.exportSymbol = function(koPath, object) {
CONSIDER
Icon
Documenting all files, classes, methods and properties with JSDoc comments using appropriate tags and types.
 	
 Right
/**
  * @ngdoc method
  * @name ngMock.$timeout#flushNext
  * @methodOf ngMock.$timeout
  * @description
  *
  * Flushes the next timeout in the queue and compares it to the provided delay
  *
  * @param {number=} expectedDelay the delay value that will be asserted against the delay of the next timeout function
  */
$delegate.flushNext = function (expectedDelay) {
    $browser.defer.flushNext(expectedDelay);
};
 	
 Right
/**
 * Computes the path of definition describe blocks that wrap around
 * this spec.
 *
 * @param spec Spec to compute the path for.
 * @return {Array<Describe>} The describe block path
 */
angular.scenario.ObjectModel.prototype.getDefinitionPath = function (spec) {
    var path = [];
    var currentDefinition = spec.definition;
    while (currentDefinition && currentDefinition.name) {
        path.unshift(currentDefinition);
        currentDefinition = currentDefinition.parent;
    }
    return path;
};
Semicolons
DO
Icon
Always use semicolons.
DO
Icon
Put semicolons at the end of function expressions.
 	
 Right
var foo = function () {
    return true;
};  // semicolon here.
DO NOT
Icon
Put semicolons at the end of function declarations.
 	
 Right
function foo() {
    return true;
}  // no semicolon here.
Quotes
DO
Icon
Whether you prefer single or double shouldn't matter, there is no difference in how JavaScript parses them. What ABSOLUTELY MUST be enforced is consistency. Never mix quotes in the same project. Pick one style and stick with it.
Block statements
DO
Icon
Indent enclosed statements with four more spaces.
 	
 Right
if (condition) {
    firstAction();  // Add 4 more spaces within the body of compound statement.
    secondAction();
}
 Wrong
if (condition) {
firstAction();
secondAction();
}
DO
Icon
Place "{" (left curly brace) at the end of the line that begins the compound statement.
Place "}" (right curly brace) at the begin of new line and indent it to align with the beginning of the line containing the matching "{" (left curly brace).
 	
 Right
if (condition) {
    firstAction();
    secondAction();
}
 Wrong
if (condition)
{
    firstAction();
    secondAction();
}
DO
Icon
Braces should be used around all statements, even single statements, when they are part of a control structure, such as an "if" or "for" statement. This makes it easier to add statements without accidentally introducing bugs.
 	
 Right
if (condition) {
    action();
}
 Wrong
if (condition) { action(); }
DO
Icon
Put else clause at the same line as closing "}" bracket of "if" statement.
 	
 Right
if (valuesToPush instanceof Array) {
    array.push.apply(array, valuesToPush);
} else {
    for (var i = 0, j = valuesToPush.length; i < j; i++) {
        array.push(valuesToPush[i]);
    }
}
 Wrong
if (valuesToPush instanceof Array) {
    array.push.apply(array, valuesToPush);
}
else {
    for (var i = 0, j = valuesToPush.length; i < j; i++) {
        array.push(valuesToPush[i]);
    }
}
Naming Guidelines
Naming
DO
Icon
Write all names in US English.
DO
Icon
Use following naming rules:
Function Names: camelCase
Constructor Functions: PascalCase
Variable Names: camelCase
Enum Names: PascalCase
Enum Values: SCREAMING_CAPS
Method Names: camelCase
Constants: SCREAMING_CAPS
Namespace Names: PascalCase
 	
 Right
var App = {};
 
App.AccessMode = {
    READ: 1,
    WRITE: 2,
    READ_WRITE: 3
};
 
App.ApplicationViewModel = function () {
    var APPLICATION_VERSION = '1.0.0';
 
    this.run = function () {
        var version = APPLICATION_VERSION;
    };
};
DO
Icon
Group related constants within a single object created as a holder for constants, emulating an enumerated type.
 	
 Right
var NodeTypes = {
    ELEMENT: 1,
    DOCUMENT: 2
};
DO NOT
Icon
Use abbreviations
 	
 Wrong
createEl, cls, cmpStrs
 Right
createElement, class, compareStrings
DO
Icon
Capitalize both letters of 2-letter acronyms.
Capitalization rules should not conflict with general naming guidelines. If first letter of acronym should be small – do not apply capitalization to the rest of the letters.
 	
 Right
function getIOResult() {
 
}
 Wrong
function getIoResult() {
 
}
DO
Icon
Capitalize only first letter of acronyms longer than 2 letters.
 	
 Right
var formattedXml;
 
function getHtml() {
 
}
 Wrong
var formattedXML;
 
function getHTML() {
 
}
DO NOT
Icon
Apply capitalization rules of acronyms for non-acronyms even if they look alike.
 	
 Wrong
ID, OK, PI
 Right
Id, Ok, Pi
CONSIDER
Icon
Prefixing private properties and methods with leading underscore.
 	
 Right
function Entity(id, name) {
    var _id = id;
    var _name = name;
 
    this.getId = function () {
        return _id;
    }
 
    this.getName = function () {
        return _name;
    }
}
DO
Icon
Name Boolean properties and variables with an affirmative phrase (canSeek instead of cantSeek). Optionally, you can also prefix Boolean properties with "is," "can," or "has," but only where it adds value.
DO
Icon
Use plural to name collections.
 	
 Right
Items, Entities, Errors
DO NOT
Icon
Use negated boolean variable names.
 	
 Wrong
isNotError, isNotFound
DO
Icon
Put "Error" suffix at the end of Exception classes.
 	
 Right
NotFoundError, OutOfRangeError, BusinessLogicError
CONSIDER
Icon
Methods returning an object MAY be named after what they return, and methods returning void after what they do.
Declaration Guidelines
Variable declaration
DO
Icon
Declare variable with "var" statement before actually using it.
Keep in mind that if you assign value to non-existing variable it automatically becomes global, that's why you should carefully follow aforementioned rule all the time.
DO
Icon
Use multiple "var" statements if you need to declare multiple variables.
 	
 Right
function f() {
    var a = 1;
    var b = 2;
    var c = a + b;
 
    return c / 2;
}
DO NOT
Icon
Combine variable declarations under single "var statement".
 	
 Wrong
function f() {
    var a = 1,
        b = 2,
        c = a + b;
 
    return c / 2;
}
DO
Icon
Declare variables close to where they are actually used.
 	
 Right
function f(items) {
    var numberOfItems = items.length;
 
    for (var i = 0; i < numberOfItems; i++) {
        var item = items[i];
        item.sell();
    }
}
DO NOT
Icon
Place all variable declarations at the beginning of the function.
While many practitioners strongly encourage this style it serves no purpose for readability and modularity of your code, and primarily aimed to shield developers from nuances of script execution.
 	
 Wrong
function f(items) {
    var numberOfItems = items.length;
    var item;
    var i;
 
    for (i = 0; i < numberOfItems; i++) {
        item = items[i];
        item.sell();
    }
}
 Wrong
function f(items) {
    var numberOfItems = items.length,
        item,
        i;
 
    for (i = 0; i < numberOfItems; i++) {
        item = items[i];
        item.sell();
    }
}
Function declarations
DO NOT
Icon
Put space between the name of a function and the "(" (left parenthesis) of its parameter list.
DO
Icon
Put one space between the ")" (right parenthesis) and the "{" (left curly brace) that begins the statement body.
DO
Icon
Align "}" (right curly brace) with the line containing the beginning of the declaration of the function.
 	
 Right
function f() {
 
}
DO
Icon
Put one space between the word function and the "(" (left parenthesis).
 	
 Right
div.addEventListener('click', function (e) {
    return false;
});
DO NOT
Icon
Use function declarations within block
While most script engines support Function Declarations within blocks it is not part of ECMAScript (see ECMA-262, clause 13 and 14). Worse implementations are inconsistent with each other and with future EcmaScript proposals. ECMAScript only allows for Function Declarations in the root statement list of a script or function. Instead use a variable initialized with a Function Expression to define a function within a block:
 	
 Wrong
if (x) {
  function foo() {}
}
 Right
if (x) {
    var foo = function () {};
}
DO
Icon
When defining IIFE, put function call outside of parenthesis.
 	
 Right
(function () {
    var x = 10;
})();
 Wrong
(function () {
    var x = 10;
}());
Functional Guidelines
Strict Mode
DO
Icon
Use strict execution mode.
DO NOT
Icon
Apply strict mode to a whole file. Instead, apply strict mode selectively at function level.
Applying strict mode to whole file can potentially brake your application after script minification.
 	
 Wrong
'use strict';
 
function Person() {
    this.firstName= 'Douglas';
    this.lastName = 'Crockford';
}
 Right
(function () {
    'use strict';
 
    function Person() {
        this.firstName = 'Douglas';
        this.lastName = 'Crockford';
    }
})();
Eval
DO NOT
Icon
Use Eval for application level activities (parsing JSON responses, type casting, e.t.c).
Improper use of Eval leads to security, maintainability and performance issues.
 	
 Wrong
var request = new XMLHttpRequest();
 
request.addEventListener('load', function () {
    var jsonData = this.responseText;
    var data = eval('(' + jsonData + ')');
});
 Right
var request = new XMLHttpRequest();
 
request.addEventListener('load', function () {
    var jsonData = this.responseText;
    var data = JSON.parse(jsonData);
});
 Right
var request = new XMLHttpRequest();
request.responseType = 'json';
 
request.addEventListener('load', function () {
    var data = this.response;
});
 Wrong
var numberAsString = '10';
var number = eval(numberAsString);
 Right
var numberAsString = '10';
var number = Number(numberAsString);
DO NOT
Icon
Use any forms of implicit Eval to satisfy previous guideline.
 	
 Wrong
setTimeout('alert("Implicit eval");', 0);
setInterval('alert("Implicit eval");', 0);
(new Function('alert("Implicit eval");'))();
CONSIDER
Icon
Wise use of Eval for framework level activities, when it is not possible to avoid it.
Almost all of the proper use cases of Eval fall under situation where you need to execute 3rd party code but for some reasons it`s not technically feasible to load with <script> tag.
Undefined
DO
Icon
Treat undefined as representation of system-level, unexpected, or error-like absence of value and null as representation of program-level, normal, or expected absence of value.
DO NOT
Icon
Assign undefined directly to represent the intentional absence of any object value. Assign null or semantically default value instead.
 	
 Wrong
function ContestFilter() {
    this.contestId = undefined;
    this.status = undefined;
    this.duration = undefined;
}
 Right
function ContestFilter() {
    this.contestId = null;
    this.status = null;
    this.duration = null;
}
 Right
function ContestFilter() {
    this.contestId = 0;
    this.status = null;
    this.duration = 0;
}
 
Modularity
CONSIDER
Icon
Wrapping script files into IIFE to limit its visibility and protect from outer impact.
This technique facilitates next benefits:
Allows encapsulating implementation details into local variables and exposing publicly visible API relying on closures
Provides convenient point for application of strict mode
Allows to protect your script from outer environment by capturing dependencies as parameters
 
 	
 Right
(function ($, undefined) {
    'use strict';
\\
    App.ModelBinder = {
        bind: function (element, event) {
            if (element === undefined) {
                return;
            }
        }
    };
}(jQuery));
DO NOT
Icon
Artificially introduce IIFE when file is already wrapped with a function.
 	
 Wrong
(function () {
    'use strict';
 
    define(function (require) {
        var shirt = require("./shirt");
 
        return {
            logTheShirt: function () {
                console.log("color: " + shirt.color + ", size: " + shirt.size);
            }
        };
    });
})();
 Right
define(function (require) {
    'use strict';
 
    var shirt = require("./shirt");
 
    return {
        logTheShirt: function () {
            console.log("color: " + shirt.color + ", size: " + shirt.size);
        }
    };
});
DO
Icon
Group related functionality into namespaces.
JavaScript has no notion of namespaces, but you can emulate them with nested objects.
 	
 Right
var App = {};
 
App.Models = {
    Person: function (firstName, lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    },
 
    Activity: function (name) {
        this.name = name;
    }
};
 Wrong
function Person(firstName, lastName) {
    this.firstName = firstName;
    this.lastName = lastName;
}
 
function Activity(name) {
    this.name = name;
}
Exceptions
DO
Icon
Use custom exceptions to indicate exceptional flow of execution.
 	
 Declaration
function OutOfRangeError(value) {
    this.message = 'Value ' + value + ' is out of range.';
}
 
OutOfRangeError.prototype = new Error();
OutOfRangeError.prototype.constructor = OutOfRangeError;
 Usage
function f(x) {
    if (x < 0) {
        throw new OutOfRangeError('x');
    }
 
    return x * 2;
}
DO NOT
Icon
Combine error code or inject error member into return value of a function.
 	
 Wrong
function f(x) {
    if (x < 0) {
        return false;
    }
 
    return x * 2;
}
 Wrong
function f(x) {
    var result = {
        value: null,
        error: false
    };
 
    if (x < 0) {
        result.error = true;
        return;
    }
 
    result.value = x * 2;
 
    return result;
}
{} and []
DO
Icon
Use {} instead of new Object().
Use [] instead of new Array().
Wrapper objects for primitive types
DO NOT
Icon
Use wrapper objects for primitive types.
Once you wrap real primitive type into object it automatically becomes truthy in logical comparisons. It may lead to hard to track bugs and unpredictable errors in application logic.
 	
 Wrong
var x = new Boolean(false);
 
if (x) {
    alert('hi');  // Shows 'hi'.
}
CONSIDER
Icon
Use constructors of wrapper objects for type casting.
This guideline does not prohibit use of more succinct forms of typecasting. Treat them all equally, but keep in mind that additionally, primitive constructors are capable of unboxing wrapped primitives into real values.
 	
 Right
var x = Boolean(0);
 
if (x) {
    alert('hi');  // This will never be alerted.
}
 
typeof Boolean(0) === 'boolean';
typeof new Boolean(0) === 'object';
Delete
CONSIDER
Icon
Setting property to null instead of deleting it.
In modern JavaScript engines, changing the number of properties on an object is much slower than reassigning the values. The delete keyword should be avoided except when it is necessary to remove a property from an object's iterated list of keys, or to change the result of if (key in obj).
 	
 Right
Foo.prototype.dispose = function () {
    this.property = null;
};
 Wrong
Foo.prototype.dispose = function () {
    delete this.property;
};
With() {}
DO NOT
Icon
Use "with" statement.
Using "with" hides the semantics of your program. Because the object of the "with" statement can have properties that collide with local variables, it can drastically change the meaning of your program.
For-in loop
DO
Icon
Use it only for iterating over keys in an object.
 	
 Right
for (var key in person) {
    var value = person[key];
    console.log(key + ': ' + value);
}
DO NOT
Icon
Use it to loop over the elements in an Array.
This is very error prone because it does not loop from 0 to length - 1 but over all the present keys in the object and its prototype chain.
 	
 Wrong
var data = [0, 25, 25, 45, 123, 10];
 
for (var key in data) {
    var value = data[key];
    console.log(key + ': ' + value);
}
 Right
var data = [0, 25, 25, 45, 123, 10];
 
for (var i = 0; i < data.length; i++) {
    var value = data[i];
    console.log(key + ': ' + value);
}
CONSIDER
Icon
Filtering iterated properties with hasOwnProperty.
 	
 Right
var person = {
    firstName: 'John',
    secondName: 'Shepard'
};
 
for (var key in person) {
    if (person.hasOwnProperty(key)) {
        var value = person[key];
        console.log(key + ': ' + value);
    }
}
=== and !== operators
DO
Icon
Prefer strict comparisons ("===" and "!==").
CONSIDER
Icon
Using regular comparisons where implicit type casting is desirable.
 	
 Right
function f(x) {
    if (x == null) { // Checks whether x is null or undefined.
        return 0;
    }
 
    return x;
}
Modifying prototypes of built-in objects
DO NOT
Icon
Modify prototype of host and native objects.
Modifying prototypes of Object, Array, Function and other built-ins is dangerous and may lead to hard to debug issues in production and should be avoided.
 
DO
Icon
Write extensions in a form of utility objects instead of extending prototypes of built-in objects.
