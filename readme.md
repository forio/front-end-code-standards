# Forio Front-End Style Guide
This document was inspired by a combination of style guides originally authored by [Douglas Crockford](http://javascript.crockford.com/code.html) and [Google](http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml).

# Javascript

## Filenames

Filenames should be all lowercase in order to avoid confusion on case-sensitive platforms. Filenames should end in .js, and should contain no punctuation except for - or _ (prefer - to _).

Modifications made to 3rd party libraries should be indicated in the filename. For example: highcharts.v2.1.custom.js.

## Indentation
The unit of indentation is four spaces. Use of tabs should be avoided because (as of this writing in the 21st Century) there still is not a standard for the placement of tabstops. The use of spaces can produce a larger filesize, but the size is not significant over local networks, and the difference is eliminated by minification.

## Names
In general use:
 * functionNamesLikeThis
 * variableNamesLikeThis
 * methodNamesLikeThis
 * ConstructorNamesLikeThis
 * SYMBOLIC_CONSTANTS_LIKE_THIS
 
## Strings

Prefer `'` over `"`
For consistency  `'` (single-quotes) are preferred to `"` (double-quotes). This is helpful when creating strings that include HTML:

```javascript
var msg = '<p class="message">This is some HTML<p>';
```

### Constants
Use NAMES_LIKE_THIS for constants; never use the `const` keyword.

```javascript
var ONE_SECOND = 1000,
    ONE_MINUTE = ONE_SECOND * 60;
```

### Private variables
Do not use _ (underbar) as the first character of a name. It is sometimes used to indicate privacy, but it does not actually provide privacy. If privacy is important, use the forms that provide private members. Avoid conventions that demonstrate a lack of competence.


### Constructors
Constructor functions which must be used with the new prefix should start with a capital letter. JavaScript issues neither a compile-time warning nor a run-time warning if a required new is omitted. Bad things can happen if new is not used, so the capitalization convention is the only defense we have.

### Namespaces
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
 
### jQuery elements
Prefix jQuery elements with $ for clarity

```javascript
var $el = $(this);
```

## Comments

Be generous with comments. It is useful to leave information that will be read at a later time by people (possibly yourself) who will need to understand what you have done. The comments should be well-written and clear, just like the code they are annotating. An occasional nugget of humor might be appreciated. Frustrations and resentments will not.

It is important that comments be kept up-to-date. Erroneous comments can make programs even harder to read and understand.

Make comments meaningful. Focus on what is not immediately visible. Don't waste the reader's time with stuff like

```javascript
i = 0; // Set i to zero.
```

Generally use line comments. Save block comments for formal documentation and for commenting out.

Use [JSDoc](http://code.google.com/p/jsdoc-toolkit/) for formal documentation.

## Variable Declarations

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

## Function Declarations

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

## Statements

###Simple Statements

Each line should contain at most one statement. Put a `;` (semicolon) at the end of every simple statement. Note that an assignment statement which is assigning a function literal or object literal is still an assignment statement and must end with a semicolon.

JavaScript allows any expression to be used as a statement. This can mask some errors, particularly in the presence of semicolon insertion. The only expressions that should be used as statements are assignments and invocations.

###Compound Statements

Compound statements are statements that contain lists of statements enclosed in { } (curly braces).

 * The enclosed statements should be indented four more spaces.
 * The `{` (left curly brace) should be at the end of the line that begins the compound statement.
 * The `}` (right curly brace) should begin a line and be indented to align with the beginning of the line containing the matching `{` (left curly brace).
 * Braces should be used around all statements, even single statements, when they are part of a control structure, such as an if or for statement. This makes it easier to add statements without accidentally introducing bugs.
 
### `return` Statement

A return statement with a value should not use `( )` (parentheses) around the value. The return value expression must start on the same line as the return keyword in order to avoid semicolon insertion.

### `if` Statement

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

### `for` Statement

A for class of statements should have the following form:

```javascript
for (initialization; condition; update) {
    statements
}

for (variable in object) {
    if (filter) {
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

### `while` Statement

A while statement should have the following form:

```javascript
while (condition) {
    statements
}
```

### `do` Statement

A do statement should have the following form:

```javascript
do {
    statements
} while (condition);
```

Unlike the other compound statements, the do statement always ends with a `;` (semicolon).

### `switch` Statement

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

### `try` Statement

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

### `continue` Statement

Avoid use of the `continue` statement. It tends to obscure the control flow of the function.

### `with` Statement

The `with` statement [should not be used](http://yuiblog.com/blog/2006/04/11/with-statement-considered-harmful/).

## Whitespace

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

## Do`s
 * Parentheses - Only where required.
 * Use of JS compilers such as the [Closure Compiler](http://code.google.com/closure/compiler/) or [YUI Compressor](http://developer.yahoo.com/yui/compressor/) is encouraged.
 * Use ternary expressions in `return` statements.
    ```javascript
    return val ? foo() : bar();
    ```
 * Use array and object literals
 * Commit often

**BE CONSISTENT**.

If you're editing code, take a few minutes to look at the code around you and determine its style. If they use spaces around all their arithmetic operators, you should too. If their comments have little boxes of hash marks around them, make your comments have little boxes of hash marks around them too.

The point of having style guidelines is to have a common vocabulary of coding so people can concentrate on what you're saying rather than on how you're saying it. We present global style rules here so people know the vocabulary, but local style is also important. If code you add to a file looks drastically different from the existing code around it, it throws readers out of their rhythm when they go to read it. Avoid this.


## Don't`s
 
### Use of CoffeeScript in production.
"I love CoffeeScript, i think CoffeeScript is a brilliant experiment.  It shows that if you take just the good parts of javascript and put a much better syntax on it, it's a really lovely programming language. I wish javascript looked a lot more like CoffeeScript.  That said, I would be careful where you use CoffeeScript.  I think it makes a lot of sense for experimentation, for prototypes, for one-offs, for hobbies...  I would not use it in production.  It's not a fully baked language, it's not a standard language, it's not fair to require anyone who might come after you..."  - Douglas Crockford

### Modify built-in objects or custom libraries.
```javascript
String.prototype.toTitleCase = function () {
    // ...
};
```

Modifying 3rd party libraries should be a last resort and proper documentation should be made if done.

 * Rename the file to make it clear: highcharts.v2.1.custom.js
 * Insert comments on change lines.
 * Make separate commits for each change.

### Confusing Pluses and Minuses

Be careful to not follow a `+` with `+` or `++`. This pattern can be confusing. Insert parens between them to make your intention clear.
```javascript
total = subtotal + +myInput.value;
```
is better written as
```javascript
total = subtotal + (+myInput.value);
```
so that the `+ +` is not misread as `++`.

### `eval` is Evil

The `eval` function is the most misused feature of JavaScript. Avoid it.

`eval` has aliases. Do not use the `Function` constructor. Do not pass strings to `setTimeout` or `setInterval`.

### Internet Explorer's Conditional Comments

It's a TRAP

### Multiline string literals
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



