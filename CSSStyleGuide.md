# CSS style-guide

## General
DO
Icon
Always use US-English in CSS.
 
 Right
.color-picker, .text-center
 Wrong
.colour-picker, .text-centre
Indentation
DO
Icon
Use four spaces to indent properties in a body of the ruleset.
DO
Icon
Rule sets for media queries and keyframes should be indented one level in.
 
 Right
@media all and (max-width: 768px) {
    .color-picker {
        color: #fff;
    }
}
 Right
@keyframes slide-up {
    0%: {
        top: 0;
    }
    100%: {
        top: 100%;
    }
}
CONSIDER
Icon
Keeping lines to 120 characters or less
DO NOT
Icon
Put multiple CSS properties on the same line, put them on a new line instead.
 
 Right
input[type="text"] { 
    display: none;
    background-color: red;
}
 Wrong
input[type="text"] { display: none; background-color: red; }
DO
Icon
Arrange long, comma-separated property values - such as collections of gradients or shadows - across multiple lines.
 
 Right
.selector {
    background-image:
        linear-gradient(#fff, #ccc),
        linear-gradient(#f3c, #4ec);
    box-shadow:
        1px 1px 1px #000,
        2px 2px 1px 1px #ccc inset;
}
 Wrong
.selector {
    background-image: linear-gradient(#fff, #ccc),
                      linear-gradient(#f3c, #4ec);
    box-shadow: 1px 1px 1px #000,
                2px 2px 1px 1px #ccc inset;
}
DO
Icon
Use one discrete selector per line in multi-selector rulesets.
 
 Right
a,
span,
h1 { 
    margin: 0;
}
 Wrong
a, span, h1 {
    margin: 0;
}
Quotes
DO
Icon
Use double quotation marks for attribute selectors and property values.
 
 Right
input[type="text"] { 
    content: "Text";
}
 Wrong
input[type='text'] {
    content: 'Text';
}
 
Whitespacing
DO
Icon
Separate each ruleset by a blank line.
DO
Icon
Leave opening curly brace on the same line with selector portion of the Rule Set.
 
 Right
input[type="text"] { 
    content: "Text";
}
 Wrong
input[type="text"] { content: "Text"; }
 Wrong
input[type="text"] 
{ 
    content: "Text";
}
DO
Icon
Use a space after a property name’s colon.
Always use a single space between property and value (but no space between property and colon) for consistency reasons.
 
 Right
input[type="text"] { 
    display: none;
}
 Wrong
input[type="text"] {
    display : none;
}
 Wrong
input[type="text"] {
    display:none
}
DO
Icon
Use a space between the last selector and the declaration block.
 
 Right
input[type="text"] { 
    content: "Text";
}
 Wrong
input[type="text"]{
    content: "Text";
}
DO NOT
Icon
Pad parentheses with spaces.
 
 Right
@media all and (max-width: 620px) {
 Wrong
@media all and ( max-width: 620px ) {
DO
Icon
Group style sheet sections together by using comments. Separate sections with new lines.
For large projects it is preferable to keep reusable modules in separate CSS files, so no commenting is usually necessary.
 
 Right
/* Header */
 
#adw-header {}
 
/* Footer */
 
#adw-footer {}
 
/* Gallery */
 
.adw-gallery {}
Semicolon
DO
Icon
Use a semicolon after every declaration.
 
 Right
input[type="text"] { 
    display: none;
    background-color: black;
}
 Wrong
input[type="text"] {
    display: none;
    background-color: black
}
 Wrong
input[type="text"] {
    display: none
    background-color: black
}
Colon and double colon
DO
Icon
Use double colon for pseudo-elements and single colon for pseudo-classes when all targeting platforms support double-colon notation (typically IE > 8).
DO
Icon
Use single colon for pseudo-elements and pseudo-classes when at least one of the targeting platforms doesn't support double colon notation (typically IE < 9).
Grouping
DO
Icon
Group and/or sort CSS properties in a specific order.
This process can be automated with tools like CSSComb.
 
 Right
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
DO
Icon
Group media queries by media after corresponding styles.
 
Shorthands
DO NOT
Icon
Put CSS unit specification after "0" values, unless necessary, such as with transition-duration.
DO
Icon
Use following notations to define colors: hex, rgba, hsl, hsla notations, while rgb and shorthand notations are disallowed.
 
 Right
#aaa, rgba(255, 115, 0, 0.3), hsl(120,100%,50%), hsla(120,100%,50%,0.3)
 Wrong
rgb(255, 113, 80), white, black
DO NOT
Icon
Use shorthand hex values.
DO
Icon
Use lowercase hex values.
 
 Right
#aaaaaa, #11ffcc, #23c1f2
 Wrong
#AAAAAA, #11FFCC, #23C1F2
DO
Icon
Use shorthand property when you need to fill all of the values of CSS property group.
 
 Right
h1 { 
    margin: 10px 0 20px 0
}
 Wrong
h1 {
    margin-top: 10px;
    margin-right: 0;
    margin-bottom: 20px;
    margin-left: 0;
}
Naming guidelines
DO
Icon
Use meaningful or generic ID and class names.
Instead of presentational or cryptic names, always use ID and class names that reflect the purpose of the element in question, or that are otherwise generic.
Names that are specific and reflect the purpose of the element should be preferred as these are most understandable and the least likely to change.
 
 Right
/* Recommended: specific */
#gallery {}
#login {}
.video {}
 
/* Recommended: generic */
.aux {}
.alt {}
 Wrong
/* Not recommended: meaningless */
#yee-1901 {}
 
/* Not recommended: presentational */
.button-green {}
DO NOT
Icon
Use presentational names for id and class names.
 
 Wrong
.button-green {
    color: green;
}
 
.width-127px {
    width: 127px;
}
DO
Icon
Maintain a glossary of abbreviations used for id and class names.
DO
Icon
Use hyphen-delimited case for id and class names.
 
 Right
#nav-section, .media-info, .tab-body
 Wrong
#navSection, .MediaInfo, .tabbody
Comments
DO
Icon
Avoid heavy commenting stylesheets.
CSS by its nature is declarative language, so usually no comments are required at all.
Functional Guidelines
DO
Icon
Avoid using ids, except for general layout elements.
Use of ids limits reusability and introduces specificity issues.  
DO
Icon
Write unprefixed properties after prefixed ones.
By doing this you will make sure, that browser will pick standardized property if possible.
 
 Right
.selector {
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
}
 Wrong
.selector {
    box-sizing: border-box;
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
}
DO NOT
Icon
Use "magic numbers".
Magic number is a circumstantial number, or number with purpose of fixing symptoms, not real issues, and as such, we should not rely on it.
 
DO
Icon
Write cross-browser CSS as much as possible.
CONSIDER
Icon
Falling back to conditional comments and browser specific hacks, if and only if it is technically infeasible to achieve desirable behavior in cross-browser manner. 
CONSIDER
Icon
Using Normalize.css to normalize inconsistencies in user-agent styles. 
DO NOT
Icon
Allow parent container to collapse when there is a content within.
By allowing container to collapse, you make your surrounding markup easy to flow in unpredictable manner.
 
 

DO NOT
Icon
Use "!important" to overcome selector specificity issues when it is possible to avoid it.
However, there are cases where !important is allowed. For example, state styles.
 
DO
Icon
Prefix selectors with unique prefix, when you have a need to isolate component or whole application from outer environment.
DO NOT
Icon
Over-qualify selectors with non-semantic parts.
 
 Right
.selector
 Wrong
div.selector
CONSIDER
Icon
 Using grunt-autoprefixer or similar tool to easily manage necessary browser prefixes.
DO
Icon
Attempt to remove code before adding more, when fixing an issue.
DO NOT
Icon
Tie selectors to particular DOM structure. Introduce semantic parts instead.
 
 Right
.file-upload .file-upload-info .file-upload-info-title
 Wrong
div.file-upload div:nth-child(2) > span
 
