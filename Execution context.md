- Everything in **JavaScript** happens in **Execution context**.

- **Execution context** is defined as the environment in which the JavaScript code is executed.

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

- **Code Component** is the place where the **JavaScript** code is executed line by line.

- **JavaScript is a synchronous single-threaded language.**

- **Single-threaded** means JS can only execute one command at a time.

- **Synchronous** means JS can only move on to the next line only when the execution of the current line has been finished.

- **Memory Component** also called **Variable environment**.

- **Code Component** also called **Thread of Execution**.

- If we run the JS program, then **Global Execution context** will be created.

- Execution context created in two phases => **Memory creation** and **Code execution** phase.
