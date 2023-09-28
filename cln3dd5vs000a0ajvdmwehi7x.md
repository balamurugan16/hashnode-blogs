---
title: "Observer Pattern"
datePublished: Thu Sep 28 2023 16:08:07 GMT+0000 (Coordinated Universal Time)
cuid: cln3dd5vs000a0ajvdmwehi7x
slug: observer-pattern
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/LPZy4da9aRo/upload/6feed44522943f432496949e6d26cdb9.jpeg
tags: design-patterns, javascript, typescript, programming-ciovqvfcb008mb253jrczo9ye, observer-pattern

---

Hello developers, With this blog I am starting a series on the basic and essential design patterns that every developer should know. Design patterns in simple terms are pre-made solutions to an existing problem that a developer may face! (P.S. Don’t judge me, that is the easiest explanation that I can give!)

### What problem does the Observer pattern solve?

Hashnode or any newsletter-based services are a perfect example. Let’s say you subscribe to my Hashnode newsletter, You will receive a notification whenever I upload a blog. If you feel that you no longer need to get notifications from my newsletter you can unsubscribe as well. So this is exactly the problem that the Observer pattern is solving. Let’s continue with this newsletter example itself in this blog.

### A detailed example of the Observer pattern

The Observer pattern is also known as the Publisher / Subscriber (Pub/Sub) pattern where Hashnode (on behalf of the blogger) is the Publisher and you, subscribing to the newsletter, the subscriber.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695916827576/280b82f1-f6a6-4d12-8a8f-26b0947c1467.png align="center")

Here, The publisher keeps track of the subscribers, If anyone wants to subscribe, they can subscribe themselves via the publisher and the same goes with unsubscribing someone. And, as long as the users are subscribed to the newsletter, they will receive the notification else they won’t. It is that simple!

### Let’s look at some code!

I am explaining it in TypeScript but design patterns are not specific to a programming language.

First, let’s define the `Publisher` and `Subscriber` interfaces

```typescript
interface Subscriber {
  update(message: string): void; // gets updated or notified
}

interface Publisher {
    subscribe(subscriber: Subscriber): void; // subscribes the user
    unsubscribe(subscriber: Subscriber): void; // unsubscribes the user
    notify(blogName: string): void; // sends notification to users
}
```

The code is pretty straightforward. Now let’s create Hashnode and the User classes

```typescript
class Hashnode implements Publisher {
  private observers: Subscriber[] = []; // tracks the subscribers

  subscribe(observer: Subscriber) {
    this.observers.push(observer); // adds user into the subscriber array
  }

  unsubscribe(observer: Subscriber) {
    const index = this.observers.indexOf(observer);
    if (index !== -1) {
      this.observers.splice(index, 1); // removes the user
    }
  }

  notify(blogName: string) {
    for (const observer of this.observers) {
      observer.update(blogName); // updates the subscriber
    }
  }
}

class User implements Subscriber {
  private name: string;

  constructor(name: string) {
    this.name = name;
  }

  update(message: string) {
    // just a simple console log for this example
    console.log(`${this.name} received message: ${message}`);
  }
}
```

Now let’s try out our design pattern! First, let’s create our publisher and subscribers

```typescript
const hashnode = new Hashnode();

const priya = new User('Priya');
const karan = new User('Karan');
const mani = new User('Mani');
const komal = new User('Komal');
const aishwarya = new User('Aishwarya');
```

Now let’s subscribe all the users to `hashnode`.

```typescript
hashnode.subscribe(priya);
hashnode.subscribe(karan);
hashnode.subscribe(mani);
hashnode.subscribe(komal);
hashnode.subscribe(aishwarya);
```

Let’s publish our first blog

```typescript
hashnode.notify('New blog on clean code');
```

Now If we execute, this will be the result. You can see that all 5 users got notified!

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695917093498/a2e6d90e-8dfd-43b9-a4e4-b9daf0ea7438.png align="center")

Now one user, Karan decides to unsubscribe from the newsletter.

```typescript
hashnode.unsubscribe(karan);
```

And another blog is getting published.

```typescript
hashnode.notify('New blog on Observer pattern');
```

Now If we execute the code the output will be like this.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1695917120091/a9cdb426-b99a-4e84-ae4c-b58a9edac088.png align="center")

As you can see, Karan didn’t get notified because he unsubscribed from the newsletter.

### Conclusion

That’s it, This is the observer pattern and it is used in a lot of places. There are real services out there like RabbitMQ, Google Cloud’s Pub/Sub which provides services that are tailored for this use case. So knowing about how these models work will be beneficial as a developer. Stay tuned for the next blog!