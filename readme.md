# Advanced JavaScript Notes [ES6]

### Prepared by Aaveg Gupta

# Var, Let and Const

- **let** and **const** introduced in 2015 (**ES6**)
- Only **var** was available prior to ES6, and we had to utilize var with certain error handling techniques if we wanted to use **const** at all.
- Although var and let do the same thing, there are two fundamental distinctions between them.
    - **Global variables** defined using **var** are a property of the **window object**, while there is none in the case of **let**.
        
        ```jsx
        var numVar = 10;
        console.log(window.numVar); // 10
        
        let numLet = 10;
        console.log(window.numLet); // undefined
        ```
        
    - It is possible to **redeclare va**r, but **redeclaring the let variable will result in an error**.
        
        ```jsx
        var numVar = 10;
        var numVar = 20;
        console.log(numVar); // 20
        
        let numLet = 10;
        let numLet = 20; // Will give error as we can't redeclare let variable
        console.log(numLet);
        ```
        

# Default Parameter

Let's assume there's a function that **adds** two integers with **two arguments**. Let's say we **forget** to give any parameters to the function, in this situation, the **arguments are undefined**, resulting in a **faulty response**. **To address** this problem, we may provide some **default values** to the **arguments**, which will be used **if no arguments are provided**.

```jsx
const add = (num1 = 2, num2 = 3) => num1 + num2;

console.log(add(4, 8)); // 12
console.log(add()); // 5 because default value of arguments are 2 and 3
```

# Rest Parameter

Assume there is a function that **adds** integers supplied as parameters, however the number of inputs might range from one or more. **Rest parameters** come in handy in these situations since we can use them to take as many arguments as we like by creating the **...args** (you can rename args to anything) as parameter of a function. As a result, everything you pass will be converted to an **array** and **stored in args**!

```jsx
const add = (...args) => {  // args is an array, containing the elements passed to the function
  let sum = 0;
  for (let i = 0; i < args.length; i++) {
    sum += args[i];
  }
  return sum;
};

console.log(add(4, 8)); // 12
console.log(add(1, 2, 3, 4, 5)); // 15
```

## *IN PROGRESS...*