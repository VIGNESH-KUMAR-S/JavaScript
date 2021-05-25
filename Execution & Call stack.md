## Execution Context

- Whenever we run a JavaScript code the **Global Execution context** is created in the **Call Stack**.

- The value of variable or function is assigned during the **Code Execution** phase.

- In **Memory Creation phase** memory is allocated for variables and functions.

- During **Memory creation phase** variables assigned with `undefined` and functions with that `function body` like `key : value` pairs.

- In **JS**, `function` are treated as a mini program. So that for every function call the seperate **Execution context** will be created in the **Call Stack**.

- The created **Execution context** will be popped in the **Call Stack** when the **Code execution phase** execute the **`return `** statement.

- Finally, if **JS** program ends, the **Global Execution context** also popped in that **Call Stack**.

- Example :
    ```js 
    var n = 2;
    function double(num) {
      var ans = num * 2;
      return ans;
    }
    var double1 = double(n);
    var double2 = double(4);
    ```
    
- So when you run this program, `Global Execution Context` is been created.

- This execution context is created in two phases:
    - **Memory Creation Phase**
    - **Code Execution Phase**

  **Memory Creation Phase**
    - In this phase, Javascript will read the code line by line and allocate memory to all the variables and functions.

    - When it allocates memory to the variables, it stores a special value **`undefined`**.

    - For functions, it stores the **`whole function body`** inside this memory space.

    - During the Memory Creation phase, the Execution context looks like :
    
      |Memory Component|Code Component|
      |---|---|
      |n : undefined|
      |double : {..body..}|
      |double1 : undefined|
      |double2 : undefined|
   
  **Code Execution Phase**
    - In this phase, Javascript again runs through the code line by line and updates the values of function and variables which are stored earlier in Memory Creation Phase.

    - After executing line 1: var n = 2;, the Global execution context will look like this:
        |Memory Component|Code Component|
        |---|---|
        |**n : 2**|
        |double : {..body..}|
        |double1 : undefined|
        |double2 : undefined|
    
    - **from line 2 to line 5, there is nothing to execute, so it skips that part.**

    - >At line 6: var double1 = double(n);

    - Here we invoke a function double(),

    - >**Whenever a new function is invoked, a new execution context is been created**

    - So, for the function double(n), JS creates a new execution context.

    - Phase 1: Memory Creation Phase for newly created execution context will look like this:

      ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1609796718689/WSACHjpxE.png?auto=compress)
      
    - Phase 2: Code Execution Phase for newly created execution context will look like:

      ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1609797057770/R374Z-r3F.png?auto=compress)
      
    - *In this phase, the value of parameter **num** is updated according to the argument passed to the function i.e. n, which is equal to 2.*

    - Next, the value of ans is updated using the expression num * 2.

    - **Whenever we encounter return statement:**

        - It gives the whole control back to the execution context where the function was invoked.
        - Whole execution context for the instance of that function will be deleted.

    - After executing line 4: return ans;, the current scenario will look like this:
      
      |Memory Component|Code Component|
      |---|---|
      |n : undefined|
      |double : {..body..}|
      |double1 : 4|
      |double2 : undefined|
      
     - The **Execution context** created by `double1` will popped out (deleted) in **Call Stack**.

     - `After executing line 7: var double2 = double(4);`, the same process is repeated as above:

        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1609798410286/xFo7iAyP2.png?auto=compress)
        
- After completing the `double2` the **Global Execution context** looks like :

  |Memory Component|Code Component|
  |---|---|
  |n : undefined|
  |double : {..body..}|
  |double1 : 4|
  |double2 : 16|
      
- **When JavaScript completes the execution of the entire code, then the Global Execution Context is also deleted.**

  ## Call Stack 

- Whenever a JavaScript code is run, the **Call Stack** created and the **Global Execution context** is pushed into the **Call Stack**.

- >**Call stack maintains the order of execution of execution contexts.**

- It is also called as,
    - Execution context stack.
    - Program stack.
    - Control stack.
    - Runtime stack.
    - Machine stack.

**Call Stack Work flow**

1.
  ||
  |---|
  |Global Execution context|
  
2.  
  ||
  |---|
  |double1(n)|
  |Global Execution context|
  
3.  
  ||
  |---|
  |~~double1(n)~~|
  |Global Execution context|
  
4.  
  ||
  |---|
  |Global Execution context|
  
5.  
  ||
  |---|
  |double2(4)|
  |Global Execution context|
  
6.  
  ||
  |---|
  |~~double2(4)~~|
  |Global Execution context|
  
7.  
  ||
  |---|
  |Global Execution context|
  
8.  
  ||
  |---|
  |~~Global Execution context~~|
  
9.  
  ||
  |---|
  |(emptied)|


