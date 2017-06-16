# Javascrip Code Standards

## Table of Contents
* [Braces](#braces)
* [Class Literals](#class-literals)
* [Function Expressions](#function-expressions)
* [Switch statements](#switch-statements)
* [Statements](#statements)
* [Comments](##comments)
* [Local variable declarations](#local-variable-declarations)
* [Array Literals](#array-literals)
* [Object Literals](#object-literals)
* [Functions](##functions)
* [Naming](#naming)


## Braces
Braces are required for all control structures (i.e. `if`, `else`, `for`, `do`, `while`, as well as any others), even if the body contains only a single statement. The first statement of a non-empty block must begin on its own line.

## Class Literals
Class literals (whether declarations or expressions) are indented as blocks. Do not add semicolons after methods, or after the closing brace of a class declaration (statements—such as assignments—that contain class expressions are still terminated with a semicolon). Use the extends keyword, but not the @extends JSDoc annotation unless the class extends a templatized type

## Function Expressions
When declaring an anonymous function in the list of arguments for a function call, the body of the function is indented two spaces more than the preceding indentation depth.

## Switch Statements
As with any other block, the contents of a switch block are indented +2.

After a switch label, a newline appears, and the indentation level is increased +2, exactly as if a block were being opened. An explicit block may be used if required by lexical scoping. The following switch label returns to the previous indentation level, as if a block had been closed.

## Statements
* *One statement per line.* Each statement is followed by a line-break.
* *Semicolons required.* Every statement must be terminated with a semicolon. Relying on automatic semicolon insertion is forbidden.

## Comments
Explain code as needed, where possible.
```
  /**
   * Multiple lines of JSDoc text are written here,
   * wrapped normally.
   * @param {number} arg A number to do something to.
   */
  function doSomething(arg) { … }
```

## Local variable declarations
* *Use `const` and `let`.* Declare all local variables with either `const` or `let`. Use const by default, 
unless a variable needs to be reassigned. The var keyword must not be used.
* *One variable per declaration*. Every local variable declaration declares only one variable: declarations such as `let a = 1, b = 2;` are not used.
* *Declared when needed, initialized as soon as possible.* Local variables are not habitually declared at the start of their containing block or block-like construct. Instead, local variables are declared close to the point they are first used (within reason), to minimize their scope.


## Array literals
* *Use trailing commas.* Include a trailing comma whenever there is a line break between the final element and the closing bracket. For example

```
  const values = [
    'first value',
    'second value',
  ];
```

* *Do not use the variadic Array constructor.* The constructor is error-prone if arguments are added or removed. Use a literal instead.

```
  <!-- Not recommended -->
  const a1 = new Array(x1, x2, x3);
  const a2 = new Array(x1, x2);
  const a3 = new Array(x1);
```

This works as expected except for the third case: if x1 is a whole number then a3 is an array of size x1 where all elements are undefined. If x1 is any other number, then an exception will be thrown, and if it is anything else then it will be a single-element array.

```
  <!-- Recommended -->
  const a1 = [x1, x2, x3];
  const a2 = [x1, x2];
  const a3 = [x1];
  const a4 = [];
```

* *Non-numeric properties.* Do not define or use non-numeric properties on an array (other than length). Use a Map (or Object) instead.

* *Spread operator.* Array literals may include the spread operator (`...`) to flatten elements out of one or more other iterables. The spread operator should be used instead of more awkward constructs with `Array.prototype`. There is no space after the `....`

## Object Literals
* *Use trailing commas.* Include a trailing comma whenever there is a line break between the final property and the closing brace.

* *Do not mix quoted and unquoted keys.* Object literals may represent either structs (with unquoted keys and/or symbols) or dicts (with quoted and/or computed keys). Do not mix these key types in a single object literal. 

```
  <!-- Not Recommended -->
  {
    a: 42, // struct-style unquoted key
    'b': 43, // dict-style quoted key
  }
```

## Functions
* *Arrow functions.* Arrow functions provide a concise syntax and fix a number of difficulties with this. Prefer arrow functions over the function keyword, particularly for nested functions. Avoid writing `const self = this`

## Naming
Give as descriptive a name as possible, within reason. Do not worry about saving horizontal space as it is far more important to make your code immediately understandable by a new reader. Do not use abbreviations that are ambiguous or unfamiliar to readers outside your project, and do not abbreviate by deleting letters within a word.

```
priceCountReader      // No abbreviation.
numErrors             // "num" is a widespread convention.
numDnsConnections     // Most people know what "DNS" stands for.
```
