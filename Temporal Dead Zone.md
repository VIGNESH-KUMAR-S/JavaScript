# Temporal Dead Zone
## Is `let` and `const` variables are not hoisted?
- No, It's hoisted.
- Then why the reason, we can't access before declaration.
- Because of **Temporal Dead Zone**
- Example :
    ```js
    console.log(a); //`a` not used before initialization
    ;;;;;
    const b=9;
    let a;
    console.log(a+"+"+9); //undefined+9
    ```
## For the above code, where is Temporal Dead Zone presents:
- Temporal Dead Zone is not for whole program but for particular variables.
- In the above code, upto the line `let a;` the **Temporal Dead Zone** contains `a` and after executing that line it'll be released from **TDZ**.
- So we can't access any variables which present in **Temporal Dead Zone**.
- **Temporal Dead Zone** for a variable is that **the time between that variable hoisting and that variable declaration**.
- If we access variable presents in **Temporal Dead Zone**, then we are going to get **Reference Error : `variable` should not be used before initialization**.

## Where the let and const are get undefined
- Like `var` , `let` and `const` also initialized with `undefined`.
- But this is not happening in `Global Object`, whereas it'll be happening in some other `Script` or `Block` or some other spaces.

## How to prove that let and const are hoisted

```js
  console.log(typeof notInThisProgram);  //undefined
  console.log(typeof a);  //Reference Error : `a` not used before ...
  
  let a=10;
```

- In the above example, the `typeof` undeclared variable is `undefined`, but for declared variable it's not.
