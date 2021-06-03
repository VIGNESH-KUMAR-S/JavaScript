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
