# setTimeout

```js
   function x() {
    i = 1;
    setTimeout(function example(){    
      console.log(i);
    },3000);
  }
  x();
```
- setTimeout stores the `example function` somewhere in the memory and attached the timer to it.

## Why the statement after the setTimeout execute before execution of function in setTimeout:
```js
   function x() {
    i = 1;
    setTimeout(function example(){    
      console.log(i);
    },3000);
  }
  x();
  console.log("First");
```
- Because, JS won't wait for anything.
- setTimeout stores the function with timer in somewhere, after that it'll start executing the next line.
- It won't wait for the time to complete the setTimeout function.
- If the timer reaches it's time then automatically that particular function executed.
- If timer ends, then only the function pushed to the call stack.

## Print first 'n' numbers with one second gap
```js
   for(var i=1; i<=5; i++) {
    setTimeout(function example(){    
      console.log(i);
    },i*1000);
  }
```
- **Why the output is always `6`**
- Because of closure
- According to this program, closure is the combination of `function example` and it's lexical environment (reference to `i`).
- For every iteration the setTimeout created and attached the function with timer in some place.
- Since the loop is terminated before execution of all the setTimeout functions, because JS engine works fast right.
- After termination of loop and also after some time, the first setTimeout function executed.
- At the execution time of setTimeout function, the value of `i` becomes `6`.
- So, the setTimeout function uses the reference of `i` variable.
- Also the `var` variable are `global`.

## Solution for above problem
```js
   for(let i=1; i<=5; i++) {
    setTimeout(function example(){    
      console.log(i);
    },i*1000);
  }
```
- **Why it works fine**
- `let` is the block scoped variable.
- Since for every iteration, the `i` variable created and destroyed like that.(Doubt)
- So that when we call setTimeout function, it uses seperate references of `i` variable.

## By using `var` variable
```js
   for(var i=1; i<=5; i++) {
    function close(i) {
        setTimeout(function example(){    
            console.log(i);
        },i*1000)
    }
    close(i);
}
```

- Closure helps us.
- For each and every function creation, the seperate closure will be created. 
- Here, closure created with `function close` and it's lexical environment (reference to variable `i`) for every iteration.
- Here for every iteration I'll call a function with current value of `i`.
- Since the setTimeout function called for every iteration with new `i` variable.
- **Lexical environment** contains **Environment record** and **Reference to it's outer scope**.
