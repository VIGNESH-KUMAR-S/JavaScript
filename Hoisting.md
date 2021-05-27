# Hoisting 
- >**Hoisting** is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution.

- Which means,
    ```js
      console.log(a);
      var a = 'Hoisting';
    ```
    the above is interpreted as this:
    ```js
      var a;
      console.log(a);
      var a = 'Hoisting';
    ```

- >Since, **Hoisting** moved only declarations not initializations.

- When JS program runs, a **`Global execution context`** created in the `call stack` area.

- Whereas, In the first phase of `Global execution context`, the **variable environment** creates memory for all variables and functions in that program.

- At the time of memory creation, variables are stored with `undefined` and functions are stored with `function body`.

- Since **code execution** started after that only, that's how the variable and functions are hoisted.

## Variable Hoisting using "var" 

  ```js
  console.log(a);   //undefined
  var a=10;   //'a' initialized with 10
  
  console.log(a);   //undefined
  var a=10;   //'a' initialized with 10
  console.log(a);   //10
  ```
## Variable Hoisting using "let" 

  ```js
  console.log(a);   //Reference error
  let a=10;   
  ```
- **let** was introduced in **`ES6`** and doesn't allow the use of undeclared variables, the interpreter explicitly spits out a Reference error.

- **> We ensure that, we use variable after declaring that.**

  ```js
  let a;
  console.log(a);   //undefined
  a=10;   //'a' initialized with 10
  console.log(a);   //10
  ```
  
## Variable Hoisting using "const" 

  ```js
  console.log(a);   //Reference error
  const a=10;
  
  const a;    //Error, const variable declared and initialized at the same time
  
  const a=10;   //'a' initialized with 10
  console.log(a);   //10

  ```

## Hoisting in Function Declaration

- If given function is a standard function declaration. Then **Hoisting** works fine.

  ```js 
  console.log(double);   //prints the body of function example()
  console.log(double(3));   //9
  double(2);
  function double(num) {
    let a = num*num;
    console.log(a); //num*num printed
    return a;
  }
  ```

## Hoisting in Function Expression and in Arrow function

- If function is an arrow function or function expression then **Hoisting** won't work.

  ```js 
  console.log(double);  //undefined
  console.log(double(3));   //Error : double is not a function
  var double = function (num) {
    let a = num*num;
    return a;
  }
  console.log(double(3));   //9
  ```
  
  ```js 
  console.log(double);  //undefined
  console.log(double(3));   //Error : double is not a function
  var double = (num) => {
    let a = num*num;
    return a;
  }
  console.log(double(3));   //9
  ```
  
- Generally, **Hoisting** is based on **Memory creation phase** or **Variable environment phase**.
  
  
  
