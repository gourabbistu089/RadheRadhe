# Complete React Fresher Interview Guide

## 1. What is React?

React is a popular JavaScript library for building user interfaces. It was developed by Facebook and is widely used for creating interactive, fast, and scalable web applications.

Key points:
- React uses a component-based architecture
- It efficiently updates and renders components
- React uses a virtual DOM for better performance

## 2. What are the main features of React?

The main features of React include:

1. JSX
2. Virtual DOM
3. Component-based architecture
4. Unidirectional data flow
5. React Native for mobile development

## 3. What is JSX?

JSX (JavaScript XML) is a syntax extension for JavaScript that allows you to write HTML-like code in your JavaScript files. It makes it easier to write and understand the structure of React components.

Example:
```jsx
const element = <h1>Hello, world!</h1>;
```

## 4. What is a component in React?

A component is a reusable piece of the user interface. In React, there are two types of components:

1. Functional components
2. Class components

Example of a functional component:
```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

Example of a class component:
```jsx
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

## 5. What are props in React?

Props (short for properties) are a way to pass data from parent components to child components. They are read-only and help make your components reusable.

Example:
```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

function App() {
  return <Welcome name="Alice" />;
}
```

## 6. What is state in React?

State is an object that holds data that may change over time within a component. Unlike props, state is managed within the component and can be updated.

Example using a class component:
```jsx
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  render() {
    return <h1>Count: {this.state.count}</h1>;
  }
}
```

## 7. What is the difference between state and props?

- Props are passed from parent to child components and are read-only.
- State is managed within a component and can be changed using setState().
- Props are used to pass data, while state is for managing data.
- Changes in props come from outside the component, while state changes happen inside the component.

## 8. What is the virtual DOM?

The virtual DOM is a lightweight copy of the actual DOM. React uses it to improve performance by minimizing direct manipulations of the real DOM.

How it works:
1. When state changes, React creates a new virtual DOM tree.
2. This new tree is compared with the previous one (a process called "diffing").
3. React calculates the most efficient way to update the real DOM.
4. Only the necessary changes are applied to the real DOM.

## 9. What are React Hooks?

Hooks are functions that allow you to use state and other React features in functional components. They were introduced in React 16.8.

Common hooks:
- useState: Allows you to add state to functional components.
- useEffect: Performs side effects in functional components.
- useContext: Subscribes to React context without introducing nesting.

Example of useState:
```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

## 10. What is the purpose of the useEffect hook?

The useEffect hook allows you to perform side effects in functional components. It's used for tasks like data fetching, subscriptions, or manually changing the DOM.

Example:
```jsx
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

## 11. What is the significance of keys in React lists?

Keys are special attributes that help React identify which items in a list have changed, been added, or been removed. They help in efficient update of the user interface.

Example:
```jsx
function NumberList(props) {
  const numbers = props.numbers;
  const listItems = numbers.map((number) =>
    <li key={number.toString()}>
      {number}
    </li>
  );
  return <ul>{listItems}</ul>;
}
```

## 12. What is React Router?

React Router is a standard routing library for React applications. It enables navigation among views in a React application, allowing for a single-page application experience.

Basic usage example:
```jsx
import { BrowserRouter as Router, Route, Link } from "react-router-dom";

function App() {
  return (
    <Router>
      <div>
        <nav>
          <ul>
            <li><Link to="/">Home</Link></li>
            <li><Link to="/about">About</Link></li>
          </ul>
        </nav>

        <Route path="/" exact component={Home} />
        <Route path="/about" component={About} />
      </div>
    </Router>
  );
}
```

## 13. What are controlled components in React?

Controlled components are form elements whose values are controlled by React state. The component's state serves as the "single source of truth" for the input.

Example:
```jsx
class NameForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {value: ''};
  }

  handleChange = (event) => {
    this.setState({value: event.target.value});
  }

  handleSubmit = (event) => {
    alert('A name was submitted: ' + this.state.value);
    event.preventDefault();
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input type="text" value={this.state.value} onChange={this.handleChange} />
        </label>
        <input type="submit" value="Submit" />
      </form>
    );
  }
}
```

## 14. What is the context API in React?

The Context API provides a way to pass data through the component tree without having to pass props down manually at every level. It's designed to share data that can be considered "global" for a tree of React components.

Basic usage:
```jsx
// Create a context
const ThemeContext = React.createContext('light');

// Provider component
function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Toolbar />
    </ThemeContext.Provider>
  );
}

// Consumer component
function Toolbar() {
  return (
    <ThemeContext.Consumer>
      {theme => <div>Current theme: {theme}</div>}
    </ThemeContext.Consumer>
  );
}
```

## 15. What are React fragments?

React fragments let you group a list of children elements without adding extra nodes to the DOM. They're useful when you need to return multiple elements from a component.

Example:
```jsx
function Table() {
  return (
    <React.Fragment>
      <tr>
        <td>Hello</td>
        <td>World</td>
      </tr>
      <tr>
        <td>Another</td>
        <td>Row</td>
      </tr>
    </React.Fragment>
  );
}
```

Short syntax:
```jsx
function Table() {
  return (
    <>
      <tr>
        <td>Hello</td>
        <td>World</td>
      </tr>
      <tr>
        <td>Another</td>
        <td>Row</td>
      </tr>
    </>
  );
}
```

## 16. What is the difference between React and React Native?

While both are developed by Facebook and share core principles, they have different purposes:

- React is a JavaScript library for building user interfaces, primarily for web applications.
- React Native is a framework for building native mobile applications using React.

Key differences:
1. Output: React renders to the browser DOM, while React Native renders to native mobile components.
2. DOM: React uses a virtual DOM, while React Native uses a native API to render components on mobile.
3. Styling: React typically uses CSS, while React Native uses a JavaScript object for styling.
4. Navigation: Web apps use React Router, while React Native apps often use React Navigation.

## 17. What is the purpose of the useState hook?

The useState hook allows you to add state to functional components. It returns an array with two elements: the current state value and a function to update it.

Example:
```jsx
import React, { useState } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

## 18. What is the difference between class components and functional components?

Class components:
- Use ES6 class syntax
- Can have state and lifecycle methods
- Use 'this' keyword to access props and state

Functional components:
- Use function syntax
- Can now use hooks to manage state and side effects
- Generally more concise and easier to understand

Example of a class component:
```jsx
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

Example of a functional component:
```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

## 19. What is the purpose of the useContext hook?

The useContext hook provides a way to pass data through the component tree without having to pass props down manually at every level.

Example:
```jsx
const ThemeContext = React.createContext('light');

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Toolbar />
    </ThemeContext.Provider>
  );
}

function Toolbar() {
  const theme = useContext(ThemeContext);
  return (
    <div>
      <button style={{ background: theme }}>I am styled by theme context!</button>
    </div>
  );
}
```

## 20. What is the purpose of the useRef hook?

The useRef hook is used to persist values between renders. It can be used to store a mutable value that does not cause a re-render when updated.

Example:
```jsx
function TextInputWithFocusButton() {
  const inputEl = useRef(null);
  const onButtonClick = () => {
    // `current` points to the mounted text input element
    inputEl.current.focus();
  };
  return (
    <>
      <input ref={inputEl} type="text" />
      <button onClick={onButtonClick}>Focus the input</button>
    </>
  );
}
```

This guide covers the most important React concepts that freshers should be familiar with for interviews. It includes code examples to illustrate how these concepts are applied in practice. Remember to not just memorize these answers, but understand the underlying concepts and be prepared to discuss them in depth during your interview. Good luck with your React interview preparation!
