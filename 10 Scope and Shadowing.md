# Scope

- **Scope** is the part of program which tells about an variable or function information.
- Where the variable's or function's created, where it'll be destroyed.
- In the program file, in which place only we should use that variable or function.
- Types :
    - Block scope
    - Global scope
    - Function scope

- Example :

    ```js
      let a=10;
      {
        let a = 100;
      }
    ```
    
- We can declare same identifier names but it should differ in their scopes.

## Block scope
- In JavaScript, a Block is a **compound statement** that is defined by curly braces {}.
- It used to combine multiple statements into one statement where JavaScript expects only one statement.

# Shadowing 
- In programming languages, variable shadowing occurs when a variable is declared in certain scope has the same name defined on it’s outer scope. 
- And when we call the variable from the inner scope, the value mentioned in inner scope will be taken into account.


```js
  let a=10;
  {
    let a=100;
    {
      let a=1000;
      console.log(a); //1000
    }
    console.log(a); //100
  }
  console.log(a); //10
```
- Here, three blocks used with same identifier name.
- The value of `a` is current block scope value only.

## Illegal Shadowing

```js
  let a=10;
  {
    let a=100;
    {
      var a=1000; //Error
    }
  }
```

- If we use same name, then all the variables should in different scope.
- But here `var` variable are global scope.
