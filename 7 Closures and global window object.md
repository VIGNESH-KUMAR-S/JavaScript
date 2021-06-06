- Empty file is the shortest JS program, because for this also global execution context will be created.

- Along with global execution context the global object called **`window`** also be created.

- Along with these two, **`this`** variable also created and this is same as **`window`**.

-  **window** contains lot of functions and variables, these functions and variables created by JS Engine.

- We can use the functions and variables under **window** object anywhere in the program.

- But, for function execution context **window object will not be created**.

- **window** object created only once at, when the **Global execution context** is created, but we can use it anywhere by using **window**.

- **this** also represents **windows** in global level.

- Example

    ```js
      var a=10;
      console.log(a);   //10
      console.log(window.a);    //10
      console.log(this.a);    //10
    ```
    
- This is applicable for `var` type variables only, but not for `let` and `const`.
- Because `let` and `const` are not stored in `window` object.
- (Infront of `a`, if there is nothing then JS engine consider that as (`window.a`) a global space.)Doubt

- **window** represents global object only.

- **window** object created only during global execution context only.

- Example

    ```js
      var a=1;
      console.log(a);   //1
      console.log(window.a);    //1
      console.log(this.a);    //1
      function b() {
          var a=2;
          console.log(a);   //2
          console.log(window.a);    //1
          console.log(this.a);    //1
      }
    ```
    
# Global Window object
- When the global execution context is created, by default there is two things will be created by JS engine called **window** and **this** .
- At global scope, `this` will reference the global object which will be `window` if you’re running JavaScript in the browser or `global` if you’re running it in a Node environment.
- For empty js file
    ![](https://ui.dev/post-images/no-code.png)

- Files with variables and functions
    - Phase 1
    ![](https://ui.dev/post-images/global-variables-in-creation-phase.png)
    - Phase 2
    ![](https://ui.dev/post-images/global-variables-in-execution-phase.png)
    
    
## What happened when Global Execution Context will be created
    1. Create a global object called `window`.
    2. Create an object called `this`.
    3. Set up memory space for variables and functions.
    4. Assign variable declarations a default value of `undefined` and function declarations with that piece of code.

## What happened when Function Execution Context will be created
    1. Create an arguments object.
    2. Create an object called `this`.
    3. Set up memory space for variables and functions.
    4. Assign variable declarations a default value of `undefined` and function declarations with that piece of code.
    
  Example of **Function Execution Context**
  
  ![](https://github.com/VIGNESH-KUMAR-S/JavaScript/blob/main/Images/function-execution-context-1.gif?raw=true)
  
  **Nested loops**
  - When a function is defined in another function, the inner function has access to the outer function’s variables. This behavior is called **lexical scoping**.


  ![](https://github.com/VIGNESH-KUMAR-S/JavaScript/blob/main/Images/javascript-execution-stack.gif?raw=true)
  
  - If the JavaScript engine can’t find a variable in that local to the function’s Execution Context, it’ll look to the nearest parent Execution Context for that variable.
  - This lookup chain will continue all the way until the engine reaches the Global Execution Context. 
  - In that case, if the Global Execution Context doesn’t have the variable, it’ll throw a `Reference Error`.

       ![](https://github.com/VIGNESH-KUMAR-S/JavaScript/blob/main/Images/parent-lookup.gif?raw=true.gif)
        
  - The child function will still have access to the outer function’s scope, even after the parent function’s Execution Context has been removed from the Execution Stack.

       ![](https://github.com/VIGNESH-KUMAR-S/JavaScript/blob/main/Images/closure-scope.gif?raw=true.gif)
        
  - Here, the `inner` function is nested inside of the `makeAdder` function, so `inner` creates a **Closure** over the `makeAdder` variable environment. Even after the `makeAdder` Execution Environment has been popped off the `Execution Stack`,`inner` access it's parent's variables and functions, because that `Closure Scope` was created.
  - Since, `inner` has access to the `x` variable (via the Scope Chain).


