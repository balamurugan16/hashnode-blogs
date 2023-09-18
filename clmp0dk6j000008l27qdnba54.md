---
title: "Does Clean Code really matter?"
datePublished: Mon Sep 18 2023 14:55:44 GMT+0000 (Coordinated Universal Time)
cuid: clmp0dk6j000008l27qdnba54
slug: does-clean-code-really-matter
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/LrxSl4ZxoRs/upload/a739e573ab5e3ee96cc45d8016716874.jpeg
tags: clean-code, programming-languages

---

![Programmers looking at my code : your code is disgusting | programmer-memes, code-memes, program-memes | ProgrammerHumor.io](https://programmerhumor.io/wp-content/uploads/2022/11/programmerhumor-io-programming-memes-59035894291b969-608x613.jpg align="center")

Cooking is an art, just like coding. It should be hygienic and done with care because people will consume the end product. Adding garnishes to your food makes it more appealing. Similarly, in programming, clean code is crucial. It ensures that your code is accessible to your colleagues and adheres to coding standards. Try this activity, take some piece of code that you have written, give it to ChatGPT and ask to roast your code. You can also give the code written by your co-worker whom you don't like or wanna take sweet revenge and enjoy!

![I asked ChatGPT to roast my code. I never want to code again | code-memes, variables-memes, try-memes, bug-memes, date-memes, IT-memes, rds-memes, variable name-memes | ProgrammerHumor.io](https://programmerhumor.io/wp-content/uploads/2023/06/programmerhumor-io-debugging-memes-databases-memes-34c48a7c81bfbcd-608x413.png align="center")

With that said, Let's discuss the importance of clean code, methodologies, tools, and common misconceptions🚀😊.

### What is "Clean Code"?

Clean code is the holy grail. It's error-free, easy to read, and follows best practices. We're talking about code that makes sense, whether you're coding in TypeScript or any other language. Let's break down the essentials.

**Proper Naming: 🏷️**

Imagine naming your variables, functions, classes, and files sensibly, just like naming your dishes. Compare these two:

```ts
const isLoading = false;

// Avoid
const x = true;
```

The `isLoading` variable communicates its purpose, while `x` leaves you scratching your head. Consistency in naming conventions is key. Camel case is common in TypeScript, but if you feel like using snake case and you and your team can stay consistent with it, then go for it 🐍.

**Unit Testing: 🧪**

I used to skip unit testing for most of my career 🙈, but when I finally gave it a shot, oh boy, did I have an awakening! 🚀 More than just testing, it's the mindset shift that struck me. Writing testable code nudged me toward clean code practices. Not every piece of code is a testing candidate; if it's poorly implemented, testing becomes a nightmare🧩. But the confidence boost from unit testing is like a shot of espresso for a developer! ☕ And when that refactor season arrives, your trusty unit tests will be there to make sure it's a smooth ride, keeping the codebase as error-free as a sunny day😎. I've been exploring tools like Vitest lately, and let me tell you, it's a game-changer! 🎮 Especially the Vitest UI—it's a total knockout feature! 💥. So, yes, I've joined the unit testing fan club, and it's been a game-changer🤩. Most of the time, if you write your code well, you won't need to do much mocking. And let's be real, mocking your code can be as frustrating as a riddle without an answer!🤯. As for Test Driven Development (TDD), well, let's just say it's not my cup of tea. ☕ So No thanks! 😄

![Unit test tiers | code-memes, test-memes, unit test-memes, date-memes, tests-memes | ProgrammerHumor.io](https://programmerhumor.io/wp-content/uploads/2023/08/programmerhumor-io-testing-memes-programming-memes-6490bdb9c7e144b-608x658.png align="center")

**Consistent Formatting and Linting: 🧹**

Proper formatting is the backbone of clean code. Poorly formatted code is like serving a messy plate. It's not only hard to digest but also reflects a lack of care. Properly formatted code, on the other hand, is a treat for your fellow developers. And linting? It's another tool in your clean code arsenal. Tools like ESLint and Prettier help you maintain quality. Pro tip: Stick with Prettier for formatting; ESLint is for linting. You can even automate linting and formatting with tools like Husky. But hey, I like to do it manually. 🙌

![Code review gone wrong | code-memes, IT-memes | ProgrammerHumor.io](https://programmerhumor.io/wp-content/uploads/2022/03/programmerhumor-io-programming-memes-7a316042d9b4b58-608x421.jpg align="center")

**Comments and Documentation: 📝**

Comments should be the spice, not the main course. Use them sparingly and only when they truly add value. Nothing's worse than scrolling through endless comments in a massive code file. Instead, let your code do the talking with well-named functions and variables. 🤐

**Don't Repeat Yourself (DRY) and Single Responsibility Principle (SRP): 🚀**

Avoid code duplication like the plague. Break your code into functions and modules, each with a single, well-defined role. It's like creating a perfectly organized kitchen. 🍳

**Code Reviews:** 👩‍💻👨‍💻

Engaging in code review sessions with your peers and seniors can be an enlightening experience. You get to tap into their wealth of knowledge, and your code gets a chance to shine brighter. But hold on, not all seniors are coding wizards 🧙‍♂️, so choose your reviewer wisely.

**More Goodies: 📌**

* **Version Control:** Think of it as your code's time machine. It helps you track changes and collaborate seamlessly.
    
* **Error Handling:** Every chef knows how to handle unexpected situations. Apply the same care to error handling in your code.
    
* **File Size:** Keep your code files bite-sized. In TypeScript, those import statements can get pretty verbose!
    
* **Design Patterns:** These are like secret recipes for scalable code. Use them wisely. 🍰
    

Remember, clean code is a journey, not a destination. It demands continuous attention and discipline. If you're hungry for more insights into clean code, check out Uncle Bob's book, "Clean Code," or his YouTube videos. By embracing these principles and making the most of JavaScript's toolkit, you'll cook up a codebase that's a delight to understand, modify, and collaborate on. Happy coding! 🚀💻😊