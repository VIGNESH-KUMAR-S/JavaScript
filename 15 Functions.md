# Functions
- Function is the heart of JavaScript.
- If the same block of code repeated , then we store that block of code in some place, whenever we want that block of code then use it by using function.

## Function declaration (or) Function statement

```js
  function x(){
     //code
     ;
     ;
  }
```
## Function expression
- Function also assigned as value.
```js
  var a = function (){
    ;
    ;
  }
  
  //or
  
  const a = function (){
    ;
    ;
  }
```

## Difference between Function declaration and expression
- The major difference is **HOISTING**.
- Function declaration only be hoisted.
- Other types are not hoisted.

## Anonymous function
- A function without name is called **Anonymous function**.
- But we can't use it in function statement.

```js
  function (){
    //code
    ;
    ;
  }
  // SYNTAX ERROR
```

- If the function are used as values, then we can use anonymous functions.

```js
  const a = function(){
    ;
  }
```

## Named Function expression

```js
  const a = function xyz(){
    console.log("Yes");
  }
  a();  //Yes
  xyz();  //Error: xyz() not defined
```
- xyz() is not available in global scope. It's in local scope.

```js
  const a = function xyz(){
    console.log("Yes");
    console.log(xyz);
  }
  a();  
```

## Parameters vs Argument

- param1, param2 are parameters. 2,4 are arguments.
```js
  function x(param1, param2){
    return (param1);
  }

  x(2,4);
```
# First Class Functions
- The ability to use function as values , arguments to another function and return values in JS called First class function.

```js
  function x(y){
    return y;
  } 
  function y(){
    console.log("Y");
  }
  x(y);
```
