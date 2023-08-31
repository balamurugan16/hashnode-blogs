---
title: "Structural vs Nominal typing🌟"
datePublished: Sat Jul 22 2023 17:42:41 GMT+0000 (Coordinated Universal Time)
cuid: clkeasuev000009mkb9di6s60
slug: structural-vs-nominal-typing
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/DuHKoV44prg/upload/dc9d39b6f8b51c35b2c72d360b362cd9.jpeg
tags: typescript, programming-ciovqvfcb008mb253jrczo9ye

---

## Introduction 📝

As technology advances, our preferences for programming languages are evolving too. Nowadays, more people are favoring statically typed languages like TypeScript, Go, and Rust over dynamically typed ones like Python, Ruby, and JavaScript. While there's no need to dislike dynamic languages (they have their strengths!), I find statically typed languages my top choice, even if they can be a bit tricky to work with sometimes. 💻💪

## Understanding Structural Typing 🛠️

Structural typing is well illustrated in TypeScript. Let's see an example:

```ts
type Car = {
  name: string;
}

type Bike = {
  name: string;
}

const myCar: Car = {
  name: "Fortuner"
}

const myBike: Bike = myCar;
```

In this TypeScript example, there are no errors when we assign a variable of type `Car` to a variable of type `Bike`. Why? Because both types have the same structure, even though they have different names for their definitions. They both have a property called `name` with a type of string. This flexibility is a key feature of structural typing, which applies to classes and interfaces in TypeScript too. 🏗️🧱

## Exploring Nominal Typing 🏭

Java represents nominal typing. Let's see how it works:

```java
class Car {
    String name;
}

class Bike {
    String name;
}

public class Program
{
    public static void main(String[] args) {
        Car car = new Car();
        car.name = "Fortuner";
        
        Bike bike = car; // This line will raise a type error in Java
    }
}
```

In this Java example, you'll encounter an "incompatible types" error when trying to assign a variable of type `Car` to a variable of type `Bike`. Java strictly enforces nominal typing, so even if the types have the same structure, they must explicitly be of the same named type. 🛠️🚧

## Pros and Cons of Each Approach 🤝✅❌

Structural typing offers incredible flexibility, following the famous "Duck typing" principle: "If it walks like a duck and it quacks like a duck, then it must be a duck!" It also maintains a good level of security similar to nominal typing.

On the other hand, nominal typing, seen in languages like C++ and Java, has its own set of use cases. However, it often involves writing more boilerplate code to handle the relationships between various types.

## Conclusion: 🎯

Understanding the differences between static and dynamic typing, along with the nuances of structural and nominal typing, can give you an advantage in your programming journey. Making informed decisions when choosing the right language for specific projects becomes easier. Happy coding! 🚀👩‍💻

> That's a wrap! Creating content like this for my blogs allows me to share these insightful details with you all. 📚🔍 If you found this helpful, stay tuned for more tech-focused content in the future! Feel free to share your thoughts and experiences in the comments below. 🗣️😊