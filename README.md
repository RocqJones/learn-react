# learn-react
Learn React  JS

# What Is React?
React is a *declarative, efficient, and flexible JavaScript library for building user interfaces.* It lets you compose complex UIs from small and isolated pieces of code called “components”.
* React has a few different kinds of components, but we’ll start with React.Component subclasses:
```
class ShoppingList extends React.Component {
  render() {
    return (
      <div className="shopping-list">
        <h1>Shopping List for {this.props.name}</h1>
        <ul>
          <li>Instagram</li>
          <li>WhatsApp</li>
          <li>Oculus</li>
        </ul>
      </div>
    );
  }
}

// Example usage: <ShoppingList name="John" />
```
* We use **components** to tell React what we want to see on the screen. When our data changes, React will efficiently update and re-render our components.
* **ShoppingList** is a **React component class, or React component type**. A *component takes in parameters, called **props (short for “properties”)**, and returns a hierarchy of views to display via the **render method**.*
- The **render method** returns a description of what you want to see on the screen. 
- React takes the description and displays the result. In particular, render returns a React element, which is a lightweight description of what to render.
* A special syntax called **“JSX”** which makes these structures easier to write. The <div /> syntax is transformed at build time to React.createElement('div'). The example above is equivalent to:
```
return React.createElement('div', {className: 'shopping-list'},
  React.createElement('h1', /* ... h1 children ... */),
  React.createElement('ul', /* ... ul children ... */)
);
```
