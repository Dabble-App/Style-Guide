# General Style Guidelines

Detailed below are default style guidelines to be adhered to in all code, unless otherwise specified or in extenuating circumstances:

* "Otherwise specified": A language-specified style guide overrides the default specified here.
* "Extenuating circumstances": Following the guide severely impacts code readability and/or extensibility, or simply causes the code to not work as intended.

## Formatting

**Line Character Limit**

Every line should have a maximum of 100 characters.

**Expressions**

Whitespace should be used appropriately and consistently to make expressions more readable. There are no strict guidelines and good style is language-dependent, but here are general rules:

* Be consistent with spacing around operators; if you put a space before, put a space after too.
* Put spaces around operators when using non-arithmetic operators.
* Use spaces to split up complex expressions in logically equivalent subparts.

Good examples:
* `Math.pow(2, a - b)`
* `(x+y == 91) ? Math.min(13, y) : (2*x + 34*y)`

Bad examples:
* `2 + a* b`
* `(-- x+y) ^2`

**Brackets and Parenthesis**

If permitted by the language, adding parenthesis and brackets for clarity are preferred.

Closing brackets should always be on the same level as opening brackets.

Good example:
```js
let arr = [
    {
        name: 'Pie',
        isCake: true
    },
    {
        name: 'Cookie',
        isCake: false,
        recipe: (
            longVariableName1, longVariableName2, longVariableName3
        ) => 'Sorry there is no recipe for now'
    }
];
```

Bad example:
```js
let arr = [
    {
        name: 'Pie',
        isCake: true
    }];
```

**Method Chaining**

When multiple method calls are chained in a long line, all calls except the first should be placed on a separate line with one further level of identation than the line with the initial call.

Good example:
```java
Random r = new Random();
double a = Stream.generate(r::nextDouble)
    .skip(3)
    .limit(5)
    .sorted()
    .peek(System.out::println)
    .reduce(0.0, (a,b) -> a+b);
```

Bad example:
```java
Random r = new Random();
double a = Stream.generate(r::nextDouble)
    .skip(3).limit(5)
    .sorted()
    .peek(System.out::println)
        .reduce(0.0, (a,b) -> a+b);
```

**Line Breaks**

Long lines should be broken up in a way that makes sense. It is preferable to break a line at a higher organizational level as opposed to breaking it right before hitting the line character limit.

Good examples:
```js
let a = (1+2+3+4+5) *
    ((6+7+8+9+10) / ((11+12+13+14+15) * (16+17+18+19+20)));
```
```js
return res.status(405)
    .json({ errors: [{ msg: 'User has already been invited or has already requested to join' }] });
```

Bad examples:
```js
let a = (1+2+3+4+5) * ((6+7+8+9+10) /
    ((11+12+13+14+15) * (16+17+18+19+20))
);
```
```js
return res.status(405).json({errors: [{ msg:
    'User has already been invited or has already requested to join'
}] });
```

## Naming

**General**

Naming for everything (folders, files, modules, variables, you name it-) should only contain ASCII letters and digits, and underscores (`_`) and dashes (`-`) in a small number of cases.

Note that if there is a language-specific or framework-specific syntactical reason otherwise, unconventional naming is permitted.

Good examples:
* `myCutePythonVar`
* `html-identifier`
* `JavaClass101`
* `I_AM_A_CONSTANT`

## Functions

**Parameters**

Only include parameters that are used in the function. Do not take unnecessary parameters as that obfuscates the code.

Unless absolutely necessary, functions should not take more than 10 parameters. As the saying goes, "if you have to include more than 10 parameters, you probably forgetting some more".

## Comments

**Doc Comments**

If the language has support for special documentation comments (ex. Javadoc for Java), follow those conventions whenever writing any code that is exported or otherwise exposed.

**Inline Comments**

Add inline comments as appropriate to describe complicated chunks of code, so that it is easier for reviewers and future readers to follow along.