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

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript 
var result = prompt(
    aMessage,
    aInitialValue,
    aCaption);
```
    
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
$('.navigation-menu')
    .find('li')
    .css('background-color', 'red')
    .show();
```

### Whitespacing

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Put trailing spaces at the end of the lines, even after binary operators, commas or semicolons.

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Separate binary operators with spaces.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
var y = (10 + x) / 12;
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Put spaces after commas and semicolons, but not before.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript 
 function f(a, b, c, d) {
 
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Put spaces after keywords, e.g.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
if (x > 0)
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Put one (or two) blank lines between block definitions.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
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
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
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

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
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
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
// Internally, all KO objects are attached to koExports (even the non-exported ones whose names will be minified by the closure compiler).
// In the future, the following "ko" variable may be made distinct from "koExports" so that private objects are not externally reachable.
var ko = typeof koExports !== 'undefined' ? koExports : {};
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
// Declare variable foo as an integer and set it to three.
var foo = 3;
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: When wrapping lines, indent to line up with a related item on the previous line.

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Write comments for every single line of code.

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Start sentences with a properly capitalized word, and end them with punctuation.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
// Google Closure Compiler helpers (used only to make the minified file smaller).
ko.exportSymbol = function(koPath, object) {
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Documenting all files, classes, methods and properties with JSDoc comments using appropriate tags and types.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
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
```
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
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
```

### Semicolons

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Always use semicolons.
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Put semicolons at the end of function expressions.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
var foo = function () {
    return true;
};  // semicolon here.
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Put semicolons at the end of function declarations.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
function foo() {
    return true;
}  // no semicolon here.
```

### Quotes

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Whether you prefer single or double shouldn't matter, there is no difference in how JavaScript parses them. What **ABSOLUTELY** MUST be enforced is consistency. **Never mix quotes in the same project. Pick one style and stick with it.**

### Block statements

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Indent enclosed statements with four more spaces.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
if (condition) {
    firstAction();  // Add 4 more spaces within the body of compound statement.
    secondAction();
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
if (condition) {
firstAction();
secondAction();
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Place "{" (left curly brace) at the end of the line that begins the compound statement.
Place "}" (right curly brace) at the begin of new line and indent it to align with the beginning of the line containing the matching "{" (left curly brace).
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
if (condition) {
    firstAction();
    secondAction();
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
if (condition)
{
    firstAction();
    secondAction();
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Braces should be used around all statements, even single statements, when they are part of a control structure, such as an "if" or "for" statement. This makes it easier to add statements without accidentally introducing bugs.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
if (condition) {
    action();
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
if (condition) { action(); }
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Put else clause at the same line as closing "}" bracket of "if" statement.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
if (valuesToPush instanceof Array) {
    array.push.apply(array, valuesToPush);
} else {
    for (var i = 0, j = valuesToPush.length; i < j; i++) {
        array.push(valuesToPush[i]);
    }
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
if (valuesToPush instanceof Array) {
    array.push.apply(array, valuesToPush);
}
else {
    for (var i = 0, j = valuesToPush.length; i < j; i++) {
        array.push(valuesToPush[i]);
    }
}
```

## Naming Guidelines

### Naming

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Write all names in US English.
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use following naming rules:
* Function Names: camelCase
* Constructor Functions: PascalCase
* Variable Names: camelCase
* Enum Names: PascalCase
* Enum Values: SCREAMING_CAPS
* Method Names: camelCase
* Constants: SCREAMING_CAPS
* Namespace Names: PascalCase
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
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
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Group related constants within a single object created as a holder for constants, emulating an enumerated type.

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
var NodeTypes = {
    ELEMENT: 1,
    DOCUMENT: 2
};
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Use abbreviations
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
createEl, cls, cmpStrs
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
createElement, class, compareStrings
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Capitalize both letters of 2-letter acronyms.

Capitalization rules should not conflict with general naming guidelines. If first letter of acronym should be small – do not apply capitalization to the rest of the letters.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
function getIOResult() {
 
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
function getIoResult() {
 
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Capitalize only first letter of acronyms longer than 2 letters.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
var formattedXml;
 
function getHtml() {
 
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
var formattedXML;
 
function getHTML() {
 
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Apply capitalization rules of acronyms for non-acronyms even if they look alike.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
ID, OK, PI
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
Id, Ok, Pi
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Prefixing private properties and methods with leading underscore.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
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
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Name Boolean properties and variables with an affirmative phrase (canSeek instead of cantSeek). Optionally, you can also prefix Boolean properties with "is," "can," or "has," but only where it adds value.
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use plural to name collections.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
Items, Entities, Errors
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Use negated boolean variable names.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
isNotError, isNotFound
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Put "Error" suffix at the end of Exception classes.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
NotFoundError, OutOfRangeError, BusinessLogicError
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Methods returning an object MAY be named after what they return, and methods returning void after what they do.

## Declaration Guidelines

### Variable declaration

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Declare variable with "var" statement before actually using it.

Keep in mind that if you assign value to non-existing variable it automatically becomes global, that's why you should carefully follow aforementioned rule all the time.

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use multiple "var" statements if you need to declare multiple variables.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
function f() {
    var a = 1;
    var b = 2;
    var c = a + b;
 
    return c / 2;
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Combine variable declarations under single "var statement".
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
function f() {
    var a = 1,
        b = 2,
        c = a + b;
 
    return c / 2;
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Declare variables close to where they are actually used.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
function f(items) {
    var numberOfItems = items.length;
 
    for (var i = 0; i < numberOfItems; i++) {
        var item = items[i];
        item.sell();
    }
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Place all variable declarations at the beginning of the function.

While many practitioners strongly encourage this style it serves no purpose for readability and modularity of your code, and primarily aimed to shield developers from nuances of script execution.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
function f(items) {
    var numberOfItems = items.length;
    var item;
    var i;
 
    for (i = 0; i < numberOfItems; i++) {
        item = items[i];
        item.sell();
    }
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
function f(items) {
    var numberOfItems = items.length,
        item,
        i;
 
    for (i = 0; i < numberOfItems; i++) {
        item = items[i];
        item.sell();
    }
}
```

### Function declarations

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Put space between the name of a function and the "(" (left parenthesis) of its parameter list.
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Put one space between the ")" (right parenthesis) and the "{" (left curly brace) that begins the statement body.
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Align "}" (right curly brace) with the line containing the beginning of the declaration of the function.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
function f() {
 
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Put one space between the word function and the "(" (left parenthesis).
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
div.addEventListener('click', function (e) {
    return false;
});
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Use function declarations within block

While most script engines support Function Declarations within blocks it is not part of ECMAScript (see ECMA-262, clause 13 and 14). Worse implementations are inconsistent with each other and with future EcmaScript proposals. ECMAScript only allows for Function Declarations in the root statement list of a script or function. Instead use a variable initialized with a Function Expression to define a function within a block:
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
if (x) {
  function foo() {}
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
if (x) {
    var foo = function () {};
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: When defining IIFE, put function call outside of parenthesis.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
(function () {
    var x = 10;
})();
 Wrong
(function () {
    var x = 10;
}());
```

## Functional Guidelines

###Strict Mode

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use strict execution mode.
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Apply strict mode to a whole file.
Instead, apply strict mode selectively at function level.

Applying strict mode to whole file can potentially brake your application after script minification.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
'use strict';
 
function Person() {
    this.firstName= 'Douglas';
    this.lastName = 'Crockford';
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
(function () {
    'use strict';
 
    function Person() {
        this.firstName = 'Douglas';
        this.lastName = 'Crockford';
    }
})();
```

### Eval

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Use Eval for application level activities (parsing JSON responses, type casting, e.t.c).

Improper use of Eval leads to security, maintainability and performance issues.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
var request = new XMLHttpRequest();
 
request.addEventListener('load', function () {
    var jsonData = this.responseText;
    var data = eval('(' + jsonData + ')');
});
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
var request = new XMLHttpRequest();
 
request.addEventListener('load', function () {
    var jsonData = this.responseText;
    var data = JSON.parse(jsonData);
});
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
var request = new XMLHttpRequest();
request.responseType = 'json';
 
request.addEventListener('load', function () {
    var data = this.response;
});
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
var numberAsString = '10';
var number = eval(numberAsString);
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
var numberAsString = '10';
var number = Number(numberAsString);
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Use any forms of implicit Eval to satisfy previous guideline.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
setTimeout('alert("Implicit eval");', 0);
setInterval('alert("Implicit eval");', 0);
(new Function('alert("Implicit eval");'))();
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Wise use of Eval for framework level activities, when it is not possible to avoid it.

Almost all of the proper use cases of Eval fall under situation where you need to execute 3rd party code but for some reasons it's not technically feasible to load with `<script>` tag.

### Undefined

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Treat undefined as representation of system-level, unexpected, or error-like absence of value and null as representation of program-level, normal, or expected absence of value.
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Assign undefined directly to represent the intentional absence of any object value. Assign null or semantically default value instead.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
function ContestFilter() {
    this.contestId = undefined;
    this.status = undefined;
    this.duration = undefined;
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
function ContestFilter() {
    this.contestId = null;
    this.status = null;
    this.duration = null;
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
function ContestFilter() {
    this.contestId = 0;
    this.status = null;
    this.duration = 0;
}
```

### Modularity

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Wrapping script files into IIFE to limit its visibility and protect from outer impact.

This technique facilitates next benefits:
* Allows encapsulating implementation details into local variables and exposing publicly visible API relying on closures
* Provides convenient point for application of strict mode
* Allows to protect your script from outer environment by capturing dependencies as parameters
 
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
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
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Artificially introduce IIFE when file is already wrapped with a function.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
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
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
define(function (require) {
    'use strict';
 
    var shirt = require("./shirt");
 
    return {
        logTheShirt: function () {
            console.log("color: " + shirt.color + ", size: " + shirt.size);
        }
    };
});
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Group related functionality into namespaces.

JavaScript has no notion of namespaces, but you can emulate them with nested objects.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
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
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
function Person(firstName, lastName) {
    this.firstName = firstName;
    this.lastName = lastName;
}
 
function Activity(name) {
    this.name = name;
}
```

### Exceptions

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use custom exceptions to indicate exceptional flow of execution.
 	
#### Declaration:
```javascript
function OutOfRangeError(value) {
    this.message = 'Value ' + value + ' is out of range.';
}
 
OutOfRangeError.prototype = new Error();
OutOfRangeError.prototype.constructor = OutOfRangeError;
```

#### Usage:
```javascript
function f(x) {
    if (x < 0) {
        throw new OutOfRangeError('x');
    }
 
    return x * 2;
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Combine error code or inject error member into return value of a function.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
function f(x) {
    if (x < 0) {
        return false;
    }
 
    return x * 2;
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
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
```

### {} and []

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: 
* Use {} instead of new Object().
* Use [] instead of new Array().

### Wrapper objects for primitive types

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Use wrapper objects for primitive types.

Once you wrap real primitive type into object it automatically becomes truthy in logical comparisons. It may lead to hard to track bugs and unpredictable errors in application logic.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
var x = new Boolean(false);
 
if (x) {
    alert('hi');  // Shows 'hi'.
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Use constructors of wrapper objects for type casting.

This guideline does not prohibit use of more succinct forms of typecasting. Treat them all equally, but keep in mind that additionally, primitive constructors are capable of unboxing wrapped primitives into real values.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
var x = Boolean(0);
 
if (x) {
    alert('hi');  // This will never be alerted.
}
 
typeof Boolean(0) === 'boolean';
typeof new Boolean(0) === 'object';
```

### Delete

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Setting property to null instead of deleting it.

In modern JavaScript engines, changing the number of properties on an object is much slower than reassigning the values. The delete keyword should be avoided except when it is necessary to remove a property from an object's iterated list of keys, or to change the result of if (key in obj).
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
Foo.prototype.dispose = function () {
    this.property = null;
};
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
Foo.prototype.dispose = function () {
    delete this.property;
};
```

### With() {}

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Use "with" statement.

Using "with" hides the semantics of your program. Because the object of the "with" statement can have properties that collide with local variables, it can drastically change the meaning of your program.

### For-in loop

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use it only for iterating over keys in an object.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
for (var key in person) {
    var value = person[key];
    console.log(key + ': ' + value);
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Use it to loop over the elements in an Array.

This is very error prone because it does not loop from 0 to length - 1 but over all the present keys in the object and its prototype chain.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```javascript
var data = [0, 25, 25, 45, 123, 10];
 
for (var key in data) {
    var value = data[key];
    console.log(key + ': ' + value);
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
var data = [0, 25, 25, 45, 123, 10];
 
for (var i = 0; i < data.length; i++) {
    var value = data[i];
    console.log(key + ': ' + value);
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Filtering iterated properties with hasOwnProperty.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
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
```

### === and !== operators
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Prefer strict comparisons ("===" and "!==").
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Using regular comparisons where implicit type casting is desirable.
 	
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```javascript
function f(x) {
    if (x == null) { // Checks whether x is null or undefined.
        return 0;
    }
 
    return x;
}
```

### Modifying prototypes of built-in objects

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Modify prototype of host and native objects.

Modifying prototypes of Object, Array, Function and other built-ins is dangerous and may lead to hard to debug issues in production and should be avoided.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Write extensions in a form of utility objects instead of extending prototypes of built-in objects.

## Q&A

**"Why do you recommend declaring variables close to where they are actually used, while many practitioners, including Douglas Crockford and David Flanagan, recommend declaring all of them at the beginning of the function?"**

There is no community ratified way of declaring variables. Followers of Crockford's style claim that, in absence of block level scoping for variables, this style protects developers from nuances of "hoisting". We strongly believe that this type of errors is rare even among beginner programmers, but has negative impact on locality of variables. Despite the fact that only functions create lifetime boundaries for variables, there is always a "psychic weight" that variables put on programmers. The best way to avoid "psychic weight" is to declare variables close to where they are actually used. We believe that in this particular case, understandability of the code outweighs chances of possible errors. 


**"Why do you recommend using individual var statements for multiple variable declarations, while many practitioners, including David Flanagan, recommend combining all of them under single var statement?"**

Former approach introduces additional maintenance cost by making programmer carefully watching for , and ;. By using individual var statements you can release your brain from remembering and watching for punctuation instead of doing useful programming. 


**"One of the guidelines says that Pi should be written like this, and not PI or pi, but this violates general naming guidelines for constants."** 

What capitalization guidelines really say is that you should apply appropriate capitalization as stated in section "Naming" without violating general naming guidelines. If in your code pi is a constant – you should write like PI, because general naming guidelines have higher order of precedence then capitalization guidelines. But there are cases where Pi is not a constant, for example method called computePi().
