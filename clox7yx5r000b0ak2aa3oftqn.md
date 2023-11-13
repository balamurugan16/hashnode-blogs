---
title: "Demystifying JSX 🚀"
seoTitle: "Demystifying JSX"
seoDescription: "A blog explaining how JSX works with React"
datePublished: Mon Nov 13 2023 18:09:52 GMT+0000 (Coordinated Universal Time)
cuid: clox7yx5r000b0ak2aa3oftqn
slug: demystifying-jsx
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1699898839735/a540906a-9899-4088-90fd-dcd932a5fce2.png
tags: javascript, reactjs, jsx

---

React is popular because of its declarative approach to building UI components. This has led to a rise in the library's popularity, making it the de-facto standard for modern web development. The declarative approach comes from various factors like functional components and JSX. Don't get confused—JSX and React are two separate things but are used together. Some other frameworks like Vue.js and Preact also use JSX. In this blog post, we will learn more about JSX and how it makes our lives easier while coding in React.

approach doesn’t scale well, and it is too verbose. Just imagine how an already complex application will look if written in the previous approach. This is what JSX brings to the table. With that example, we have reached the end of this blog post. This blog is a part of my React series, and if you like this series, let me know by leaving a like and comment. Until next time! ￼

JSX is an XML-like syntax that is often used to express UI components. It was developed by Facebook. You can learn more about JSX [here](https://facebook.github.io/jsx/). JSX looks similar to HTML but is different in many ways concerning the syntax and features like:

1. A JSX element should have only a single root element. This should be obvious if you are using the fragment in React (`<></>`).
    
2. It requires tags to be closed explicitly. For example, in JSX, the image tag should be autoclosed (`<img />`).
    
3. Most of the HTML attributes are in camel casing. For example, `onClick`, `onChange`, etc.
    
4. JSX allows the injection of JavaScript using curly braces. This allows the full power of JavaScript to create a dynamic UI.
    

Now let's try to create a simple React component without using JSX and JSX and compare to see the benefits and simplicity that JSX is bringing.

Let’s start by creating an `h1` tag containing “Hi Mom!”

```typescript
import React from "react"

export default function Component() {
  return (
    React.createElement('h1', {id: "heading"}, "Hi Mom!")
  );
}
```

Okay, so here you can see some new weirdness going on. Let me demystify it.

React exports a function `createElement` that lets us create any HTML element. It takes in three parameters:

1. The first parameter takes in the name of the HTML element, in our case, the `h1` element.
    
2. The second parameter will take in all the valid HTML attributes like `id`, `className`, `onClick`, etc. In our case, the `id` attribute.
    
3. The third parameter will take in the children for the current element. In our case, just the text **“Hi Mom!”**.
    

Now React will take all these and convert them into HTML behind the scenes. Let’s go the extra mile by wrapping the `h1` element in an `header` element.

```typescript
import React from "react"

export default function Component() {
  return (
    React.createElement(
      'header',
      {},
      React.createElement(
        "h1",
        {id: "heading"},
        "Hi Mom!"
      )
    )
  );
}
```

Here you can see the use of the third parameter. We have wrapped the previously created element into a new `header` element. This is how React elements can be created without using JSX 🤯.

Now let’s use JSX and recreate the UI that we have written so far.

```typescript
export default function Component() {
  return (
    <header>
      <h1 id="heading">Hi Mom!</h1>
    </header>
  );
}
```

The syntax with JSX is far more readable and familiar as well. The previous approach doesn’t scale well, and it is too verbose. Just imagine how an already complex application will look if written in the previous approach. This is what JSX brings to the table.

With that example, we have reached the end of this blog post. This blog is a part of my React series, and if you like this series, let me know by leaving a like and comment. Until next time! 👋