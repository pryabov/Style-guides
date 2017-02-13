# Java Script style-guide

## Code Formatting Guidelines

### **Indentation**

DO: Use four spaces for indentation.

#### CONSIDER:
Try to keep lines to 120 characters or less.
Think of this guideline as a recommendation not a rule. Do not sacrifice expressiveness in a favor of line length.
 
DO NOT: Mix indentation styles within a project.

#### CONSIDER:
Enforce indentation rules at compile time with JSHint.
How to configure? [Awaits to be discussed]
 
#### DO
When wrapping lines, indent to line up with a related item on the previous line.

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
