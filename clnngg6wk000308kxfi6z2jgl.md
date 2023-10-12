---
title: "Singleton Pattern"
datePublished: Thu Oct 12 2023 17:29:51 GMT+0000 (Coordinated Universal Time)
cuid: clnngg6wk000308kxfi6z2jgl
slug: singleton-pattern
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/npxXWgQ33ZQ/upload/d5904928588aeb043b8dba1a725727d1.jpeg
tags: design-patterns, javascript, typescript, programming-ciovqvfcb008mb253jrczo9ye

---

![Factory produced more than one instance of Singleton | ProgrammerHumor.io](https://programmerhumor.io/wp-content/uploads/2021/07/programmerhumor-io-programming-memes-f98afcf6e4b8b5b-608x344.jpg align="center")

> People who understood the above picture don’t need to read this article, you already understood the pattern but those who didn’t get it, stay tuned to where I will explain it at the end.

The most popular pattern, and usually the pattern that is covered first when the topic of design patterns comes is the **Singleton pattern**. The idea here is to share a single global instance throughout the application. I will first explain how this pattern works and will share my thoughts on this pattern because I feel that this pattern should be an anti-pattern rather than a design pattern.

### Overview

So with the Singleton pattern, basically we restrict the information of certain classes to one single immutable object that can be accessed globally throughout the application. For example, we can have a counter instance with methods like `increment`, `decrement` and `currentCount`.

The increment method increments the value of the counter by 1. Any time this method is called anywhere in the application, it affects the single instance of the counter that has been created. This makes sure that there is only a “Single source of truth”.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697131612739/613a12c6-1357-41fe-b0a1-49bc94a13346.png align="center")

### Implementation:

```jsx
let instance;

class Counter {
  constructor() {
    if (instance) {
      throw new Error("You can only create one instance!");
    }
    this.counter = counter;
    instance = this;
  }

  getCount() {
    return this.counter;
  }

  increment() {
    return ++this.counter;
  }

  decrement() {
    return --this.counter;
  }
}

const singletonCounter = Object.freeze(new Counter());
 
export default singletonCounter;
```

1. Creating the `Counter` class, which contains a `constructor`, `getInstance`, `getCount`, `increment` and `decrement` method. Within the constructor, we check to make sure the class hasn't already been instantiated.
    
2. Setting a variable equal to the frozen newly instantiated object, by using the built-in `Object.freeze` method. This ensures that the newly created instance is not modifiable.
    
3. Exporting the variable as the `default` value within the file to make it globally accessible.
    

### Is it an Anti Pattern?

One of the most overused patterns in the programming industry is the singleton pattern. This is my opinion and always anyone can have any opinions. I couldn’t think of any use case for this pattern because of the hidden tradeoffs that it has. What do I mean by it? This pattern surely gives an advantage by restricting the instantiation of multiple instances and saving memory but at the same time, This pattern gives short-term simplicity by giving up long-term scalability and maintainability. When It comes to unit testing, since we can’t create new instances each time, all tests rely on the modification to the global instance of the previous test. The order of the test matters in this case, and one small modification can lead to an entire test suite failing. In JavaScript, ES modules are by default singletons, meaning we not need to create singleton to achieve this behavior.

Sure it has a great use case, for example, for state management, the Redux library has a store that follows the singleton pattern, one instance of the store is available throughout the runtime of the application which makes an excellent use case of the singleton pattern. Redux also uses the observer pattern by allowing to subscribe to the store to get the values. To know more about observer patterns, [read this article](https://balamurugan16.hashnode.dev/observer-pattern).

### Conclusion

The motive of this article is not to trash talk about the Singleton pattern, but to explain the pattern itself and to analyze whether a particular pattern is useful. My opinions are totally against the singleton pattern but you may find some good use case for it. Singleton pattern can be a great tool for some libraries like Redux but not in a real-world application.

> The image above has multiple instances of singletons!