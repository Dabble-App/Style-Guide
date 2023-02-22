# TypeScript Code Guidelines

Detailed below are style guidelines to be followed in TypeScript and TSX code, in addition to the [General](general.md) style guidelines.

## Formatting

**Line Character Limit**

TS code is expected to adhere to the general line character limit, but TSX can be up to 150 characters if necessary.

**Long TSX**

If TSX lines are long, consider breaking them down via attribute.

Good example:
```tsx
return (
  <Chip
    onClick={()=>{router.push('/project/[projectId]')}}
    label={<Typography marginLeft="10px">{props.name}</Typography>}
    sx={{
      height: "50px",
      paddingLeft: "10px",
      justifyContent: "flex-start"
    }}
  />
);
```

**Identation**

TypeScript code should be idented block-style by 2 spaces.

## TypeScript Syntax

**Semicolons**

End all code lines with a semicolon. The only reason to do otherwise is in a 1-line arrow function expression.

Note that non-code lines (ex. ending braces of an if statement) do not need semicolons.

Good examples:
```tsx
if(x+y === 3) {
  x++;
  y--;
  return x-y;
}
```
```tsx
() => {console.log('hi')}
```

Bad example:
```tsx
let arr = [1, 2, 3]
```

**Quotes**

Prefer single quotes (`'`) over double quotes (`"`) for strings where possible.

Good example:
* `let str: string = 'I ate an apple';`

**Equality Operator**

Prefer `===` and `!==` over `==` and `!=` where possible.

Good examples:
* `str === 'abc'`
* `x+1 !== 3`

Bad examples:
* `x == y ? 1 : 2`
* `str != '123'`

**Trailing Commas**

There should not be trailing commas in arrays and objects.

Good example:
```tsx
{
  candies: [1, 2, 3],
  cookies: true
}
```

Bad example:
```tsx
{
  candies: [1, 2, 3,],
  cookies: true,
}
```

## Imports

**Deconstruction**

Deconstruct imports where possible.

Good example:
```tsx
import { Fragment } from 'react';
...
<Fragment>
  ...
</Fragment>
```

Bad example:
```tsx
import React from 'react';
...
<React.Fragment>
  ...
</React.Fragment>
```

**Repeat Modules**

If you have to import multiple things from one module, combine the various imports into one import statement.

Good example:
```tsx
import { x, y, z } from 'my-module';
```

Bad example:
```tsx
import { x } from 'my-module';
import { y } from 'my-module';
import { z } from 'my-module';
```

**Bulk Imports**

If you are importing a lot from a module and the line is getting long, split up the import into multiple lines where one import takes one line.

Good example:
```tsx
import {
  CheckOutlined,
  CloseOutlined,
  MailOutline,
} from "@mui/icons-material";
```

## Variables

**Primitive Types**

Variables should never be instantiated as wrapper types. Wrapper types have funny behavior, such as `new Boolean(false)` evaluating to `true`.

Primitive types should always be typed as primitive types and not wrapper types.

Good examples:
* `const x: number = 10;`
* `let str: string = 'I love computers';`

Bad examples:
* `let oopsies = new String('abcdef');`
* `const y: Number = 10;`

**Variable Declarations**

Declare variables with `const` if possible. If the variable will be reassigned, use `let`. Never use `var` as it can result in funny behavior.

Types do not need to be declared for variables. However, if the type is unique and declaring the type enhances code clarity, please add a type.

If the type can be trivially inferred (ex. assigned to a literal upon declaration), do not declare the type.

Good examples:
* `const myvar: Transport = createTransport();`
* `let abc = 20;`

Bad examples:
* `const i: number = 10;`
* `let s: string = 'I declare code';`
* `var x = 15;`

**Forbidden Types**

The following types should never be used:
* `null`
* `undefined`
* `Number`
* `String`
* `Boolean`

## Functions

**Function Parameters**

Types should be declared for function parameters, so that callers know what to expect. Avoid using the `any` type if possible.

**Function Return Types**

Declare return types for all functions that return data, unless the return type is unknown.

**Function Declarations**

Use the `function()` declaration if a function is top-level.

Use arrow functions for all other declarations.

## Interfaces and Custom Types

[This section has not been developed]