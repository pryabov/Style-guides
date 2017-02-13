# Java Script style-guide

## Code Formatting Guidelines

### **Indentation**

![Image of Yaktocat](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use four spaces for indentation.

![Image of Yaktocat](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Try to keep lines to 120 characters or less.

Think of this guideline as a recommendation not a rule. Do not sacrifice expressiveness in a favor of line length.
 
![Image of Yaktocat](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Mix indentation styles within a project.

![Image of Yaktocat](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Enforce indentation rules at compile time with JSHint.

How to configure? [Awaits to be discussed]
 
![Image of Yaktocat](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: When wrapping lines, indent to line up with a related item on the previous line.

Right
 
```javascript 
var result = prompt(
    aMessage,
    aInitialValue,
    aCaption);
```
    
![Image of Yaktocat](https://github.com/AleksandrCh/Style-guides/blob/master/images/like20.png?raw=true) Right
 
```javascript
$('.navigation-menu')
    .find('li')
    .css('background-color', 'red')
    .show();
```
