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
      a = 'Hoisting';
    ```

- >Since, **Hoisting** moved only declarations not initializations.

- When JS program runs, a **`Global execution context`** created in the `call stack` area.

- Whereas, In the first phase of `Global execution context`, the **variable environment** creates memory for all variables and functions in that program.

- At the time of memory creation, all variables stored with `undefined` and functions are stored with `function body`.

- But,`var` variables only stored in **global** or **function** scope whereas, `let` and `const` stored in **script** or **block** or other scope.

- Since **code execution** started only after first phase, that's how the variable and functions are hoisted.

## Variable Hoisting using "var" 

  ```js
  console.log(a);   //undefined
  var a=10;   //'a' initialized with 10
  ----------------------------------------
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
- **let** stored in script scope, if variable or function that stored in global scope only hoisted.

- >**We ensure that, we use variable after declaring that.**

  ```js
  let a;   //here `undefined` is stored in script scope
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
  

**Examples**

1. 
    ```js
      function foo() {
          function bar() {
              console.log("hlo");
              return 3;
          }    
          return bar();
          function bar() {
              return 8;    
          }
      }
      console.log(foo());
    ```
    Above code internally reconstructed to :
    ```js
      function foo() {
          function bar() {
              return 8;    
          }
          return bar();
      }
      console.log(foo());
    ```

    - In **JavaScript** if we write same name and same or different argument with different functions, then it's **Function Overriding**.
    - Based on hoisting the two `bar()` functions will be moved to the top of their scope.
    - After that the first one will be deleted. Which means last function only presents, all other functions are deleted.



2.
    ```js
      var a = 1;
      function b() {  
          console.log(typeof a);  //function
          a = 10;
          console.log(a);  //10
          console.log(typeof a);  //number
          return;
          function a() {};
      }
      b();
      console.log(a); //1
    ```
    The above program internally reconstructed to :
  
    ```js
      var a;
      a=1;
      function b() {  
          function a();
          console.log(typeof a);  //function
          a = 10;
          console.log(a);  //10
          console.log(typeof a);  //number
          return;
          function a() {};
      }
      b();
      console.log(a); //1
    ```
    - Variable and functions with same name, so that function replaced variable.
    - Since, `'a'` in `function b()` acting as inner function. But at the time of **code execution** the `typeof` **a** changed to `number`.

3.
    ```js
        var myVar = 'foo';
        (function() {  
            console.log('Original value was: ' + myVar);
            var myVar = 'bar';  
            console.log('New value is: ' + myVar);
        })();
    ```
    Based on hoisting :
    ```js
        var myVar;
        myVar = 'foo';
        (function() {  
            var myVar;
            console.log('Original value was: ' + myVar);
            myVar = 'bar';  
            console.log('New value is: ' + myVar);
        })();
    ```
    - Here, inside the function there is **`var` myVar** variable which will be hoisted to the top of that function.
    
4.
    ```js
    console.log(typeof a);  //function
    function a() {
        console.log("fun");
        return 9;
    }
    a();    //fun
    console.log(typeof a);  //function
    
    var a=10;
    console.log(typeof a);  //number
    ```
   - If `var` variable and `function declaration` have same identifiers, then **`Memory creation phase`** consider that as a function and creates memory for that. 


>**Note :** **`let`** and **`const`** variable declarations also hoisted, But their scope is not in **window** object.

    
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
  
  
  
