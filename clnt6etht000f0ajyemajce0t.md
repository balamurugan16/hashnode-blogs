---
title: "Styling React Components"
datePublished: Mon Oct 16 2023 17:35:27 GMT+0000 (Coordinated Universal Time)
cuid: clnt6etht000f0ajyemajce0t
slug: styling-react-components
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1697477695661/3ad5beb2-b7de-48f7-aa09-4d402ff624e3.png
tags: css, javascript, reactjs

---

Personally, for me, I don’t like to style. I mean, I don’t hate CSS and styling but I hate when I give styling a try and It looks bad.

Anyway, I don’t have to emphasize the importance of styling, If your users need to stay in your app, then the app should look good. Unlike the dating culture, in web development **“Looks do matter!”** (Just Kidding, Looks matter in dating as well! 😂).

In this article, I will share 5 different ways to style react components so that you can choose the approach that suits you when you develop your application.

But first of all, why should you know all the different ways to style, you may ask! Isn’t knowing one approach enough? Yeah but No. First of all, it is easy to take consistency for granted. Because in a large codebase, developers should be aware of the styling approaches, and should not go with the approach that they are familiar with. So knowing the other approaches exist will keep you ready to tackle any situation.

## 1\. The `style` attribute

In react, you either write the inline styles using the `style` attribute.

```xml
<div 
  style={{
    display: "flex", 
    justifyContent: "center", 
    alignItems: "center" 
  }}>
  <h1>Hi Mom!</h1>
</div>
```

As you can see, this approach has a few problems, if the CSS properties count increases, then the component will be bloated with a bunch of CSS. Reusability is not an option and for inline CSS the specificity is also high so If you already have some styles, the inline styles will most probably take precedence!

## 2\. CSS or Sass

You can also have your styles in a separate stylesheet and import that into the component. This provides the benefits of using either the CSS or Sass’s features like nesting, variables, mixins and so on. I like this approach and I will never be against this one, the only thing is there are more modern approaches that solve the problem better. But if you prefer this approach then you can very well go with this.

## 3\. CSS in JS

Initially, I didn’t like this approach but when I started to use this, this was a game changer. Essentially there are libraries like styled-components that let us write styles in a normal CSS way and also give additional features like nesting, conditional styling and so on, and produce a react wrapper component out of the styles that we define. This approach is really useful because you can organize your styled react components better. Look at the following example.

```javascript
export const App = () => {
  return (
    <Wrapper>
      <h1>Hi Mom!</h1>
    </Wrapper>
  );
};

const Wrapper = styled.div`
  display: flex;
  justify-content: center;
  align-items: center
`
```

So here, notice the way I have written the CSS. Yes the API that this library gives is a bit weird but you will get used to it in no time. This is a better way to write CSS directly in a JavaScript file. If you are using VS Code, install the styled-components extension, this gives better syntax highlighting and auto-complete support which will be handy!

## 4\. Tailwind CSS

Tailwind is by far the best and most modern approach for styling. Tailwind’s approach is to provide utility classes for your known CSS properties like `flex` means `display:flex` and so on. This will let you quickly style your components and not worry about naming the class or id to style your components. Sometimes your class names can become a nightmare but there are ways to come around that as well. Tailwind provides customization as well with the `tailwind.config.js` file where essentially you can configure your typography, colors and so on. Look at the following example.

```javascript
export const App = () => {
  return (
    <div className="flex justify-center items-center">
      <h1>Hi Mom!</h1>
    </div>
  );
};
```

As you can see, it is intuitive and easy. Developers can quickly style the components. If you are using VS Code install the tailwind extension for auto-complete support. It will be very useful.

## 5\. Component Library

The final approach is going with a component library. Component libraries come with pre-styled components reducing our work. There are several libraries out there like MUI, Daisy UI, Chakra UI and so on. Usually, component libraries come with a built-in opinionated way of styling, for example, MUI comes with styled-components for styling and Daisy UI is built on top of Tailwind CSS. This way, you get pre-styled components and a way to add styles on top of them.

To conclude, now you know 5 different ways to style react components. Next time you can pitch the approach to your seniors which will give you a good impression with your colleagues. Trust me, you can pick up girls if you know CSS! (Just kidding, programming nerds can never get girls by exposing that they are programmers!)