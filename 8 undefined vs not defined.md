# undefined

- `undefined` is a property in `global object`(window).
- The `global undefined` property represents the primitive value `undefined`. It is one of JavaScript's primitive types.
- If variable declared but not initialized then JS engine defaultly initialize `undefined` to it.
- Example :

    ```js
      console.log(typeof undefined);  //undefined
      console.log(window.undefined);  //undefined (In chrome)
      
    
      var a;
      console.log(a); //undefined
      a = 11;
      console.log(a); //11
    
      const a=undefined;
      console.log(a);  //undefined
    ```
- In the last two lines, we explicitly give `undefined` to const though it's work fine it's not good practice.
- **Actually if variable is not assigned then `undefined` assigns to it , but not for `const` it should declare and initialize at same time**.
- We have initialize `undefined` also to const variable.
    
## not defined

- If a variable is not at all declared, then that's not-defined.
- Example :

    ```js
      ;;;;
      console.log(x)  //Error:`x` is not defined
    ```
