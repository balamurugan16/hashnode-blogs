---
title: "React with Typescript, Tips and Tricks that you should know!"
datePublished: Mon Oct 30 2023 18:15:13 GMT+0000 (Coordinated Universal Time)
cuid: clod7zvcl000b09l4g2w75r45
slug: react-with-typescript-tips-and-tricks-that-you-should-know
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1698689648731/e07fb676-a1cb-4248-ad24-3890e80cb792.png
tags: reactjs, typescript

---

React is a popular JavaScript library for building user interfaces, and TypeScript is a statically typed superset of JavaScript. Together, they make for a powerful combination, allowing developers to write safer and more maintainable code. In this guide, we'll explore various aspects of using TypeScript with React, from typing props to taking advantage of TypeScript's advanced features for a more productive development experience. Additionally, we will refer to the [React TypeScript cheat sheet](https://react-typescript-cheatsheet.netlify.app/) to help you deepen your understanding.

## Typing Props

One of the fundamental aspects of React development with TypeScript is typing the props passed to your components. You can define prop types directly within the parameters, enhancing code readability and maintainability:

```typescript
type Props = {
    prop1: string;
    prop2: string;
}
const MyComponent = ({ prop1, prop2 }: Props) => {
  return <div>{prop1} - {prop2}</div>;
};
```

This ensures that `MyComponent` receives the expected props and provides type safety during development.

## Generic Types for Hooks and Functions

You can use TypeScript's generic types to provide type information to React hooks and functions like `useState`, `useRef`, `useMemo`, and more. For example:

```typescript
const [count, setCount] = useState<number>(0);
const myRef = useRef<HTMLDivElement | null>(null);
const memoizedValue = useMemo<number>(() => computeExpensiveValue(), [deps]);
```

These generic types help prevent type-related bugs and make your code more self-explanatory.

## Typing onClick Functions

When defining onClick event handlers that are used in JSX elements, it's a good practice to specify their types, especially if they are defined separately. For example:

```typescript
type MouseEventHandler = (event: React.MouseEvent<HTMLButtonElement>) => void;

const handleButtonClick: MouseEventHandler = (event) => {
  // Handle button click event
};
```

Typing the `handleButtonClick` function ensures that it correctly handles the `onClick` event.

## VS Code Tooltip for React Components

Visual Studio Code provides excellent TypeScript support, and you can take advantage of it to get tooltips and autocompletions for React components. By hovering over an HTML element or its attribute, you can infer the return type or the type of the element/attribute. This feature makes it easier to understand how to use it correctly and define types for your components.

## PropsWithChildren

React components often receive children as props. The `PropsWithChildren` utility type is helpful for this scenario. It allows you to specify that a component accepts children and other props:

```typescript
import { PropsWithChildren } from 'react';

type Props = {
    title: string;
} & PropsWithChildren;

const Card = ({ title, children }: Props) => {
  return (
    <div className="card">
      <h2>{title}</h2>
      <div className="content">{children}</div>
    </div>
  );
};
```

## ComponentPropsWithoutRef and ComponentPropsWithRef

The `ComponentPropsWithoutRef` and `ComponentPropsWithRef` utility types are helpful when you're working with component props. They help in maintaining a clear separation between props and ref types:

* `ComponentPropsWithoutRef` allows you to specify component props without including the `ref` prop.
    
* `ComponentPropsWithRef` includes the `ref` prop.
    

For example:

```typescript
import { ComponentPropsWithoutRef } from 'react';

type InputProps = ComponentPropsWithoutRef<'input'>;

const MyInput = (props: InputProps) => {
  return <input {...props} />;
};
```

By using these utility types, you can ensure that your components handle props and refs appropriately.

## Conclusion

Using React with TypeScript provides a strong foundation for building robust and maintainable applications. Typing props, using generic types for hooks, and understanding advanced TypeScript utility types like `PropsWithChildren`, `ComponentPropsWithoutRef`, and `ComponentPropsWithRef` are key steps in mastering this powerful combination. Make sure to refer to the [React TypeScript cheat sheet](https://react-typescript-cheatsheet.netlify.app/) for additional tips and best practices to enhance your React TypeScript development skills. Happy coding!