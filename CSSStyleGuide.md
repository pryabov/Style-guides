# CSS style-guide

### General

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Always use US-English in CSS.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
.color-picker, .text-center
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
.colour-picker, .text-centre
```

### Indentation

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use four spaces to indent properties in a body of the ruleset.
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Rule sets for media queries and keyframes should be indented one level in.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
@media all and (max-width: 768px) {
    .color-picker {
        color: #fff;
    }
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
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

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Keeping lines to 120 characters or less

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Put multiple CSS properties on the same line, put them on a new line instead.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
input[type="text"] { 
    display: none;
    background-color: red;
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
input[type="text"] { display: none; background-color: red; }
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Arrange long, comma-separated property values - such as collections of gradients or shadows - across multiple lines.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
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
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
.selector {
    background-image: linear-gradient(#fff, #ccc),
                      linear-gradient(#f3c, #4ec);
    box-shadow: 1px 1px 1px #000,
                2px 2px 1px 1px #ccc inset;
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use one discrete selector per line in multi-selector rulesets.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
a,
span,
h1 { 
    margin: 0;
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
a, span, h1 {
    margin: 0;
}
```

### Quotes

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use double quotation marks for attribute selectors and property values.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
input[type="text"] { 
    content: "Text";
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
input[type='text'] {
    content: 'Text';
}
```
 
### Whitespacing

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Separate each ruleset by a blank line.
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Leave opening curly brace on the same line with selector portion of the Rule Set.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
input[type="text"] { 
    content: "Text";
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
input[type="text"] { content: "Text"; }
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
input[type="text"] 
{ 
    content: "Text";
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use a space after a property name’s colon.

Always use a single space between property and value (but no space between property and colon) for consistency reasons.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
input[type="text"] { 
    display: none;
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
input[type="text"] {
    display : none;
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
input[type="text"] {
    display:none
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use a space between the last selector and the declaration block.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
input[type="text"] { 
    content: "Text";
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
input[type="text"]{
    content: "Text";
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Pad parentheses with spaces.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
@media all and (max-width: 620px) {
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
@media all and ( max-width: 620px ) {
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Group style sheet sections together by using comments. Separate sections with new lines.

For large projects it is preferable to keep reusable modules in separate CSS files, so no commenting is usually necessary.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
/* Header */
 
#adw-header {}
 
/* Footer */
 
#adw-footer {}
 
/* Gallery */
 
.adw-gallery {}
```

### Semicolon

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use a semicolon after every declaration.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
input[type="text"] { 
    display: none;
    background-color: black;
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
input[type="text"] {
    display: none;
    background-color: black
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
input[type="text"] {
    display: none
    background-color: black
}
```

### Colon and double colon

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use double colon for pseudo-elements and single colon for pseudo-classes when all targeting platforms support double-colon notation (typically IE > 8).
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use single colon for pseudo-elements and pseudo-classes when at least one of the targeting platforms doesn't support double colon notation (typically IE < 9).

### Grouping

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Group and/or sort CSS properties in a specific order.

This process can be automated with tools like CSSComb.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
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

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Group media queries by media after corresponding styles.
 
### Shorthands

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Put CSS unit specification after "0" values, unless necessary, such as with transition-duration.
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use following notations to define colors: hex, rgba, hsl, hsla notations, while rgb and shorthand notations are disallowed.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
#aaa, rgba(255, 115, 0, 0.3), hsl(120,100%,50%), hsla(120,100%,50%,0.3)
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
rgb(255, 113, 80), white, black
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Use shorthand hex values.
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use lowercase hex values.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
#aaaaaa, #11ffcc, #23c1f2
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
#AAAAAA, #11FFCC, #23C1F2
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use shorthand property when you need to fill all of the values of CSS property group.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
h1 { 
    margin: 10px 0 20px 0
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
h1 {
    margin-top: 10px;
    margin-right: 0;
    margin-bottom: 20px;
    margin-left: 0;
}
```

### Naming guidelines

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use meaningful or generic ID and class names.

Instead of presentational or cryptic names, always use ID and class names that reflect the purpose of the element in question, or that are otherwise generic.
Names that are specific and reflect the purpose of the element should be preferred as these are most understandable and the least likely to change.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
/* Recommended: specific */
#gallery {}
#login {}
.video {}
 
/* Recommended: generic */
.aux {}
.alt {}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
/* Not recommended: meaningless */
#yee-1901 {}
 
/* Not recommended: presentational */
.button-green {}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Use presentational names for id and class names.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
.button-green {
    color: green;
}

.width-127px {
    width: 127px;
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Maintain a glossary of abbreviations used for id and class names.
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Use hyphen-delimited case for id and class names.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
#nav-section, .media-info, .tab-body
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
#navSection, .MediaInfo, .tabbody
```

### Comments

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Avoid heavy commenting stylesheets.

CSS by its nature is declarative language, so usually no comments are required at all.

### Functional Guidelines

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Avoid using ids, except for general layout elements.

Use of ids limits reusability and introduces specificity issues.

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Write unprefixed properties after prefixed ones.

By doing this you will make sure, that browser will pick standardized property if possible.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
.selector {
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
}
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
.selector {
    box-sizing: border-box;
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
}
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Use "magic numbers".

Magic number is a circumstantial number, or number with purpose of fixing symptoms, not real issues, and as such, we should not rely on it.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Write cross-browser CSS as much as possible.

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Falling back to conditional comments and browser specific hacks, if and only if it is technically infeasible to achieve desirable behavior in cross-browser manner. 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Using Normalize.css to normalize inconsistencies in user-agent styles. 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Allow parent container to collapse when there is a content within.

By allowing container to collapse, you make your surrounding markup easy to flow in unpredictable manner.
 
![](/images/overflow-float.png)

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Use "!important" to overcome selector specificity issues when it is possible to avoid it.

However, there are cases where !important is allowed. For example, state styles.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Prefix selectors with unique prefix, when you have a need to isolate component or whole application from outer environment.
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Over-qualify selectors with non-semantic parts.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
.selector
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
div.selector
```

![](https://github.com/AleksandrCh/Style-guides/blob/master/images/consider25.png?raw=true) CONSIDER: Using grunt-autoprefixer or similar tool to easily manage necessary browser prefixes.
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/right25.png?raw=true) DO: Attempt to remove code before adding more, when fixing an issue.
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrong25.png?raw=true) DO NOT: Tie selectors to particular DOM structure. Introduce semantic parts instead.
 
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/rightmark20.png?raw=true)
```css
.file-upload .file-upload-info .file-upload-info-title
```
![](https://github.com/AleksandrCh/Style-guides/blob/master/images/wrongmark20.png?raw=true)
```css
div.file-upload div:nth-child(2) > span
```
