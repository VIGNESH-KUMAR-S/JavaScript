# Closures
- A closure is the **combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment)**. 
- In other words, a closure gives you access to an **outer function’s scope from an inner function**. 
- In JavaScript, **closures are created every time a function is created, at function creation time**.
- Closure is based on scoping chain and lexical environment.

Example : 1
```js
  function x() {
    let a = 10;
    function y() {
        const c = 99;
        console.log(a, c);
    }
    y();
  }
  x();
```
- Here, function y access the outer variable a in x function based on closures.
- **`a` is present in `function x()`, whereas in `function y()` the reference to `a` only stored in closure, value of `a` not stored**.

Example : 2
```js
  function x() {
    let a = 10;    
    function y(c) {
        console.log(a, c);
    }
    return y;
  }
  x()(6);
```
- Here, the `function x()` returns `function y()` , after returning that `function y()` the `function x()` pop out in the call stack.
- After pop out of `function x()` , how the variable **`a`** in **x** function visible to **y** function ? Because of Closure.

## Though the outer function removed from stack, the inner function still access to its outer functions variable

- **Closure is the combination of function with it's lexical scope**.
- At the function creation time of `function y()`, the closure created and stored with it's lexical scope.
- When the function called, JS engine looks where the function body presents. Not looks where the function called.

Example 3 :

```js
  function add5(){
    const a=5;
    return function add(b){
      return (a+b);
    }
  }
  add5(); // function add(b) {...}
  let add3 = add5()(3); //8
  let add55 = add5()(55); //60
```

- Here `add()(3)` and `add()(55)` shares the same function body but different values of `b`

Example 3 :

```js
  function multiplier(factor){
    return number => number * factor;
  }

  let twice = multiplier(2);
  let thrice = multiplier(3);
  console.log("twice--> ", twice);
  console.log("first call--> ", twice(5));
  console.log("second call--> ", thrice(8));

```
- `twice` and `thrice` are both closures. They share the same function body definition but store different lexical environments. 
- In the `twice` lexical environment, a factor is 2, while in the lexical environment for `thrice`, a factor is 3.

# Uses of Closures
1. Module design pattern
2. Object data privacy
3. Event handlers
4. Asynchronous Programming
5. Currying
6. function like once
7. Memoization
8. setTimeouts
9. Iterators
10. etc...
