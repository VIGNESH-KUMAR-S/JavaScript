# Lexical Environment
- Every time the JavaScript engine creates an `execution context` to execute the function or global code.
- It also creates a **`new lexical environment`** to store the variable defined in that function during the `execution` of that function.
- For each execution context the seperate **Lexical Environment** will be created.
- It stores the things (Variables, functions,...) in `key:value` pairs.
- The Lexical Environment is not done physically, it's done backend in the JS engine (Doubt).
- It contains two components :
    1. Environment record :
        - It's the actual place where the variable and function declarations are stored.
        - It stores all the variables and functions which present in current execution context.

    2. Reference to the outer lexical environment :
        - It means it has access to its outer (parent) lexical environment.

It's look like this
```js
  lexicalEnvironment = {
    environmentRecord: {
      <identifier> : <value>,
      <identifier> : <value>,
      .
      .
      .
      
    }
    outer: < Reference to the parent lexical environment>
  }
```

**Example :**

```js
    let language = 'JS';
    function a() {
      let b = 25;  
      console.log('Inside function a()');
    }
    a();
    console.log('Inside global execution context');
```
- When the JavaScript engine creates a global execution context to execute global code.
- It also creates a new lexical environment to store the variables and functions defined in the global scope. 
- So the lexical environment for the global scope will look like this:

```js
    globalLexicalEnvironment = {
      environmentRecord: {
          language    : 'JS',
          a : < reference to function object >
      }
      outer: null
    }
```

- Here the outer lexical environment is set to **`null`** because there is **no outer lexical environment for the global scope**.

- When the engine creates an execution context for a() function,
- It also creates a lexical environment to store variables defined in that function during the execution of the function. 
- So the lexical environment of the function will look like this:

```js
    functionLexicalEnvironment = {
      environmentRecord: {
          b    : 25,
      }
      outer: <globalLexicalEnvironment>
    }

```

## When Lexical environment removed(deleted)

- When a function completes, its execution context is removed from the stack.
- But its lexical environment may or may not be removed from the memory.
- It's depending on if that lexical environment is referenced by any other lexical environments in their outer lexical environment property.
- If there is any need of the current lexicle environment for the outer lexicle environment or any other lexicle environment then the current lexicle environment not deleted.

## Lexical Scope 
- Lexical Scope means that in a nested group of functions, the inner functions have access to the variables and other resources of their parent scope. 
- This means that the child's functions are lexically bound to the execution context of their parents. 
- **Lexical scope is sometimes also referred to as Static Scope.**


```js
  function a() {
        let a = 1;
        function b() {
              function c() {
                    console.log(a);
              }
              c();
        }
        b();
  }
  a();
```

- Here, `a` searched in current scope if not present then searched in it's parent scope, if not .... upto **Global lexicle environment(Global space)**.
- If the variable not present in Global scope also then we are getting an error.

## Scoping chain
- **The Scope Chain is the hierarchy of scopes that will be searched in order to find a function or variable.**
- When asked to find a variable, JavaScript always starts at the innermost level of the code nest and keeps jumping back to the parent scope until it finds the variable or any other resource it is looking for.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1610133490141/DgG9zwudY.png?auto=compress)

