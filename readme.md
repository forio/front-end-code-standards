# Forio Front-End Style Guide

This document was inspired by a combination of works:
 * [Douglas Crockford - Code Conventions for the JavaScript Programming Language](http://javascript.crockford.com/code.html)
 * [Google - Javascript Style Guide](http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml)
 * [Google - HTML/CSS Style Guide](http://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml#Indentation)
 * [HTML Boilerplate - Documentation](http://html5boilerplate.com/docs)

# Table of Contents

### 1.0 [General](https://github.com/forio/front-end-code-standards#10-general)
* 1.1 [Helpful Resources](https://github.com/forio/front-end-code-standards#11-helpful-resources)
* 1.2 [Filenames](https://github.com/forio/front-end-code-standards#12-filenames)
* 1.3 [Project Structure](https://github.com/forio/front-end-code-standards#13-project-structure)
* 1.4 [Indentation](https://github.com/forio/front-end-code-standards#14-indentation)

### 2.0 [Javascript](https://github.com/forio/front-end-code-standards#20-javascript)
* 2.1 [Strings](https://github.com/forio/front-end-code-standards#21-strings)
* 2.2.0 [Names](https://github.com/forio/front-end-code-standards#220-names)
    * 2.2.1 [Constants](https://github.com/forio/front-end-code-standards#221-constants)
    * 2.2.2 [Private variables](https://github.com/forio/front-end-code-standards#222-private-variables)
    * 2.2.3 [Constructors](https://github.com/forio/front-end-code-standards#223-constructors)
    * 2.2.4 [Namespaces](https://github.com/forio/front-end-code-standards#224-namespaces)
    * 2.2.5 [jQuery Elements](https://github.com/forio/front-end-code-standards#225-jquery-elements)
* 2.3 [Comments](https://github.com/forio/front-end-code-standards#23-comments)
* 2.4 [Variable Declarations](https://github.com/forio/front-end-code-standards#24-variable-declarations)
* 2.5 [Function Declarations](https://github.com/forio/front-end-code-standards#25-function-declarations)
* 2.6.0 [Statements](https://github.com/forio/front-end-code-standards#260-statements)
    * 2.6.1 [Simple Statements](https://github.com/forio/front-end-code-standards#261-simple-statements)
    * 2.6.2 [Compound Statements](https://github.com/forio/front-end-code-standards#262-compound-statements)
    * 2.6.3 [`return` Statement](https://github.com/forio/front-end-code-standards#263-return-statement)
    * 2.6.4 [`if` Statement](https://github.com/forio/front-end-code-standards#264-if-statement)
    * 2.6.5 [`for` Statement](https://github.com/forio/front-end-code-standards#265-for-statement)
    * 2.6.6 [`while` Statement](https://github.com/forio/front-end-code-standards#266-while-statement)
    * 2.6.7 [`do` Statement](https://github.com/forio/front-end-code-standards#267-do-statement)
    * 2.6.8 [`switch` Statement](https://github.com/forio/front-end-code-standards#268-switch-statement)
    * 2.6.9 [`try` Statement](https://github.com/forio/front-end-code-standards#269-try-statement)
    * 2.6.10 [`continue` Statement](https://github.com/forio/front-end-code-standards#2610-continue-statement)
    * 2.6.11 [`with` Statement](https://github.com/forio/front-end-code-standards#2611-with-statement)
    * 2.6.12 [Testing for Equality or Inequality](https://github.com/forio/front-end-code-standards#2612-testing-for-equality-or-inequality)
* 2.7 [Whitespace](https://github.com/forio/front-end-code-standards#27-whitespace)
* 2.8 [Do`s](https://github.com/forio/front-end-code-standards#28-dos)
* 2.9.0 [Don't`s](https://github.com/forio/front-end-code-standards#290-donts)
    * 2.9.1 [Use of CoffeeScript in Production](https://github.com/forio/front-end-code-standards#291-use-of-coffeescript-in-production)
    * 2.9.2 [Modification of Built-in Objects and Custom Libraries](https://github.com/forio/front-end-code-standards#292-modification-of-built-in-objects-and-custom-libraries)
    * 2.9.3 [Confusing Pluses and Minuses](https://github.com/forio/front-end-code-standards#293-confusing-pluses-and-minuses)
    * 2.9.4 [`eval` is Evil](https://github.com/forio/front-end-code-standards#294-eval-is-evil)
    * 2.9.5 [Internet Explorer's Conditional Comments](https://github.com/forio/front-end-code-standards#295-internet-explorers-conditional-comments)
    * 2.9.6 [Multiline String Literals](https://github.com/forio/front-end-code-standards#296-multiline-string-literals)
    
### 3.0 [HTML and CSS](https://github.com/forio/front-end-code-standards#30-html-and-css)
* 3.1 [The `<html>`, `<head>`, and `<body>` Elements](https://github.com/forio/front-end-code-standards#31-the-html-head-and-body-elements)
* 3.2 [Doctype and Encoding](https://github.com/forio/front-end-code-standards#32-doctype-and-encoding)
* 3.3.0 [Other Important `<meta>` Elements](https://github.com/forio/front-end-code-standards#330-other-important-meta-elements)
    * 3.3.1 [Use the Latest Rendering Engine](https://github.com/forio/front-end-code-standards#331-use-the-latest-rendering-engine)
    * 3.3.2 [Mobile Viewport](https://github.com/forio/front-end-code-standards#332-mobile-viewport)
* 3.4 [Optimized Google Analytics Snippet](https://github.com/forio/front-end-code-standards#34-optimized-google-analytics-snippet)
* 3.5.0 [HTML Formatting](https://github.com/forio/front-end-code-standards#350-html-formatting)
    * 3.5.1 [Quotes](https://github.com/forio/front-end-code-standards#351-quotes)
    * 3.5.2 [Capitalization](https://github.com/forio/front-end-code-standards#352-capitalization)
    * 3.5.3 [Trailing Whitespace](https://github.com/forio/front-end-code-standards#353-trailing-whitespace)
    * 3.5.4 [Entity References](https://github.com/forio/front-end-code-standards#354-entity-references)
    * 3.5.5 [Optional Elements](https://github.com/forio/front-end-code-standards#355-optional-elements)
    * 3.5.6 [Optional Attributes](https://github.com/forio/front-end-code-standards#356-optional-attributes)
* 3.6 [Semantics](https://github.com/forio/front-end-code-standards#36-semantics)
* 3.7 [Separation of Concerns](https://github.com/forio/front-end-code-standards#37-separation-of-concerns)
* 3.8.0 [ID and Class Naming](https://github.com/forio/front-end-code-standards#380-id-and-class-naming)
    * 3.8.1 [Use Meaningful or Generic ID and Class Names](https://github.com/forio/front-end-code-standards#381-use-meaningful-or-generic-id-and-class-names)
    * 3.8.2 [Use Names That are as Short as Possible but as Long as Necessary](https://github.com/forio/front-end-code-standards#382-use-names-that-are-as-short-as-possible-but-as-long-as-necessary)
* 3.9.0 [Selector Performance](https://github.com/forio/front-end-code-standards#390-selector-performance)
    * 3.9.1 [Avoid a Universal Key Selector](https://github.com/forio/front-end-code-standards#391-avoid-a-universal-key-selector)
    * 3.9.2 [Make your Rules as Specific as Possible](https://github.com/forio/front-end-code-standards#392-make-your-rules-as-specific-as-possible)
    * 3.9.3 [Remove Redundant Qualifiers](https://github.com/forio/front-end-code-standards#393-remove-redundant-qualifiers)
* 3.10.0 [CSS Formatting](https://github.com/forio/front-end-code-standards#3100-css-formatting)
    * 3.10.1 [Shorthand Properties](https://github.com/forio/front-end-code-standards#3101-shorthand-properties)
    * 3.10.2 [0 and Units](https://github.com/forio/front-end-code-standards#3102-0-and-units)
    * 3.10.3 [Quotation Marks in URI Values](https://github.com/forio/front-end-code-standards#3103-quotation-marks-in-uri-values)
    * 3.10.4 [Hexadecimal Notation](https://github.com/forio/front-end-code-standards#3104-hexadecimal-notation)
    * 3.10.5 [Prefixes](https://github.com/forio/front-end-code-standards#3105-prefixes)
    * 3.10.6 [ID and Class Name Delimiters](https://github.com/forio/front-end-code-standards#3106-id-and-class-name-delimiters)
    * 3.10.7 [Order](https://github.com/forio/front-end-code-standards#3107-order)
    * 3.10.8 [Block Content Indentation](https://github.com/forio/front-end-code-standards#3108-block-content-indentation)
    * 3.10.9 [Semicolons](https://github.com/forio/front-end-code-standards#3109-semicolons)
    * 3.10.10 [Property Name Stops](https://github.com/forio/front-end-code-standards#31010-property-name-stops)
    * 3.10.11 [Selector and Declaration Separation](https://github.com/forio/front-end-code-standards#31011-selector-and-declaration-separation)
    * 3.10.12 [Rule Separation](https://github.com/forio/front-end-code-standards#31012-rule-separation)
* 3.11 [Conditional Stylesheets/CSS Hacks](https://github.com/forio/front-end-code-standards#311-conditional-stylesheetscss-hacks)



# 1.0 General

**BE CONSISTENT**

If you're editing code, take a few minutes to look at the code around you and determine its style. If they use spaces around all their arithmetic operators, you should too. If their comments have little boxes of hash marks around them, make your comments have little boxes of hash marks around them too.

The point of having style guidelines is to have a common vocabulary of coding so people can concentrate on what you're saying rather than on how you're saying it. We present global style rules here so people know the vocabulary, but local style is also important. If code you add to a file looks drastically different from the existing code around it, it throws readers out of their rhythm when they go to read it. Avoid this.

## 1.1 Helpful Resources

 * [HTML5 Boilerplate](http://html5boilerplate.com/)
 * [Twitter Bootstrap](http://twitter.github.com/bootstrap/)
 * [Underscore.js](http://underscorejs.org/)

## 1.2 Filenames

Filenames should be all lowercase in order to avoid confusion on case-sensitive platforms. Filenames should contain no punctuation except for - or _ (prefer - to _).

Modifications made to 3rd party libraries should be indicated in the filename. For example: highcharts.v2.1.custom.js.

## 1.3 Project Structure
```
├── index.html
├── public
│   ├── js
│   │   ├── vendor
│   │   │   ├── jquery
│   │   │   │   ├── jquery.min.js
│   │   │   │   └── jquery.js
│   │   │   ├── backbone
│   │   │   │   ├── backbone.min.js
│   │   │   │   └── backbone.js
│   │   │   └── underscore
│   │   │   │   ├── underscore.min.js
│   │   │   │   └── underscore.js
│   │   │   └── forio
│   │   │   │   ├── api.min.js
│   │   │   │   └── api.js
│   │   └── compiled.js
│   ├── img
│   │   └── ...
│   ├── css
│   │   └── style.css
├── src
│   ├── less
│   │   ├── bootstrap
│   │   │   ├── variables.less
│   │   │   ├── ...
│   │   │   └── bootstrap.less
│   │   ├── app
│   │   │   ├── header.less
│   │   │   ├── ...
│   │   │   └── footer.less
│   │   └── style.less
│   ├── templates
│   │   └── ...
│   ├── js
│   │   ├── models
│   │   │   ├── user.js
│   │   │   └── run.js
│   │   ├── collections
│   │   │   ├── users.js
│   │   │   └── runs.js
│   │   └── views
│   ├── router.js
│   ├── app.js 
│   └── style.css
```

## 1.4 Indentation
The unit of indentation is four spaces. Use of tabs should be avoided because (as of this writing in the 21st Century) there still is not a standard for the placement of tabstops. The use of spaces can produce a larger filesize, but the size is not significant over local networks, and the difference is eliminated by minification.



# 2.0 Javascript

## 2.1 Strings

Prefer `'` over `"`
For consistency  `'` (single-quotes) are preferred to `"` (double-quotes). This is helpful when creating strings that include HTML:

```javascript
var msg = '<p class="message">This is some HTML<p>';
```

## 2.2.0 Names
In general use:
 * functionNamesLikeThis
 * variableNamesLikeThis
 * methodNamesLikeThis
 * ConstructorNamesLikeThis
 * SYMBOLIC_CONSTANTS_LIKE_THIS

### 2.2.1 Constants
Use NAMES_LIKE_THIS for constants; never use the `const` keyword.

```javascript
var ONE_SECOND = 1000,
    ONE_MINUTE = ONE_SECOND * 60;
```

### 2.2.2 Private Variables
Do not use _ (underbar) as the first character of a name. It is sometimes used to indicate privacy, but it does not actually provide privacy. If privacy is important, use the forms that provide private members. Avoid conventions that demonstrate a lack of competence.


### 2.2.3 Constructors
Constructor functions which must be used with the new prefix should start with a capital letter. JavaScript issues neither a compile-time warning nor a run-time warning if a required new is omitted. Bad things can happen if new is not used, so the capitalization convention is the only defense we have.

### 2.2.4 Namespaces
JavaScript has no inherent packaging or namespacing support.

Global name conflicts are difficult to debug, and can cause intractable problems when two projects try to integrate. In order to make it possible to share common JavaScript code, we've adopted conventions to prevent collisions.

Global variables (generally only 1 per project) should be all lowercase if a word or all caps if an acronym.

Use different namespaces for external code and internal code

"External code" is code that comes from outside your codebase, and is compiled independently. Internal and external names should be kept strictly separate. If you're using an external library that makes things available in `foo.hats.*`, your internal code should not define all its symbols in `foo.hats.*`, because it will break if the other team member defines new symbols.

```javascript
window['forio'] = window['forio'] || {};
forio.utils = {};
```

```javascript
window['MLB'] = window['MLB'] || {};
```
 
### 2.2.5 jQuery Elements
Prefix jQuery elements with $ for clarity

```javascript
var $el = $(this);
```

## 2.3 Comments

Be generous with comments. It is useful to leave information that will be read at a later time by people (possibly yourself) who will need to understand what you have done. The comments should be well-written and clear, just like the code they are annotating. An occasional nugget of humor might be appreciated. Frustrations and resentments will not.

It is important that comments be kept up-to-date. Erroneous comments can make programs even harder to read and understand.

Make comments meaningful. Focus on what is not immediately visible. Don't waste the reader's time with stuff like

```javascript
i = 0; // Set i to zero.
```

Generally use line comments. Save block comments for formal documentation and for commenting out.

Use [JSDoc](http://code.google.com/p/jsdoc-toolkit/) for formal documentation.

## 2.4 Variable Declarations

All variables should be declared before used. JavaScript does not require this, but doing so makes the program easier to read and makes it easier to detect undeclared variables that may become implied globals. Implied global variables should never be used.

The `var` statements should be the first statements in the function body.

It is preferred that each variable be given its own line and comment. They should be listed in alphabetical order.

```javascript
var currentEntry, // currently selected table entry
    level,        // indentation level
    size;         // size of table
```
JavaScript does not have block scope, so defining variables in blocks can confuse programmers who are experienced with other C family languages. Define all variables at the top of the function.  The assignment of nullable parameters may proceed variable definitions.

```javascript
var doStuff = function (options) {
    options || (options = {});
    
    var a,
        b;
};
```

Use of global variables should be minimized. **Implied global variables should never be used**.

## 2.5 Function Declarations

All functions should be declared before they are used. Inner functions should follow the var statement. This helps make it clear what variables are included in its scope.

There should be no space between the name of a function and the `(` (left parenthesis) of its parameter list. There should be one space between the `)` (right parenthesis) and the `{` (left curly brace) that begins the statement body. The body itself is indented four spaces. The `}` (right curly brace) is aligned with the line containing the beginning of the declaration of the function.

```javascript
function outer(c, d) {
    var e = c * d;

    function inner(a, b) {
        return (e * a) + b;
    }

    return inner(0, 1);
}
```

This convention works well with JavaScript because in JavaScript, functions and object literals can be placed anywhere that an expression is allowed. It provides the best readability with inline functions and complex structures.

```javascript
function getElementsByClassName(className) {
    var results = [];
    walkTheDOM(document.body, function (node) {
        var a,                  // array of class names
            c = node.className, // the node's classname
            i;                  // loop counter

        // If the node has a class name, then split it into a list of simple names.
        // If any of them match the requested name, then append the node to the set of results.

        if (c) {
            a = c.split(' ');
            for (i = 0; i < a.length; i += 1) {
                if (a[i] === className) {
                    results.push(node);
                    break;
                }
            }
        }
    });
    return results;
}
```

If a function literal is anonymous, there should be one space between the word function and the `(` (left parenthesis). If the space is omitted, then it can appear that the function's name is function, which is an incorrect reading.

```javascript
div.onclick = function (e) {
    return false;
};

that = {
    method: function () {
        return this.datum;
    },
    datum: 0
};
```

Use of global functions should be minimized.

When a function is to be invoked immediately, the entire invocation expression should be wrapped in parens so that it is clear that the value being produced is the result of the function and not the function itself.

```javascript
var collection = (function () {
    var keys = [], values = [];

    return {
        get: function (key) {
            var at = keys.indexOf(key);
            if (at >= 0) {
                return values[at];
            }
        },
        set: function (key, value) {
            var at = keys.indexOf(key);
            if (at < 0) {
                at = keys.length;
            }
            keys[at] = key;
            values[at] = value;
        },
        remove: function (key) {
            var at = keys.indexOf(key);
            if (at >= 0) {
                keys.splice(at, 1);
                values.splice(at, 1);
            }
        }
    };
}());
```

## 2.6.0 Statements

### 2.6.1 Simple Statements

Each line should contain at most one statement. Put a `;` (semicolon) at the end of every simple statement. Note that an assignment statement which is assigning a function literal or object literal is still an assignment statement and must end with a semicolon.

JavaScript allows any expression to be used as a statement. This can mask some errors, particularly in the presence of semicolon insertion. The only expressions that should be used as statements are assignments and invocations.

### 2.6.2 Compound Statements

Compound statements are statements that contain lists of statements enclosed in { } (curly braces).

 * The enclosed statements should be indented four more spaces.
 * The `{` (left curly brace) should be at the end of the line that begins the compound statement.
 * The `}` (right curly brace) should begin a line and be indented to align with the beginning of the line containing the matching `{` (left curly brace).
 * Braces should be used around all statements, even single statements, when they are part of a control structure, such as an if or for statement. This makes it easier to add statements without accidentally introducing bugs.
 
### 2.6.3 `return` Statement

A return statement with a value should not use `( )` (parentheses) around the value. The return value expression must start on the same line as the return keyword in order to avoid semicolon insertion.

### 2.6.4 `if` Statement

The if class of statements should have the following form:

```javascript
if (condition) {
    statements
}

if (condition) {
    statements
} else {
    statements
}

if (condition) {
    statements
} else if (condition) {
    statements
} else {
    statements
}
```

### 2.6.5 `for` Statement

A for class of statements should have the following form:

```javascript
for (initialization; condition; update) {
    statements
}

for (variable in object) {
    if (object.hasOwnProperty(variable)) {
        statements
    } 
}
```

The first form should be used with arrays and with loops of a predeterminable number of iterations.

The second form should be used with objects. Be aware that members that are added to the prototype of the object will be included in the enumeration. It is wise to program defensively by using the hasOwnProperty method to distinguish the true members of the object:

```javascript
for (variable in object) {
    if (object.hasOwnProperty(variable)) {
        statements
    } 
}
```

### 2.6.6 `while` Statement

A while statement should have the following form:

```javascript
while (condition) {
    statements
}
```

### 2.6.7 `do` Statement

A do statement should have the following form:

```javascript
do {
    statements
} while (condition);
```

Unlike the other compound statements, the do statement always ends with a `;` (semicolon).

### 2.6.8 `switch` Statement

A switch statement should have the following form:

```javascript
switch (expression) {
case expression:
    statements
default:
    statements
}
```

Each case is aligned with the switch. This avoids over-indentation.

Each group of statements (except the default) should end with `break`, `return`, or `throw`. Do not fall through.

### 2.6.9 `try` Statement

The try class of statements should have the following form:

```javascript
try {
    statements
} catch (variable) {
    statements
}

try {
    statements
} catch (variable) {
    statements
} finally {
    statements
}
```

### 2.6.10 `continue` Statement

Avoid use of the `continue` statement. It tends to obscure the control flow of the function.

### 2.6.11 `with` Statement

The `with` statement [should not be used](http://yuiblog.com/blog/2006/04/11/with-statement-considered-harmful/).

### 2.6.12 Testing for Equality or Inequality

JavaScript has two sets of equality operators: `===` and `!==`, and their evil twins `==` and `!=`. The good ones work the way you would expect. If the two operands are of the same type and have the same value, then === produces true and !== produces false. The evil twins do the right thing when the operands are of the same type, but if they are of different types, they attempt to coerce the values. the rules by which they do that are complicated and unmemorable. These are some of the interesting cases:

```javascript
'' == '0'           // false
0 == ''             // true
0 == '0'            // true

false == 'false'    // false
false == '0'        // true

false == undefined  // false
false == null       // false
null == undefined   // true

' \t\r\n ' == 0     // true
```

The lack of transitivity is alarming. My advice is to never use the evil twins. 

**Instead, always use `=== and !==`.**

All of the comparisons just shown produce false with the `===` operator.

## 2.7 Whitespace

Blank lines improve readability by setting off sections of code that are logically related.

Blank spaces should be used in the following circumstances:

 * A keyword followed by ( (left parenthesis) should be separated by a space.
    ```javascript
    while (true) {
    ```
 * A blank space should not be used between a function value and its `(` (left parenthesis). This helps to distinguish between keywords and function invocations.
 * All binary operators except `.` (period) and `(` (left parenthesis) and `[` (left bracket) should be separated from their operands by a space.
 * No space should separate a unary operator and its operand except when the operator is a word such as typeof.
 * Each `;` (semicolon) in the control part of a for statement should be followed with a space.
 * Whitespace should follow every `,` (comma).

## 2.8 Do`s
 * Parentheses - Only where required.
 * Use of JS compilers such as the [Closure Compiler](http://code.google.com/closure/compiler/) or [YUI Compressor](http://developer.yahoo.com/yui/compressor/) is encouraged.
 * Use ternary expressions in `return` statements.
    ```javascript
    return val ? foo() : bar();
    ```
 * Use array and object literals
 * Commit often
 * Use JSHint in your editor. [TextMate Bundle](http://fgnass.posterous.com/jslint-in-textmate)

## 2.9.0 Don't`s
 
### 2.9.1 Use of CoffeeScript in Production

> "I love CoffeeScript, I think CoffeeScript is a brilliant experiment.  It shows that if you take just the good parts of javascript and put a much better syntax on it, it's a really lovely programming language. I wish javascript looked a lot more like CoffeeScript.  That said, I would be careful where you use CoffeeScript.  I think it makes a lot of sense for experimentation, for prototypes, for one-offs, for hobbies...  I would not use it in production.  It's not a fully baked language, it's not a standard language, it's not fair to require anyone who might come after you..." - Douglas Crockford

> "I don't always use CoffeeScript, but when I do, I stay the hell AWAY from production." - The Most Interesting Man in the World

### 2.9.2 Modification of Built-in Objects and Custom Libraries
```javascript
String.prototype.toTitleCase = function () {
    // ...
};
```

Modifying 3rd party libraries should be a last resort and proper documentation should be made if done.

 * Rename the file to make it clear: highcharts.v2.1.custom.js
 * Insert comments on change lines.
 * Make separate commits for each change.

### 2.9.3 Confusing Pluses and Minuses

Be careful to not follow a `+` with `+` or `++`. This pattern can be confusing. Insert parens between them to make your intention clear.
```javascript
total = subtotal + +myInput.value;
```
is better written as
```javascript
total = subtotal + (+myInput.value);
```
so that the `+ +` is not misread as `++`.

### 2.9.4 `eval` is Evil

The `eval` function is the most misused feature of JavaScript. Avoid it.

`eval` has aliases. Do not use the `Function` constructor. Do not pass strings to `setTimeout` or `setInterval`.

### 2.9.5 Internet Explorer's Conditional Comments

![Admiral Ackbar does not use IE conditional comments](http://i.imgur.com/CGNQq.jpg)

> ### It's a TRAP!

### 2.9.6 Multiline String Literals
Do not do this:

```javascript
var myString = 'A rather long string of English text, an error message \
                actually that just keeps going and going -- an error \
                message to make the Energizer bunny blush (right through \
                those Schwarzenegger shades)! Where was I? Oh yes, \
                you\'ve got an error and all the extraneous whitespace is \
                just gravy.  Have a nice day.';
```

Concatenate instead:
```javascript
var myString = 'A rather long string of English text, an error message ' +
    'actually that just keeps going and going -- an error ' +
    'message to make the Energizer bunny blush (right through ' +
    'those Schwarzenegger shades)! Where was I? Oh yes, ' +
    'you\'ve got an error and all the extraneous whitespace is ' +
    'just gravy.  Have a nice day.';
```

# 3.0 HTML and CSS

## 3.1 The `<html>`, `<head>`, and `<body>` Elements

HTML5 doesn’t require the `<html>`, `<head>` and `<body>` elements (browsers add them if missing), but you should always use them!

If, for example, you omit the `<body>` element in IE, use the html5shiv and don't have any visible content (like text, images, etc.) in front of a new HTML5 element, that element with all the content from inside it will be included by IE in the `<head>` element.

## 3.2 Doctype and Encoding

Always use the HTML5 doctype `<!doctype html>` and utf-8 encoding `<meta charset="utf-8">`.

The encoding should come in the first [1024 Bytes](http://www.whatwg.org/specs/web-apps/current-work/multipage/semantics.html#charset)

## 3.3.0 Other Important `<meta>` Elements

### 3.3.1 Use the Latest Rendering Engine

Versions 8 and 9 of Internet Explorer contain multiple rendering engines. So even if a site visitor is using IE8 or IE9, it’s possible that they're not using the latest rendering engine their browser contains. To fix this, use:

```html
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
```
The meta element tells the IE rendering engine two things:

1. It should use the latest, or edge, version of the IE rendering environment
2. If already installed, it should use the Google Chrome Frame rendering engine.

This meta element ensures that anyone browsing your site in IE is treated to the best possible user experience that their browser can offer.

### 3.3.2 Mobile Viewport

```html
<meta name="viewport" content="width=device-width">
```

There are a few different options that you can use with this meta element. You can find out more in the [Apple developer docs](http://j.mp/mobileviewport).

## 3.4 Optimized Google Analytics Snippet

```html
<!-- Asynchronous Google Analytics snippet. Change UA-XXXXX-X to be your site's ID. -->
<script>
    var _gaq=[['_setAccount','UA-XXXXX-X'],['_trackPageview']];
    (function(d,t){var g=d.createElement(t),s=d.getElementsByTagName(t)[0];
    g.src=('https:'==location.protocol?'//ssl':'//www')+'.google-analytics.com/ga.js';
    s.parentNode.insertBefore(g,s)}(document,'script'));
</script>
```

[How it works](http://mathiasbynens.be/notes/async-analytics-snippet)

## 3.5.0 HTML Formatting

Use a new line for every block, list, or table element, and indent every such child element.
Independent of the styling of an element (as CSS allows elements to assume a different role per display property), put every block, list, or table element on a new line.

Also, indent them if they are child elements of a block, list, or table element.

(If you run into issues around whitespace between list items it is acceptable to put all li elements in one line. A linter is encouraged to throw a warning instead of an error.)

```html
<blockquote>
    <p><em>Space</em>, the final frontier.</p>
</blockquote>
```

```html
<ul>
    <li>Moe</li>
    <li>Larry</li>
    <li>Curly</li>
</ul>
<table>
    <thead>
        <tr>
            <th scope="col">Income</th>
            <th scope="col">Taxes</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>$ 5.00</td>
            <td>$ 4.50</td>
        </tr>
    </tbody>
</table>
```

Do not leave off optional closing tags as it's easy to get confused and leave of required closing tags and confuse readers who don't know what is optional.

If you're concerned about saving file size, use an html compiler.

```html
<!-- Not recommended -->
<ul>
    <li>This
    <li>Is
    <li>Wrong
</ul>
<!-- Recommended -->
<ul>
    <li>This</li>
    <li>Is</li>
    <li>Wrong</li>
</ul>
```

### 3.5.1 Quotes

In HTML, we use `"` (double quotes) around attribute values, like this:

```html
<a href="foo">bar</a>
```

This way, we can use consistent quotes when writing HTML inside of JS:

```javascript
alert('<a href="foo">bar</a>');
```

### 3.5.2 Capitalization

Use lowercase only.

All code has to be lowercase: this applies to element names, attributes, attribute values (unless text/CDATA), selectors, properties, and property values (with the exception of strings).

### 3.5.3 Trailing Whitespace

Remove trailing white spaces.
Trailing white spaces are unnecessary and can complicate diffs.

### 3.5.4 Entity References

Use entity references only where required `<`, `>`, and `&`  as well as control or "invisible" characters (like no-break spaces).

There is no need to use entity references like &mdash;, &rdquo;, or &#x263a;, assuming the same encoding (UTF-8) is used for files and editors as well as among teams.

```html
<!-- Not recommended -->
The currency symbol for the Euro is &ldquo;&eur;&rdquo;.
<!-- Recommended -->
The currency symbol for the Euro is “€”.
```

### 3.5.5 Optional Elements

Omitting [optional elements](http://www.whatwg.org/specs/web-apps/current-work/multipage/syntax.html#syntax-tag-omission) can be useful for file size optimization, but be clear and consistent.

### 3.5.6 Optional Attributes

Omit optional attributes on script and stylesheets.

## 3.6 Semantics

Use HTML according to its purpose.
Use elements for what they have been created for. For example, use `<header>` elements for headings, `<p>` elements for paragraphs, `<a>` elements for anchors, etc.

Using HTML according to its purpose is important for accessibility, reuse, and code efficiency reasons.

```html
<!-- Not recommended -->
<div onclick="goToRecommendations();">All recommendations</div>
<!-- Recommended -->
<a href="recommendations/">All recommendations</a>
```

## 3.7 Separation of Concerns

Avoid inline javascript/CSS in markup.

```html
<!-- Not recommended -->
<!DOCTYPE html>
<title>HTML sucks</title>
<link rel="stylesheet" href="base.css" media="screen">
<link rel="stylesheet" href="grid.css" media="screen">
<link rel="stylesheet" href="print.css" media="print">
<h1 style="font-size: 1em;">HTML sucks</h1>
<p>I’ve read about this on a few sites but now I’m sure:
  <u>HTML is stupid!!1</u>
<center>I can’t believe there’s no way to control the styling of
  my website without doing everything all over again!</center>
```

## 3.8.0 ID and Class Naming

### 3.8.1 Use Meaningful or Generic ID and Class Names.
Instead of presentational or cryptic names, always use ID and class names that reflect the purpose of the element in question, or that are otherwise generic.

Names that are specific and reflect the purpose of the element should be preferred as these are most understandable and the least likely to change.

Generic names are simply a fallback for elements that have no particular or no meaning different from their siblings. They are typically needed as "helpers."

Using functional or generic names reduces the probability of unnecessary document or template changes.

```css
/* Not recommended: meaningless */
#yee-1901 {}

/* Not recommended: presentational */
.button-green {}
.clear {}

/* Recommended: specific */
#gallery {}
#login {}
.video {}

/* Recommended: generic */
.aux {}
.alt {}
```

### 3.8.2 Use Names That Are as Short as Possible but as Long as Necessary

Try to convey what an ID or class is about while being as brief as possible.

Using ID and class names this way contributes to acceptable levels of understandability and code efficiency.

```css
/* Not recommended */
#navigation {}
.atr {}
/* Recommended */
#nav {}
.author {}
```

## 3.9.0 Selector Performance

Selectors are matched right to left.  The right most being the key selector.

Avoiding inefficient key selectors that match large numbers of elements can [speed up page rendering](https://developers.google.com/speed/docs/best-practices/rendering).

### 3.9.1 Avoid a Universal Key Selector
```css
body * {...}
.hide-scrollbars * {...}
```
Allow elements to inherit from ancestors, or use a class to apply a style to multiple elements.

### 3.9.2 Make Your Rules as Specific as Possible
Prefer class and ID selectors over element selectors.

### 3.9.3 Remove Redundant Qualifiers.
These qualifiers are redundant:
 * ID selectors qualified by class and/or element selectors
 * Class selectors qualified by element selectors (when a class is only used for one tag, which is a good design practice anyway).

```css
/* Not recommended */
ul#example {}
div.error {}

/* Recommended */
#example {}
.error {}
```

## 3.10.0 CSS Formatting

### 3.10.1 Shorthand Properties
Use shorthand properties where possible.
CSS offers a variety of shorthand properties (like font) that should be used whenever possible, even in cases where only one value is explicitly set.

Using shorthand properties is useful for code efficiency and understandability.

```css
/* Not recommended */
border-top-style: none;
font-family: palatino, georgia, serif;
font-size: 100%;
line-height: 1.6;
padding-bottom: 2em;
padding-left: 1em;
padding-right: 1em;
padding-top: 0;

/* Recommended */
border-top: 0;
font: 100%/1.6 palatino, georgia, serif;
padding: 0 1em 2em;
```

### 3.10.2 0 and Units
Do not use units after 0 values unless they are required.

```css
margin: 0;
padding: 0;
```

### 3.10.3 Quotation Marks in URI Values

Omit quotation marks in URI values.
Do not use `""`, `'` (quotation marks) with `url()`.

```css
@import url(//www.google.com/css/go.css);
```

### 3.10.4 Hexadecimal Notation
Use 3 character hexadecimal notation where possible.
For color values that permit it, 3 character hexadecimal notation is shorter and more succinct.

```css
/* Not recommended */
color: #eebbcc;

/* Recommended */
color: #ebc;
````

### 3.10.5 Prefixes

Prefix selectors with an application-specific prefix (optional).
In large projects as well as for code that gets embedded in other projects or on external sites use prefixes (as namespaces) for ID and class names. Use short, unique identifiers followed by a dash.

Using namespaces helps preventing naming conflicts and can make maintenance easier, for example in search and replace operations.

```css
.adw-help {} /* AdWords */
#maia-note {} /* Maia */
```

### 3.10.6 ID and Class Name Delimiters
Separate words in ID and class names by a hyphen.
Do not concatenate words and abbreviations in selectors by any characters (including none at all) other than hyphens, in order to improve understanding and scannability.

```css
/* Not recommended: does not separate the words “demo” and “image” */
.demoimage {}

/* Not recommended: uses underscore instead of hyphen */
.error_status {}

/* Recommended */
#video-id {}
.ads-sample {}
```

### 3.10.7 Order

Alphabetize declarations.
Put declarations in alphabetical order in order to achieve consistent code in a way that is easy to remember and maintain.

Ignore vendor-specific prefixes for sorting purposes. However, multiple vendor-specific prefixes for a certain CSS property should be kept sorted (e.g. `-moz` prefix comes before `-webkit`).

```css
background: fuchsia;
border: 1px solid;
-moz-border-radius: 4px;
-webkit-border-radius: 4px;
border-radius: 4px;
color: black;
text-align: center;
text-indent: 2em;
```

### 3.10.8 Block Content Indentation
Indent all block content.
Indent all block content, that is rules within rules as well as declarations, so to reflect hierarchy and improve understanding.

```css
@media screen, projection {
    html {
        background: #fff;
        color: #444;
    }
}
```

### 3.10.9 Semicolons

Use them.

### 3.10.10 Property Name Stops

Use a space after a property name’s colon.
Always use a single space between property and value (but no space between property and colon) for consistency reasons.

```css
/* Not recommended */
h3 {
    font-weight:bold;
}

/* Recommended */
h3 {
    font-weight: bold;
}
```

### 3.10.11 Selector and Declaration Separation

Separate selectors and declarations by new lines.
Always start a new line for each selector and declaration.

```css
/* Not recommended */
a:focus, a:active {
    position: relative; top: 1px;
}

/* Recommended */
h1,
h2,
h3 {
    font-weight: normal;
    line-height: 1.2;
}
```

### 3.10.12 Rule Separation

Separate rules by new lines.
Always put a line between rules.

```css
html {
    background: #fff;
}

body {
    margin: auto;
    width: 50%;
}
```

## 3.11 Conditional Stylesheets/CSS Hacks

[Neither](http://aulirish.com/2008/conditional-stylesheets-vs-css-hacks-answer-neither/)

```html
<!--[if lt IE 7]> <html class="no-js lt-ie9 lt-ie8 lt-ie7"> <![endif]-->
<!--[if IE 7]>    <html class="no-js lt-ie9 lt-ie8"> <![endif]-->
<!--[if IE 8]>    <html class="no-js lt-ie9"> <![endif]-->
<!--[if gt IE 8]><!--> <html class="no-js"> <!--<![endif]-->
```

```css
.ie8 legend {
    margin-left: 20px;
}
```
