# CSS style-guide

### General

![](/images/right25.png) DO: Always use US-English in CSS.
 
![](/images/rightmark20.png)
```css
.color-picker, .text-center
```
![](/images/wrongmark20.png)
```css
.colour-picker, .text-centre
```

### Indentation

![](/images/right25.png) DO: Use four spaces to indent properties in a body of the ruleset.
![](/images/right25.png) DO: Rule sets for media queries and keyframes should be indented one level in.
 
![](/images/rightmark20.png)
```css
@media all and (max-width: 768px) {
    .color-picker {
        color: #fff;
    }
}
```
![](/images/rightmark20.png)
```css
@keyframes slide-up {
    0%: {
        top: 0;
    }
    100%: {
        top: 100%;
    }
}
```

![](/images/consider25.png) CONSIDER: Keeping lines to 120 characters or less

![](/images/wrong25.png) DO NOT: Put multiple CSS properties on the same line, put them on a new line instead.
 
![](/images/rightmark20.png)
```css
input[type="text"] { 
    display: none;
    background-color: red;
}
```
![](/images/wrongmark20.png)
```css
input[type="text"] { display: none; background-color: red; }
```

![](/images/right25.png?raw=true) DO: Arrange long, comma-separated property values - such as collections of gradients or shadows - across multiple lines.
 
![](/images/rightmark20.png)
```css
.selector {
    background-image:
        linear-gradient(#fff, #ccc),
        linear-gradient(#f3c, #4ec);
    box-shadow:
        1px 1px 1px #000,
        2px 2px 1px 1px #ccc inset;
}
```
![](/images/wrongmark20.png)
```css
.selector {
    background-image: linear-gradient(#fff, #ccc),
                      linear-gradient(#f3c, #4ec);
    box-shadow: 1px 1px 1px #000,
                2px 2px 1px 1px #ccc inset;
}
```

![](/images/right25.png) DO: Use one discrete selector per line in multi-selector rulesets.
 
![](/images/rightmark20.png)
```css
a,
span,
h1 { 
    margin: 0;
}
```
![](/images/wrongmark20.png)
```css
a, span, h1 {
    margin: 0;
}
```

### Quotes

![](/images/right25.png) DO: Use double quotation marks for attribute selectors and property values.
 
![](/images/rightmark20.png)
```css
input[type="text"] { 
    content: "Text";
}
```
![](/images/wrongmark20.png)
```css
input[type='text'] {
    content: 'Text';
}
```
 
### Whitespacing

![](/images/right25.png) DO: Separate each ruleset by a blank line.
![](/images/right25.png) DO: Leave opening curly brace on the same line with selector portion of the Rule Set.
 
![](/images/rightmark20.png)
```css
input[type="text"] { 
    content: "Text";
}
```
![](/images/wrongmark20.png)
```css
input[type="text"] { content: "Text"; }
```
![](/images/wrongmark20.png)
```css
input[type="text"] 
{ 
    content: "Text";
}
```

![](/images/right25.png) DO: Use a space after a property name’s colon.

Always use a single space between property and value (but no space between property and colon) for consistency reasons.
 
![](/images/rightmark20.png)
```css
input[type="text"] { 
    display: none;
}
```
![](/images/wrongmark20.png)
```css
input[type="text"] {
    display : none;
}
```
![](/images/wrongmark20.png)
```css
input[type="text"] {
    display:none
}
```

![](/images/right25.png) DO: Use a space between the last selector and the declaration block.
 
![](/images/rightmark20.png)
```css
input[type="text"] { 
    content: "Text";
}
```
![](/images/wrongmark20.png)
```css
input[type="text"]{
    content: "Text";
}
```

![](/images/wrong25.png) DO NOT: Pad parentheses with spaces.
 
![](/images/rightmark20.png)
```css
@media all and (max-width: 620px) {
```
![](/images/wrongmark20.png)
```css
@media all and ( max-width: 620px ) {
```

![](/images/right25.png) DO: Group style sheet sections together by using comments. Separate sections with new lines.

For large projects it is preferable to keep reusable modules in separate CSS files, so no commenting is usually necessary.
 
![](/images/rightmark20.png)
```css
/* Header */
 
#adw-header {}
 
/* Footer */
 
#adw-footer {}
 
/* Gallery */
 
.adw-gallery {}
```

### Semicolon

![](/images/right25.png) DO: Use a semicolon after every declaration.
 
![](/images/rightmark20.png)
```css
input[type="text"] { 
    display: none;
    background-color: black;
}
```
![](/images/wrongmark20.png)
```css
input[type="text"] {
    display: none;
    background-color: black
}
```
![](/images/wrongmark20.png)
```css
input[type="text"] {
    display: none
    background-color: black
}
```

### Colon and double colon

![](/images/right25.png?raw=true) DO: Use double colon for pseudo-elements and single colon for pseudo-classes when all targeting platforms support double-colon notation (typically IE > 8).
![](/images/right25.png?raw=true) DO: Use single colon for pseudo-elements and pseudo-classes when at least one of the targeting platforms doesn't support double colon notation (typically IE < 9).

### Grouping

![](/images/right25.png) DO: Group and/or sort CSS properties in a specific order.

This process can be automated with tools like CSSComb.
 
![](/images/rightmark20.png)
```css
.selector {
    /* Positioning */
    position: absolute;
    z-index: 10;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
 
    /* Display */
    display: inline-block;
    overflow: hidden;
 
    /* Box Model & Flex Box Model */
    box-sizing: border-box;
    width: 100px;
    height: 100px;
    padding: 10px;
    border: 10px solid #333;
    margin: 10px;
 
    /* Visual */
    background: #000;
    color: #fff;
    text-align: right;   
 
    /* Font */
    font-family: sans-serif;
    font-size: 16px;
}
```

![](/images/right25.png) DO: Group media queries by media after corresponding styles.
 
### Shorthands

![](/images/wrong25.png) DO NOT: Put CSS unit specification after "0" values, unless necessary, such as with transition-duration.
![](/images/right25.png) DO: Use following notations to define colors: hex, rgba, hsl, hsla notations, while rgb and shorthand notations are disallowed.
 
![](/images/rightmark20.png)
```css
#aaa, rgba(255, 115, 0, 0.3), hsl(120,100%,50%), hsla(120,100%,50%,0.3)
```
![](/images/wrongmark20.png)
```css
rgb(255, 113, 80), white, black
```

![](/images/wrong25.png) DO NOT: Use shorthand hex values.
![](/images/right25.png) DO: Use lowercase hex values.
 
![](/images/rightmark20.png)
```css
#aaaaaa, #11ffcc, #23c1f2
```
![](/images/wrongmark20.png)
```css
#AAAAAA, #11FFCC, #23C1F2
```

![](/images/right25.png) DO: Use shorthand property when you need to fill all of the values of CSS property group.
 
![](/images/rightmark20.png)
```css
h1 { 
    margin: 10px 0 20px 0
}
```
![](/images/wrongmark20.png)
```css
h1 {
    margin-top: 10px;
    margin-right: 0;
    margin-bottom: 20px;
    margin-left: 0;
}
```

### Naming guidelines

![](/images/right25.png) DO: Use meaningful or generic ID and class names.

Instead of presentational or cryptic names, always use ID and class names that reflect the purpose of the element in question, or that are otherwise generic.
Names that are specific and reflect the purpose of the element should be preferred as these are most understandable and the least likely to change.
 
![](/images/rightmark20.png)
```css
/* Recommended: specific */
#gallery {}
#login {}
.video {}
 
/* Recommended: generic */
.aux {}
.alt {}
```
![](/images/wrongmark20.png)
```css
/* Not recommended: meaningless */
#yee-1901 {}
 
/* Not recommended: presentational */
.button-green {}
```

![](/images/wrong25.png) DO NOT: Use presentational names for id and class names.
 
![](/images/wrongmark20.png)
```css
.button-green {
    color: green;
}

.width-127px {
    width: 127px;
}
```

![](/images/right25.png) DO: Maintain a glossary of abbreviations used for id and class names.
![](/images/right25.png) DO: Use hyphen-delimited case for id and class names.
 
![](/images/rightmark20.png)
```css
#nav-section, .media-info, .tab-body
```
![](/images/wrongmark20.png)
```css
#navSection, .MediaInfo, .tabbody
```

### Comments

![](/images/right25.png) DO: Avoid heavy commenting stylesheets.

CSS by its nature is declarative language, so usually no comments are required at all.

### Functional Guidelines

![](/images/right25.png) DO: Avoid using ids, except for general layout elements.

Use of ids limits reusability and introduces specificity issues.

![](/images/right25.png) DO: Write unprefixed properties after prefixed ones.

By doing this you will make sure, that browser will pick standardized property if possible.
 
![](/images/rightmark20.png)
```css
.selector {
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
}
```
![](/images/wrongmark20.png)
```css
.selector {
    box-sizing: border-box;
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
}
```

![](/images/wrong25.png) DO NOT: Use "magic numbers".

Magic number is a circumstantial number, or number with purpose of fixing symptoms, not real issues, and as such, we should not rely on it.
 
![](/images/right25.png) DO: Write cross-browser CSS as much as possible.

![](/images/consider25.png) CONSIDER: Falling back to conditional comments and browser specific hacks, if and only if it is technically infeasible to achieve desirable behavior in cross-browser manner. 
![](/images/consider25.png) CONSIDER: Using Normalize.css to normalize inconsistencies in user-agent styles. 
![](/images/wrong25.png) DO NOT: Allow parent container to collapse when there is a content within.

By allowing container to collapse, you make your surrounding markup easy to flow in unpredictable manner.
 
![](/images/overflow-float.png)

![]r/images/wrong25.png) DO NOT: Use "!important" to overcome selector specificity issues when it is possible to avoid it.

However, there are cases where !important is allowed. For example, state styles.
 
![](/images/right25.png) DO: Prefix selectors with unique prefix, when you have a need to isolate component or whole application from outer environment.
![](/images/wrong25.png) DO NOT: Over-qualify selectors with non-semantic parts.
 
![](/images/rightmark20.png)
```css
.selector
```
![](/images/wrongmark20.png)
```css
div.selector
```

![](/images/consider25.png) CONSIDER: Using grunt-autoprefixer or similar tool to easily manage necessary browser prefixes.
![](/images/right25.png) DO: Attempt to remove code before adding more, when fixing an issue.
![](/images/wrong25.png) DO NOT: Tie selectors to particular DOM structure. Introduce semantic parts instead.
 
![](/images/rightmark20.png)
```css
.file-upload .file-upload-info .file-upload-info-title
```
![](/images/wrongmark20.png)
```css
div.file-upload div:nth-child(2) > span
```
