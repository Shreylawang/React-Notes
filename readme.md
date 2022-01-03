# Introduction to React 

## What is React?


- React is a **JavaScript library** for building fast and interactive 
  UI and **Single Page Application (SPA)**.
- Developed by **Facebook** in `29 May 2013`.
- React is the view part of **MVC application**.
- **Declarative View** :- React will efficiently update and render just
  the components we need to change and update data to, the entire page
  won't reload.
- **Component Based** :- Build encapsulated components that manage their 
  own state, then compose them to make complex UIs


## Why React? 

- Why to use React, Why to not simply be dependant upon DOM?
- The reason is **React Virtual Dom!**
- When we are using DOM, we are using using Real DOM which is inbuilt 
  in virtual DOM.
- The disadvantges of using DOM is that
    - High Memory consumption
    - Updates Slow
    - Expensive
- The Advantages of using Virtual DOM 
    - Updates Faster
    - No memory wastage  
    - Memory efficient


#  Virtual DOM
- React uses **Virtual DOM**, **Virtual DOM -> lightweight copy of the actual DOM**(a virtual representation of the DOM).
- So for **Every Object** that exists in the **Original DOM**, **There is an Object for that in React Virtual DOM**.
- It is exactly the same, but it does not have the power to directly **change the layout of the document.**
- Manipulating DOM -> 🐌**Slow**, but manipulating Virtual DOM -> 🐎**Fast**.
- Updating the virtual DOM -> Comparatively Faster than updating the Actual DOM 🏄‍♀️.     
- So each time there is a change in the state of our application, virtual DOM gets updated first instead of the real DOM. 


## How Virtual DOM actually make the things faster

- When anything New -> **Added** to the application, a **Virtual DOM is created** and it is represented as a **Tree** 🌲.
- Each element in the application is a **Node** ⭕ in this Tree 🌲.
- So, whenever there is a **change in State** of any element, a **New Virtual DOM Tree** is **created**.
- This **New Virtual DOM Tree 🌲** is then **compared** with the **Previous Virtual DOM Tree 🌲** and make a note of the changes.
-  After this, it finds the best possible ways to make these changes to the Real DOM.
- Now only the **Updated Elements will get Rendered on the Page Again.**


## How Virtual DOM helps React

- In react, **Everything is Treated as a Component** be it a functional component or class component.
- **A Component can contain some State**.
- Each time we change something in our JSX file or let’s put it in simple terms, whenever **The State of any Component is changed React updates it’s Virtual DOM Tree 🌲.**
- Though it may sound that it is ineffective but the cost is not much significant as **Updating the Virtual DOM doesn’t take much time.**
- **React maintains Two Virtual DOM at each time**, one contains the **Updated Virtual DOM** and one which is just the **Pre-Update version** of this Updated Virtual DOM.
- Now it **Compares the Pre-Update version with the Updated Virtual DOM** and figures out what exactly has **Changed in the DOM like which Components have been Changed.**
- **Diffing** -> This process of **Comparing the current Virtual DOM Tree 🌲 with the Previous one** is known as **‘Diffing’**.
- Once React finds out what exactly has changed then it updated those objects only, on real DOM.
- **Batch Updates** -> React uses something called as **Batch Updates** to update the real DOM, It just mean that the **Changes to the real DOM are sent in batches instead of sending any update for a single change in the state of a component.** 
- We have seen that the **re-rendering of the UI is the most expensive part** and React manages to **do this most efficiently by ensuring that the Real DOM receives batch updates to re-render the UI.**
- **Reconciliation** ->  This entire **Process of Transforming Changes from the Virtual DOM to the Real DOM** is called **Reconciliation**, This significantly improves the performance and is the main reason why React and it’s Virtual DOM is much **Loved by Developers** all around.


# What is a Library?

- There are a billion webpages, and many of them are interactive in some way - in fact, many of them are interactive in the same ways. How many websites have you seen that use a slideshow? I've seen hundreds, myself!
- Now, it's possible that every one of those web developers wrote their own JavaScript code to make a slideshow, but a lot of them probably re-used the same code. As programmers, we should re-use existing code when we can, so that we don't waste our time writing code that another programmer has already written.
- In JavaScript, the way we do that is by **Using a library. A library is a JavaScript file that contains a bunch of functions, and those functions accomplish some useful task for your webpage**.
- A JavaScript library is a **Library of Pre-written JavaScript Code** that allows for easier development of JavaScript-based applications, especially for **AJAX** and other web-centric technologies.


## Origin of Library


- With the **Expanded demands for JavaScript**, an **Easier means for Programmers to develop such dynamic interfaces was needed**. 
- Thus, **JavaScript libraries and JavaScript widget libraries were developed**, allowing for developers to **concentrate more upon more distinctive applications of Ajax**.
- This has led to other companies and groups, such as **Microsoft and Yahoo! developing their own JavaScript-based user interface libraries**, which find their way into the web applications developed by these companies.
- Some JavaScript libraries allow for **easier integration of JavaScript with other web development technologies, such as CSS, PHP, Ruby, and Java**.
- Almost all JavaScript libraries are released under either a copycenter or copyleft license to ensure license-free distribution, usage, and modification.


# Understanding Modules and Named Export

- A module in JavaScript is just a file containing related code.
- In JavaScript, we use the **Import and Export keywords to share and receive functionalities respectively across different modules**.
- The **Export keyword is used to make a variable, function, class or object  accessible to other modules**. In other words, it becomes a **Public Code**.
- The **Import keyword is used to bring in public code from another module**.

## Named Export

**Syntax**
- By declaring module we can activate import/export feature in javascript
```javascript
<script type="module" src="index.js"></script>
```
- To export module :-
```javascript
function xyz(){
  return;
}
export {xyz}
```
- To import module :-
```javascript
import {xyz} from './main'
function abc(){
  return xyz();
}
```
**Example**
- Exporting Module
```javascript
function DisplayName(name) {
  console.log(name);
}
export {DisplayName}
```
- Importing Module
```javascript
import { DisplayName } from './main';
function NameIs() {
	return DisplayName("shrey");
}
```

