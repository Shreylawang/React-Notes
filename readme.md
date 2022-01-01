# Introduction to React

## What is React?


- React is a JavaScript library for building fast and interactive 
  UI and Single Page Application (SPA).
- Developed by Facebook in 2011.
- React is the view part of MVC application.
- Declarative View :- React will efficiently update and render just
  the components we need to change and update data to, the entire page
  won't reload.
- Component Based :- Build encapsulated components that manage their 
  own state, then compose them to make complex UIs


## Why React? 

- Why to use React, Why to not simply be dependant upon DOM?
- The reason is React Virtual Dom!
- When we are using DOM, we are using using real DOM which is inbuilt 
  in virtual DOM.
- The disadvantges of using DOM is that
    - High Memory consumption
    - Updates Slow
    - Expensive
- The Advantages of using Virtual DOM 
    - Updates Faster
    - No memory wastage  
    - Memory efficient


# Virtual DOM
- React uses Virtual DOM exists which is like a lightweight copy of the actual DOM (a virtual representation of the DOM).
- So for every object that exists in the original DOM, there is an object for that in React Virtual DOM.
- It is exactly the same, but it does not have the power to directly change the layout of the document.
- Manipulating DOM is slow, but manipulating Virtual DOM is fast as nothing gets drawn on the screen.
- Updating the virtual DOM is comparatively faster than updating the actual DOM.     
- So each time there is a change in the state of our application, virtual DOM gets updated first instead of the real DOM. 


## How Virtual DOM actually make the things faster

- When anything new is added to the application, a virtual DOM is created and it is represented as a tree.
- Each element in the application is a node in this tree.
- So, whenever there is a change in state of any element, a new Virtual DOM tree is created.
- This new Virtual DOM tree is then compared with the previous Virtual DOM tree and make a note of the changes.
-  After this, it finds the best possible ways to make these changes to the real DOM.
- Now only the updated elements will get rendered on the page again


## How Virtual DOM helps React

- In react, everything is treated as a component be it a functional component or class component.
- A component can contain a state.
- Each time we change something in our JSX file or let’s put it in simple terms, whenever the state of any component is changed react updates it’s Virtual DOM tree.
-  Though it may sound that it is ineffective but the cost is not much significant as updating the virtual DOM doesn’t take much time.
- React maintains two Virtual DOM at each time, one contains the updated Virtual DOM and one which is just the pre-update version of this updated Virtual DOM.
- Now it compares the pre-update version with the updated Virtual DOM and figures out what exactly has changed in the DOM like which components have been changed.
- **Diffing** -> This process of comparing the current Virtual DOM tree with the previous one is known as **‘diffing’**.
- Once React finds out what exactly has changed then it updated those objects only, on real DOM.
- **Batch Updates** -> React uses something called as **Batch Updates** to update the real DOM, It just mean that the changes to the real DOM are sent in batches instead of sending any update for a single change in the state of a component. 
- We have seen that the re-rendering of the UI is the most expensive part and React manages to do this most efficiently by ensuring that the Real DOM receives batch updates to re-render the UI.
- **Reconciliation** ->  This entire process of transforming changes from the virtual dom to the real DOM is called **Reconciliation**, This significantly improves the performance and is the main reason why React and it’s Virtual DOM is much loved by developers all around.


