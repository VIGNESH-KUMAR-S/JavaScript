# Datatypes in JavaScript

- Datatypes are used to represent data.
- There are 2 types in JS
    - **Primitive**
        - Number
        - BigInt
        - Boolean
        - String
        - Null
        - Undefined
        - Symbol (new in ECMAScript 6)
    - **Non-Primitive** or **Object** or **Reference**
        - Array
        - Object
        - Function
        - Date
        - Regex


1. **Number**
    - The `Number` type represents both `integer` and `floating-point` numbers and has 3 symbolic values:
        - `+Infinity`
        - `-Infinity`
        - `NaN (Not-a-Number)`
    - **Example**

        ```js 
        10/0        //+Infinity
        10/-0       //-Infinity
        -10/0       //-Infinity
        "helo"/2    //NaN
        2-"hai"     //NaN
        ```

2. **BigInt**
    - It can safely store and operate on large integers that are beyond the safe limit for Number.
    - **Example**
    ```js
    let a = 1234n;      //'n' represents this is BigInt number
    let b = 2;
    b = b*a;    //TypeError: Cannot mix BigInt and other types
    b = BigInt(b) * a;       //b=2468
    a = Number.MAX_SAFE_INTEGER;
    a = a*10;   //Expected output not come
    a = BigInt(a) * 10n;       //Expected output comes
    ```

    ```js
    Number.MAX_SAFE_INTEGER //Maximum safest integer
    Number.MIN_SAFE_INTEGER //Minimum safest integer
    Number.MAX_VALUE        //Maximum value
    Number.MIN_VALUE        //Minimum value
    ```

3. **Boolean**
    - The `Boolean` type represents a logical value that has two possible values: `true` and `false`. 

4. **String**
    - The `String` type represents textual data in JavaScript and is a set of **“elements”** of **16-bit unsigned integer** values.
    - JavaScript strings are **immutable**, i.e., once it is created, it is not possible to modify it.
    - **Example**
        ```js
        let a="helo"
        let b='helo'
        ```
    
5. **null**
    - The `Null` datatype in JavaScript only represents `null` value.
    - **Example** 
        ```js
        let a=null;     
        console.log(typeof a);  //'object'
        ```

6. **undefined**
    - The `Undefined` type represents a variable that doesn’t have any value, even though we have declared it. 
    - **Example** 
        ```js
        let a;     
        console.log(a);  //'undefined'
        ```

7. **symbol**
    - The `Symbol` type is a unique and immutable primitive value and may be used as the key of an Object property.


8. **objects**
    - The `object` type refers to the collection of primitive as well as complex data types.
    - Object properties exist in `key: value` pairs, separated by **commas**.
    - **Example**
        ```js
        let a = {
            name : 'Vignesh',
            rollNo : "171EC310",
            dept : 'ECE',
            phone : 8754890649,
            isGraduated : true
        };     
        console.log(a);
        ```
9. **arrays**
    - `Arrays` are a special type of object in JavaScript.
    - The main difference between `arrays` and `objects` is that array contents have a **natural order** and **the keys are numeric and sequential**.
    - >On the other hand, object keys can be **numeric as well as strings**. 
    - **Example**
        ```js
        let a=["viky",8754890649,'ECE',true,9.8];     
        console.log(a);
        ```

10. **functions**
    - We use functions when we want to use the same code repeatedly, but not to rewrite it every time.
    - **Example**
        ```js
        function call() {
            console.log("Called");
        }
        call();
        ```

