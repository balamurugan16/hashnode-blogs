---
title: "Higher-order functions in JavaScript"
datePublished: Mon Oct 02 2023 16:31:30 GMT+0000 (Coordinated Universal Time)
cuid: cln93ymum000108ml3pld9l5j
slug: higher-order-functions-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/eYpcLDXHVb0/upload/1f33b99aa3fc232cdb9d5aee79a4f1ad.jpeg
tags: javascript, programming-ciovqvfcb008mb253jrczo9ye

---

This blog focuses on Higher-order functions, what problem it solves, and how to use them in your daily life as a JavaScript developer. JavaScript already has a lot of built-in higher-order functions like `map`, `forEach`, `reduce`, etc. But how they work internally is fun to know and learn and this is a pretty common interview question, (Trust me! It is). This is not that graph data structure that you learned for your interview and never used anywhere in the real world, HOF (higher-order functions) are the foundation for the higher-order components that you see in React!

So let’s dive in!

Before dealing with HOF, In JavaScript a function is like any other value, it can be stored in a variable, passed as an argument, and so on. See the below example!

```typescript
const onClick = (e) => {
	console.log(e.target.value);
}

let array = [1,2,3];
array.forEach((value) => {
	console.log(value);
})
```

In the above example, notice that I am declaring the function as a variable, with the const keyword. The second example `forEach` is a function that is receiving another function as an argument! This knowledge is key to understanding HOF!

So we will start with a function and try to optimize it until we understand HOF! See the following code.

```typescript
function doubleTheArray(input: number[]) {
    const output = [];
    for (let i = 0; i < input.length; i++) {
        output.push(input[i] * 2)
    }
    return output;
}

function tripleTheArray(input: number[]) {
    const output = [];
    for (let i = 0; i < input.length; i++) {
        output.push(input[i] * 3)
    }
    return output;
}

function quadrupleTheArray(input: number[]) {
    const output = [];
    for (let i = 0; i < input.length; i++) {
        output.push(input[i] * 4)
    }
    return output;
}
```

So here, I have 3 functions that receive an array, do a manipulation to the array, and return a new array. The outputs of all these functions will look like this.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1696264182744/a6115454-8302-41f4-9073-9d9e89f01951.png align="center")

If you look closely, all the functions are basically having the same code except the logic that we use inside the `output.push()` function. So now let’s optimize this code.

```typescript
function manipulateArray(input: number[], callback: (value: number) => number) {
    const output = [];
    for (let i = 0; i < input.length; i++) {
        output.push(callback(input[i]))
    }
    return output;
}

const output1 = manipulateTheArray([1,2,3], (a) => a * 2)
const output2 = manipulateTheArray([1,2,3], (a) => a * 3)
const output3 = manipulateTheArray([1,2,3], (a) => a * 4)

console.log(output1, output2, output3)
```

If you see here in this example, The code that is varying in all three functions is replaced with a function call. Now the user can decide what to do with the array elements rather than having 3 different functions for a particular use case. In this example, I am passing a function that takes a number and manipulates it. Now If I want the array elements to be multiplied by 5 I can use the same `manipulateArray` function instead of writing a whole new function. This follows the DRY principle (Don’t repeat yourself).

If you look closely, the `.map` function does exactly the same. Let me rewrite the above example.

```typescript
const array = [1,2,3]

const output = array.map((a) => a * 3)

console.log(output);
```

Whatever we wrote previously is already available in JavaScript as a higher-order function. `map`, `forEach`, and `reduce` are methods that are used quite frequently and now you can use them without any confusion as you know how they work under the hood.

This is called a higher-order function. A “higher-order function” is a function that accepts functions as parameters and/or returns a function. We didn’t cover the returning a function part which will be covered when we deal with Higher order components in React (A react component is basically a function!). Until then, Tata!