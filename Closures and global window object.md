- Empty file is the shortest JS program, because for this also global execution context will be created.

- Along with global execution context the global object called `**window**` also be created.

- Along with these two, `**this**` variable also created and this is same as `**window**`.

-  **window** contains lot of functions and variables, these functions and variables created by JS Engine.

- We can use the functions and variables under **window** object anywhere in the program.

- But, for function execution context **window object will not be created**.

- In the global level **this** pointing to the **window**.

- Example

    ```js
      var a=10;
      console.log(a);   //10
      console.log(window.a);    //10
      console.log(this.a);    //10
    ```
    
- Infront of `a`, if there is nothing then JS engine consider that as a global space.

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
  
  ![alt-text](https://ui.dev/post-images/function-execution-context-gif.gif)
