---
title: "Higher order components in React"
datePublished: Thu Oct 05 2023 18:09:30 GMT+0000 (Coordinated Universal Time)
cuid: clndhs8gu000008l95f2tboqj
slug: higher-order-components-in-react
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1696875162369/a5ffb7d3-69b0-4365-a6be-712b417f5e97.png
tags: javascript, reactjs, typescript

---

Any developer trying to attend a React interview will come across the question “What are HOCs?” from their interviewer, and this question will give the notion to the interviewer whether you are a good front-end engineer specializing in React. Following my previous article on Higher-order functions, we will look at Higher-order Component patterns in React with some examples.

Let’s say you have some reusable logic that you want to use across all your components, there are several patterns to achieve that and one such pattern is the HOC pattern. Look at the following example,

```jsx
function withCenterStyling(Element) {
	return (props) => {
		const styles = {
			display: "flex",
			alignItems: "center",
			justifyContent: "center"
		}
		return <Element {...props} styles={styles} />;
	}
}
```

Here, the `withCenterStyling` is a HOC, what it does is that it takes another React Functional component and returns a new overridden functional component.

<div data-node-type="callout">
<div data-node-type="callout-emoji">💡</div>
<div data-node-type="callout-text">A functional component is nothing but a function that returns some HTML which is referred to as JSX.</div>
</div>

So the `withCenterStyling` component can be reused for any component that requires a center alignment, which promotes code reusability. This is Higher order Components, Simple!

But that example is very basic, let’s take another example.

```jsx
// imagine there is a loading spinner component existing
import Loading from "./Loading.tsx";

function withLoader({ Element, url }) {
	return (props) => {
		const [data, setData] = useState(null);
	
		async function loadData() {
			const jsonData = await fetch(url);
			const response = await jsonData.json();
			setData(response);
		}
	
		useEffect(() => {
			loadData();
		}, [])
	
		if (!data) return <Loading />;
		
		return <Element {...props} data={data} />;
	}
}
```

Uff! That is a lot of code but let’s break it down. As you know by now, a HOC will take in a react component and return another react component. So here, the `withLoader` will take in a component and a URL. So the idea here is that the data will be fetched from the provided URL and the fetched data will be passed to the component. During the fetching time, a small loading spinner should be displayed. This will be very useful because showing Loading progress while fetching data is such a common activity.

So here the higher-order component is doing the data fetching and conditionally shows the loading spinner if the data is not yet received! See, It’s that simple.

So this is HOC in React. It will be really useful when the React Component Architecture is well maintained. HOCs can also be incrementally added to an existing codebase so If you want to impress your team lead or colleagues, explain this concept, take up the refactoring task, implement HOCs and break the UI in the production! All the best!!!!!