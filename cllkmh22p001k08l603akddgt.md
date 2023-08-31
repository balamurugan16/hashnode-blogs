---
title: "Developer Tools Tricks"
datePublished: Mon Aug 21 2023 08:35:45 GMT+0000 (Coordinated Universal Time)
cuid: cllkmh22p001k08l603akddgt
slug: developer-tools-tricks
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/k86_YnmIpW0/upload/57c0b036eb0dfe62f93179cb3679299a.jpeg
tags: javascript, web-development, programming-tips

---

As a web developer, I feel it is a must to learn how Developer tools work. I am not suggesting taking a new 20-hour course on it but knowing a few tricks will make your lives much better. This blog would be a starting point for you to know a few of them, As you progress in your career, you will learn more tricks.

I am using Google Chrome here, mostly of the tips and tricks will be the same for all the Chromium-based browsers except Firefox which has a different setup. I will make a separate blog on tips specific to the Firefox browser because it has some good features that Chrome is not offering currently.

To open up your developer tools, press `Ctrl + shift + c` or right-click and select Inspect.

### 1\. The `$` operator

If you have used the JQuery library, you should be familiar with the O.G, `$` operator. It helps to select HTML elements and even does AJAX requests. Similarly in Chrome, in the console tab, the `$` operator can be used to select the HTML elements

[![dollar operator](https://res.cloudinary.com/practicaldev/image/fetch/s--vF2_qz----/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1iss1at7lud8nix9abx6.png align="center")](https://res.cloudinary.com/practicaldev/image/fetch/s--vF2_qz----/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1iss1at7lud8nix9abx6.png)

This is not even the killer feature, there is another use case. If you come across an element from the HTML tree in the Elements tab and want to select that element in the console, you just click on the element and type `$0` on the console, It just selects and returns the DOM element. That value can be assigned to a variable as well 🤯. You can see the dev tools pointing out `== $0` near the HTML element.

[![dom tree](https://res.cloudinary.com/practicaldev/image/fetch/s--QObXcERy--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/7cb1hbrhuug3sndhf202.png align="center")](https://res.cloudinary.com/practicaldev/image/fetch/s--QObXcERy--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/7cb1hbrhuug3sndhf202.png)

  
`$0` will return the last selected element, `$1` will return the element selected before the recent one and the list goes on😮.

### 2\. Offline mode

If you want to test out your application in offline mode, (I used to do it if I want to check how my app works if the network request fails) In the network tab there is an option for that.

[![offline mode](https://res.cloudinary.com/practicaldev/image/fetch/s--_4Tx-0ma--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/uih1n0lbibwgzioq6b9w.png align="center")](https://res.cloudinary.com/practicaldev/image/fetch/s--_4Tx-0ma--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/uih1n0lbibwgzioq6b9w.png)

There are options to give presets like Fast 3G and Slow 3G and you can even give custom presets to check how your application works in different network throttling but I am not going into that because I don’t know how to do that 🤭.

### 3\. Inbuilt IDE (Sources tab)

The Sources tab is an inbuilt IDE in itself. It has multiple features like a debugger with a call stack, scope viewer, etc., VS Code features like `Ctrl + p` to open a file, `Ctrl + shift + p` to run a command, and as a code editor as well(with some caveats).

[![sources tab](https://res.cloudinary.com/practicaldev/image/fetch/s--VSEHUXHl--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/fee4be8hjwb4wo4y630e.png align="center")](https://res.cloudinary.com/practicaldev/image/fetch/s--VSEHUXHl--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/fee4be8hjwb4wo4y630e.png)

In the sidebar, the page tab will show the content that is being served to the browser. Here I am using a React with Typescript and Vite app so all the files will be available here with the `App.tsx` file opened. Here, I can add breakpoints and If I refresh, the debugging process starts. This works similarly to the VS Code debugger tool if you have worked with it.

[![debugger](https://res.cloudinary.com/practicaldev/image/fetch/s--TlVBaLfw--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/diq1u3p986934x6md7op.png align="center")](https://res.cloudinary.com/practicaldev/image/fetch/s--TlVBaLfw--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/diq1u3p986934x6md7op.png)

The snippets feature will be very handy as it is a sandbox where you can have small JS code snippets. If I have to test out a small piece of code, I do it in the snippets tab only because it has access to the debugger as well which will be handy 😍.

### 4\. Elements tab (HTML)

The elements tab in itself can have a separate blog because it is that feature-rich. Any front-end developer without using this tab cannot produce a very good UI (Change my mind!). The elements tab has great tooling over both HTML and CSS.

Say you want to hide an element from the DOM to see how to layout looks without removing the element from the DOM (moreover like 0 opacity) This feature can be used.

[![bofore](https://res.cloudinary.com/practicaldev/image/fetch/s--6nxoDcQv--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/lzqns76keqa1agg39hh3.png align="center")](https://res.cloudinary.com/practicaldev/image/fetch/s--6nxoDcQv--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/lzqns76keqa1agg39hh3.png)

[![hide element option](https://res.cloudinary.com/practicaldev/image/fetch/s--Gkug-8CM--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/gh3tyyjtev5em7y2aheh.png align="center")](https://res.cloudinary.com/practicaldev/image/fetch/s--Gkug-8CM--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/gh3tyyjtev5em7y2aheh.png)

[![after](https://res.cloudinary.com/practicaldev/image/fetch/s--POMvsFe9--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ud5klr51evx9xat5ubtk.png align="center")](https://res.cloudinary.com/practicaldev/image/fetch/s--POMvsFe9--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ud5klr51evx9xat5ubtk.png)

If you see here, the `h1` element is hidden yet the DOM space is still occupied. Similarly, there are a lot of features when you see the menu by right-clicking an element. The Delete element will remove the element from the DOM. The duplicate element is self-explanatory.

Two more features, the Expand recursively feature will expand all the elements that are children to the selected element, and the Scroll to view feature (I use this feature a lot) will take the viewport to that element. This will be extremely useful if your web page has scrollable content (Extremely helpful in an infinite scrolling page)

The properties tab on the right side of the elements tab will give all the information about the DOM element.

[![properties](https://res.cloudinary.com/practicaldev/image/fetch/s--I19WJakr--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/sxixh1wc6abpup41wn97.png align="center")](https://res.cloudinary.com/practicaldev/image/fetch/s--I19WJakr--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/sxixh1wc6abpup41wn97.png)

### 5\. Force State

One more feature that the elements tab offer which I can’t live without is the Force state feature. In HTML, there are states like active, focus, hover, etc, These states will trigger upon user event. If you are applying styles for an element let's say in a hover state, hovering over the element and working will be tedious, here comes the Force state feature.

[![force state](https://res.cloudinary.com/practicaldev/image/fetch/s--V-AB82r8--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/yf6rfcy4347q37uel6pe.png align="center")](https://res.cloudinary.com/practicaldev/image/fetch/s--V-AB82r8--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/yf6rfcy4347q37uel6pe.png)

Once you select any state (`hover` in this case), a breakpoint will appear in the Elements tab on that particular element and that particular element will be forced in that state. Now the styles can be applied. (Try out the styles in the Elements tab itself to see the results instantly). Here I have forced the hover state on a button.

[![result](https://res.cloudinary.com/practicaldev/image/fetch/s--C57GfRqu--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1j4p5qdi9q0hgwp4sk87.png align="center")](https://res.cloudinary.com/practicaldev/image/fetch/s--C57GfRqu--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1j4p5qdi9q0hgwp4sk87.png)

### 6\. Elements tab (CSS)

The CSS tooling provided by the dev tools is very powerful, CSS was never easy for me but with the right tooling, I was able to survive and even produce good styles.  
Most of the CSS properties like color, box-shadow, and transition timing functions are provided with a small utility to pick the values. For example, there is a color picker tool to pick colors, In chrome, there are color suggestions available. For the transition timing function, a cubic bezier curve is provided with which the transition value can be precisely given.

[![color and cubic bezier picker](https://res.cloudinary.com/practicaldev/image/fetch/s--7wlt0mGO--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/adwyz77yl1m1f2gx2hov.png align="center")](https://res.cloudinary.com/practicaldev/image/fetch/s--7wlt0mGO--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/adwyz77yl1m1f2gx2hov.png)

There are more features given by the elements tab itself like,

* The Computed tab inside the Elements tab will give all the final computed styles of the selected element. This will be useful as CSS styles are cascaded in nature.
    
* Shift + click on the color values cycles between color formats (hex, HSL, RGB)
    
* The Layouts tab gives the grid and flexbox layout which is a very useful feature. (This feature is very good in Firefox)
    

That’s it for this blog post folks, I don’t want to dump a lot of information in one blog post itself, will definitely make a follow-up post with more tips and tricks in the future. Thanks!