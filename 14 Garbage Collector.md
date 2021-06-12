# Garbage Collector
- [javascriptinfo garbage collector](https://javascript.info/garbage-collection)

- **Garbage Collection** is a mechanism to remove the unused or unreachable statement in JS.
- This is done automatically by JS.
- Example

  ```js
    let obj = {
      "a" : 12,
      "b" : 13
    }
    
    obj = "string"
  ```
  - Here the properties are deleted and it's not possible to reach again.
  
  
 # Garbage collector in closure
 - Closure have one disadvantage that, it takes lots of memory usage.


 ## Why it takes high memory ?
 - Because the closure of particular function stores the information of all of it's parent lexical environment.
 - Garbage collector not able to delete parent's scope, if anyother function used the reference of it's parent scope.
 - Though the parent function is deleted, parent function pop out in the call stack, still the nested inner function access parent's scope based on closure.
 - That's why it takes high memory.
  ```js
  function x() {
    let a=9;
    let b=99;
    function y(c) {
      console.log(b+c);   //100
    }
    y(1);
  }
  x();
```
- Here, `function y` forms closure with combination of **`function y and a and b`** . 
- Though `a` not used in inner function , `a` is referenced by inner function.
- This problem will be omitted in some smart JS engines.

## Some smart engines (chrome V8)
- Here the closure of `function y` is created with **`function y and b`** variable only.
- Because `a` variable not used in inner function.

![In V8 chrome engine](https://github.com/VIGNESH-KUMAR-S/JavaScript/blob/main/Images/Garbage%20collector.png)
