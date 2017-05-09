# ReactJs-Interview-Questions
ReactJs Interview Questions

1. **What is Virtual DOM? List down the steps on how does React Handle change to the DOM?**
> A virtual DOM object is a representation of a DOM object, like a lightweight copy. When you render a JSX element, every single virtual DOM object gets updated. Once the virtual DOM has updated, then React compares the virtual DOM with a virtual DOM snapshot that was taken right before the update. Once React knows which virtual DOM objects have changed, then React updates those objects, and only those objects, on the real DOM.
> In summary, here's what happens when you try to update the DOM in React:
>
> - The entire virtual DOM gets updated.
> - The virtual DOM gets compared to what it looked like before you updated it. React figures out which objects have changed.
> - The changed objects, and the changed objects only, get updated on the real DOM.
> - Changes on the real DOM cause the screen to change.
2. **Why can't we call** *this.setState* **from render function of React Component?**
> Answer Coming Soon...
3. **What do you mean by Automatic Binding of context in React?**
> Answer Coming Soon...
4. **What is Stateless Functional Component and how do we define them?**
> Answer Coming Soon...
5. **What are propTypes and how do we define propTypes for Stateless Functional Component?**
> Answer Coming Soon...
