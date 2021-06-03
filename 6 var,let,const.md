These three are used to create datatypes.

# var

- `var` statement used to create a variable in **Global or Function** scoped.
- **Scope** essentially means where these variables are available for use.
- If `var` is declared outside of all functions then it's **Globally** scoped.
- If `var` is declared inside the function then it's **Function** scoped.
- **Example**
    ```js
        var a=10;   //Global scope
        function scope() {
            var b=10;
            var a=b;    //Function scope
        }
        console.log(a);     //10
    ```

- `var` variables are redeclared and updated
    ```js
        var a=10;
        a=20;
        var a=30;
        var a='helo';
        var a=3.4;
        function a() {
            console.log("a fun");
        }
    ```

- The above is the **Problem** in `var`.

- `var` variables are **Hoisted**.

# let and const

- `let` and `const` introduced in **ECMAScript 2015**.
- These two are **Block** scoped.
- Block scope : **{block}**. (Inside curly braces).
- **const** should be declared and defined at the same time.
- **let** can't be redeclared but updation is possible.

- **Example**
    ```js
        let a=10;
        a=20;
        let a=9;    //error
        -------------------------------------------------------------------
        console.log(typeof a);  
        //error: cannot access before initialization
        let a=19;
        -------------------------------------------------------------------
        let a;  
        //assigned `undefined` during "Thread of execution" phase (Doubt)

        console.log(typeof a);  //undefined
        let a=19;
        console.log(typeof a);  //number
        -------------------------------------------------------------------
        console.log(typeof a);  
        //error: cannot access before initialization
        const a=19;
    ```

# SUMMARY

- **`var`** declarations are globally scoped or function scoped while **`let`** and **`const`** are block scoped.
- **`var`** variables can be updated and re-declared within its scope; **`let`** variables can be updated but not re-declared; **`const`** variables can neither be updated nor re-declared.
- They are all hoisted to the top of their scope. But while **`var`** variables are initialized with `undefined`, *`let`** and **`const`** variables are not initialized.
- While **`var`** and **`let`** can be declared without being initialized, **`const`** must be initialized during declaration.
- **var VS let VS const**
```
var:
  function scoped
  undefined when accessing a variable before it's declared

let:
  block scoped
  ReferenceError when accessing a variable before it's declared
const:
  block scoped
  ReferenceError when accessing a variable before it's declared
  can't be reassigned
```
