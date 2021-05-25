- Everything in **JavaScript** happens in **Execution context**.
- **Execution context** contains two components => `Memory` and `Code` Components.
- **Memory Component** contains `key:value` pair of all the variable and functions.
- Example :
    ```js
    const a=2;
    var b=22;
    function multiply(a,b) {
      let x=a;
      let y=b;
      x = x*y;
      return x;
    }
    console.log(multiply(a,b));
    ```
    
- `key:value` pairs for the above code :
  - a:2
  - b:22
  - multiply:{ let x=a; ....   }
- **Code Component** is the place where the *JavaScript* code is executed line by line.
- **JavaScript is a synchronous single-threaded language.**
- JavaScript can execute only one line at a time in a specific order.
- It executes the next line only the current line executed successfully.
- **Memory Component** also called **Variable environment**.
- **Code Component** also called **Thread of Execution**.
- If we run the JS program, then **Execution context** will be created.
- Execution context created in two phases => **Memory creation** and **Code execution** phase.
