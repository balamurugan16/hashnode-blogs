---
title: "JavaScript Array methods Explained"
seoTitle: "JavaScript Array methods"
seoDescription: "A blog explaining the JavaScript array methods like forEach, map, filter, every, some, and reduce."
datePublished: Tue Nov 14 2023 12:30:09 GMT+0000 (Coordinated Universal Time)
cuid: cloyb9vu7000c09jq5iuchhqx
slug: javascript-array-methods-explained
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1699927660057/7c233a4c-44a8-45ce-869f-53fd508cbef5.png
tags: programming-blogs, javascript

---

Arrays are a fundamental data structure that is used almost every day, unlike other data structures like a Tree or graph. JavaScript has some good methods that can be used on an array which is so easy to implement when compared to the traditional for-loop approach. In this blog, we will look at 6 JavaScript array Higher order methods, and when and how to use them with examples.

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">Before that, If you want to know about Higher-order functions in JavaScript, make sure you read <a target="_blank" rel="noopener noreferrer nofollow" href="https://balamurugan16.hashnode.dev/higher-order-functions-in-javascript" style="pointer-events: none">this blog</a>.</div>
</div>

There are a few things to note before starting,

1. All these array methods take an arrow function as one of the parameters.
    
2. This arrow function will get executed for each element of the array
    

### **ForEach**

The `forEach` method is the simplest method of all, It is similar to a for loop implemented for an array. It takes in an arrow function and executes that arrow function for each element of the loop as the name says. The function also does not return anything.

```jsx
const fruits = ['apple', 'banana', 'orange'];

fruits.forEach((fruit, index) => {
  console.log(`Fruit at index ${index}: ${fruit}`);
});
```

The arrow function can take in 3 optional parameters.

1. The first parameter is the current element.
    
2. The second parameter is the current element’s index.
    
3. The Third parameter is the array itself.
    

**The above parameter list will be similar in most of the array methods.**

### Map

The `map` method takes in an array and transforms it into another array. This method is very popular in the React world where an array is transformed into a JSX element. T

```jsx
const numbers = [1, 2, 3, 4, 5];

const squaredNumbers = numbers.map((num) => {
  return num ** 2;
});

console.log(squaredNumbers); // [1, 4, 9, 16, 25]
```

The `map` method returns the transformed array so there is a return value. Also, the callback function should return the transformed value for each element. This method also has similar parameters passed into the callback function like the `forEach` method.

### **Filter**

The `filter` method provides an easy solution to selectively extract elements from an array based on a condition. It takes an arrow function that evaluates the condition for each element, creating a new array with only the elements that pass the test.

```jsx
const numbers = [1, 2, 3, 4, 5, 6];

const evens = numbers.filter((num) => {
  return num % 2 === 0;
});

console.log(evens); // [2, 4, 6]
```

The arrow function can utilize the standard parameters—current element, index, and the array itself—just like in many other array methods.

### **Reduce**

The `reduce` method is a powerhouse for transforming an array into a single value, often used for summing up or accumulating values. It takes an arrow function and an initial value for the accumulator.

```jsx
const numbers = [1, 2, 3, 4, 5];

const sum = numbers.reduce((accumulator, current) => {
  return accumulator + current;
}, 0);

console.log(sum); // 15
```

The arrow function receives the accumulator and the current element, and it should return the updated value of the accumulator. Here, the sum of all numbers is calculated.

### **Every**

The `every` method checks if every element in an array satisfies a given condition. It returns `true` if all elements pass the test; otherwise, it returns `false`.

```jsx
const ages = [25, 30, 22, 28];

const isAdult = ages.every((age) => {
  return age >= 18;
});

console.log(isAdult); // true
```

In this example, the `every` method ensures that all ages are 18 or older.

### **Some**

Conversely, the `some` method checks if at least one element in an array meets a specified condition. It returns `true` if any element passes the test.

```jsx
const temperatures = [20, 25, 18, 22];

const hasHighTemperature = temperatures.some((temp) => {
  return temp > 25;
});

console.log(hasHighTemperature); // true
```

Here, `some` checks if there is at least one temperature higher than 25.

So that's it, Those are the 6 different JavaScript array methods that can be used in different scenarios based on your use case. I have used all these methods extensively. I hope this blog was helpful, leave a like and comment if you liked it. Until next time!