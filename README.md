# ReactJs Interview Questions
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
> *this.setState* updates the state of the component and since the component state is updated, it calls render method on its own. So, if we call *this.setState* from render method there will be infinite loop.
3. **What do you mean by Automatic Binding of context in React?**
> Automatic binding allows you to pass functions as props, and any *this* values in the functions' bodies will automatically refer to whatever they referred to when the function was defined. Consider following code example:

    var Parent = React.createClass({
        inputChanged: function() {
            //do something using context this
        },
        render: function() {
            return <Child onChange={this.inputChanged}>
        }
    })

    var Child = React.createClass({
        render: function() {
            return <input onChange={this.props.onChange}>
        }
    });
    
> When input changes in Child component, inputChanged function of Parent component is called. 
Considering dynamic context binding in Javascript, inputChanged must have *this* referring to Child component,
but because of automatic binding by ReactJS, the context refers to where the function is defined hence *this* 
in inputChanged refers to Parent component.

4. **What is Stateless Functional Component and how do we define them?**
> Component written directly as function is called stateless functional component. e.g.

    function Card(props) {
        return (
            <div>
                <div>{props.name}</div>
                <div>{props.email}</div>
                <div>{props.phone}</div>
            </div>
        )
    } 

> When a component class has nothing else but only render function and returns JSX then stateless functional component can be used. The props parameter passed to the function is equivalent to {this.props}.
5. **What are propTypes and how do we define propTypes for Stateless Functional Component?**
> If a component class expects the prop to be passed from parent component then propTypes is to be used. It helps in mainly in two purposes:

> - Validation w.r.t. datatype, required etc
> - Documenting the expected properties.

> propTypes in components:

    var Child = React.createClass({
        propTypes: {
            name: React.PropTypes.string
        },
        render: function() {
            return <div>{this.props.name}</div>
        }
    })

> propTypes in stateless functional component should be provided as direct function properties:

    function Child(props){
        return <div>{this.props.name}</div>
    }
    Child.propTypes = {
        name: React.PropTypes.string
    };
    
#### Contd... ####

