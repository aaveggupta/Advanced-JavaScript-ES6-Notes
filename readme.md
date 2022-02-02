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

# Spread Operator (...)

This operator comes in helpful when we need to **insert** elements from **one array or object into another**. All of these tasks can be accomplished without the need of any push, pop, or insert operations.

```jsx
let arr1 = [1, 2, 3];
let arr2 = [4, 5, 6];

let arr3 = [arr1, arr2];
console.log(arr3); // [[1, 2, 3], [4, 5, 6]]

arr3 = [...arr1, ...arr2];
console.log(arr3); // [1, 2, 3, 4, 5, 6]
```

# For-of Loop

When we need to **traverse** over an **array** without knowing anything about its size, then **for-of loop** comes very handy. We simply need the **name** of the array and a **for-of loop** to **iterate** over the entries in the **simplest** method possible.

```jsx
let arr = [1, 2, 3, 4, 5, 6];

for (let i of arr) {
  console.log(i);
}
```

# Template Literals

**Backticks(')** are used to symbolize template literals. Template literals may be divided into two types.

1. **Untagged Template Literals**
    
    Because these literals produce strings, they can be used for string interpolation. Anything between backticks becomes an entire string, and it's a lot easier to use than traditional string interpolation techniques!
    
    ```jsx
    let name = "Aaveg"
    
    let conventionalMethod = "Hello, My name is " + name + ".";
    let newMethod = `Hello, My name is ${name}.`;
    
    console.log(conventionalMethod);
    console.log(newMethod);
    ```
    
2. **Tagged Template Literals**
    
    Tagged template literals invokes a **function** with an **array of text segments** from the literal and **arguments that are variables** within the literal.
    
    ```jsx
    const fun = (arr, ...args) => {
      console.log(arr); // ['Hello, I am ', ', currently living in ', ' and doing graduation from ', '']
      console.log(args); // ['Aaveg', 'Gurugram', 'IIST Indore']
    };
    
    let name = "Aaveg";
    let city = "Gurugram";
    let college = "IIST Indore";
    
    fun`Hello, I am ${name}, currently living in ${city} and doing graduation from ${college}`;
    ```
    

# Array Destructuring

Let's say we have an **array** and we want to place the items of the array into **separate variables**. The standard way is to **declare** the variable and then **initialize** it based on the index of the element in the array. However, when we have a lot of variables, this technique becomes cumbersome. In these circumstances, **array destructuring** comes into play, allowing us to **initialize variables** with array items in a **single line**.

```jsx
let arr = ["Aaveg", "Gurugram", [10, "September"]];

let nameOldMethod = arr[0];
let cityOldMethod = arr[1];
let dobOldMethod = arr[2][0];
let domOldMethod = arr[2][1];

let [nameNewMethod, cityNewMethod, [dobNewMethod, domNewMethod]] = arr;
```

# Object Destructuring

**Object destructuring** works similarly to array destructuring. In a **single line**, we may assign elements of objects to variables.

```jsx
let info = {
  name: "Aaveg",
  city: "Gurugram",
  dob: {
    date: 10,
    month: "September",
  },
};

let {name: newName, city, dob: { date, month }} = info;
```

## *IN PROGRESS...*