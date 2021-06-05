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
    
    ```
    
## not defined

- If a variable is not at all declared, then that's not-defined.
- Example :

    ```js
      ;;;;
      console.log(x)  //Error:`x` is not defined
    ```
