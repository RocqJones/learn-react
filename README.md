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

## Why Immutability Is Important?
There are generally two approaches to changing data. 
1. The first approach is to mutate the data by directly changing the data’s values. 
2. The second approach is to replace the data with a new copy which has the desired changes.
#### Data Change with Mutation
```
var player = {score: 1, name: 'Jeff'};
player.score = 2;
// Now player is {score: 2, name: 'Jeff'}
```
#### Immutation / Data Change without Mutation
```
var player = {score: 1, name: 'Jeff'};

var newPlayer = Object.assign({}, player, {score: 2});
// Now player is unchanged, but newPlayer is {score: 2, name: 'Jeff'}

// Or if you are using object spread syntax proposal, you can write:
// var newPlayer = {...player, score: 2};
```
The end result is the same but by not mutating (or changing the underlying data) directly, we gain several benefits described below.
* **Complex Features Become Simple:** Immutability makes complex features much easier to implement. The ability to undo and redo certain actions is a common requirement in applications. Avoiding direct data mutation lets us keep previous versions of the code history intact, and reuse them later.
* **Detecting Changes** Detecting changes in mutable objects is difficult because they are modified directly. This detection requires the mutable object to be compared to previous copies of itself and the entire object tree to be traversed.
* **Determining When to Re-Render in React** The main benefit of immutability is that it helps you build pure components in React. Immutable data can easily determine if changes have been made, which helps to determine when a component requires re-rendering.
