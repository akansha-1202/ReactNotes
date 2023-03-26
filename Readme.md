**React Roadmap doc:**
 https://docs.google.com/spreadsheets/d/15SA5agTJ-kksNk3xyVXWx7DyptlyAQiDqwVueUkpVuE/edit#gid=0

# Topics

1. React Introduction
    * What is React
    * React vs Vue vs Angular
2. React Features
    * Virtual Dom
    * SPA,JSX,Bebel
    * One way data binding
    * Components
    * Class component
    * Functional component
    * Named and default export
    * Communiny support
    * Web and mobile

3. Class and functional component
    * Components and props
    * Is there any reason to still use react class components?
    * Functional components vs class components in react
    * Migrate class components to functional components with Hooks in react

4. State and Props
    * How to use props 
    * Pass props in both class and functional component
    * How to update state from props
    * How to pass data from parent to child and vice versa
    * Putting props to usestate

5. Conditional rendering
    * How to perform
    * Different techniques for conditional rendering

6. Rendering
    * Life cycle methods

           @Mounting
              constructor()
              render()
              componentDidMount()
           @Updating
              shouldComponentUpdate()
              render()
              componentDidUpdate()
           @Unmounting
              componentWillUnmount()

7. Lists and keys
      * List components in react 
      * Why do we need the key props"

8.  Events Handling events in react 
      * Synthetic events
      * React event handler
9. HOC(Higher Order Component)"

10. HOOKS

      * UseState
      * useEffect
      * useMemo
      * useRef
      * UseReducer
      * UseCallback""
      * useContext
      * useParams hook

11. ROUTERS

      * How to perform routing
      * Brower router
      * Routes
      * Route
      * Link
      * Dynamic params in routing

12. Props drilling
13. State uplifting
14. Context API
15. Axio and fetch
      * Get, post, put,delete
      * Fetch json file and show it in the screen
      * Create own API and Fetch it and show on the screen
      * Difference between axio and fetch
16. Lazy loading 
17. Memory leak
18. State management
      * Redux toolkit 
      * perform CURD operation in redux
      * Redux thunk 
      * Redux saga vs Thunk




# **REACT NOTES** 

## DAY-1

## What is React.JS?

* React.js is a popular **open-source JavaScript library** used to build user interfaces for web applications. It was developed by `Facebook` and has been widely adopted by the web development community for its simplicity, speed, and flexibility.

* In a nutshell, React allows developers to create reusable UI components that can be combined to form complex user interfaces. Each component encapsulates its own logic and state, making it easier to reason about the behavior of the application.

* React is based on a concept called the **virtual DOM**, which is a lightweight representation of the actual DOM (Document Object Model). 
* When a user interacts with a React component, the virtual DOM is updated to reflect the changes, and then React efficiently updates only the necessary parts of the actual DOM to reflect those changes. This results in better performance and a smoother user experience.

**There are two kinds of programming,**
* Declarative Programming
* Imperative Programming

*Declarative Programming:*<br>
Its main goal is to get desired output without describing how to get it .
*Imperative Programming:*<br>
Its main goal is to describe how to get output or accomplish it
**React is Declarative in nature.**

* Finally, React can be used with other popular front-end libraries and frameworks, such as Redux for managing state and React Router for routing. It also has a large and active community, which provides helpful resources and support for developers.


## React Vs Angular Vs Vue


| Feature    | React     | Vue      | Angular    |
| :----------| :---------| :--------|:---------- |
| `Created by`      | Facebook | Evan You |Google|
| `Initial Release`      | 2013 | 2014. |2010 |
| `Architecture`      | Component-based | Component-based |Component-based |
| `Learning Curve`      | Low | Low |High |
| `Performance`      | High | High. |High |
| `Data Binding`      | One-way | Two-way | Two-way |
| `Templating`      | JSX | Html-based |Html-based |
| `State Management`      | Redux, Context API | Vuex |RxJS, ngrx |
| `Ecosystem`      | Large | Growing |Large |

# React features

## 1. React: The Virtual Dom
### DOM: 
DOM stands for Document Object Model. 
Normally, whenever a user requests a webpage, the browser receives an HTML document for that page from the server. The browser then constructs a logical, tree-like structure from the HTML to show the user the requested page in the client.

This tree-like structure is called the Document Object Model, also known as the DOM. It is a structural representation of the web document as nodes and objects, in this case, an HTML document.

![Alt text](dom.jpg)

### The problem with Dom

> DOM manipulation is the heart of the modern, interactive web. Unfortunately, it is also a lot slower than most JavaScript operations.
> This slowness is made worse by the fact that most JavaScript frameworks update the DOM much more than they have to.

## Virtual Dom 

* React contains a lightweight representation of real DOM in the memory called Virtual DOM.  
* DOM gets created whenever any React application gets loaded on the screen for the first time, Whenever React components gets mounted on the screen for the first time.
* Now when any user makes any changes on the screen like button click, then the changes will not directly go to Real Dom.
* So, we are having two virtual doms, one VDOM gets created at the time of mounting of react component so it is a copy of your real DOM.
* Another VDOM is the dom which contains the new changes, updated state variables values.
* Now these two virtual DOMs will get compared with each other and will check for the new changes this complete procedure is known as **`diffing algorithm.`**
* Now the new changes will be updated in your Real DOM, this procedure is known as **`Recoinciliation`**
This makes a big difference! React can update only the necessary parts of the DOM. React’s reputation for performance comes largely from this innovation.

In summary, here’s what happens when you try to update the DOM in React:

1. he entire virtual DOM gets updated.
2. The virtual DOM gets compared to what it looked like before you updated it. React figures out which objects have changed.
3. The changed objects, and the changed objects only, get updated on the real DOM.
4. Changes on the real DOM cause the screen to change.

## 2. SPA
 * A single-page application (SPA) is a type of web application that loads a single HTML page and dynamically updates the content as the user interacts with the application. In a traditional web application, clicking on a link or submitting a form would typically result in a request to the server, which would respond with a new HTML page to be rendered in the browser. In contrast, a SPA loads all the necessary HTML, CSS, and JavaScript files upfront and then communicates with the server in the background to fetch or update data as needed.

* React is a popular JavaScript library for building SPAs. React allows developers to create reusable UI components that can be composed together to create complex user interfaces. React components are declarative, meaning they describe what should be rendered on the page rather than how it should be rendered. This makes it easier to reason about the code and to make changes without introducing bugs.

* In a React SPA, the initial HTML page typically only contains a single "div" element, which serves as the entry point for the React application. When the page loads, React renders the initial UI based on the state of the application. As the user interacts with the application, React updates the UI in response to events such as button clicks or form submissions.

* To handle server requests, a React SPA typically uses an API (Application Programming Interface) to communicate with the server. The API provides a set of endpoints that the client-side code can use to fetch or update data. The client-side code sends requests to the server using the Fetch API or other libraries such as Axios or jQuery. When the server responds, the client-side code updates the state of the application and rerenders the UI as needed.

> One advantage of using a React SPA is that it can provide a smoother and more responsive user experience compared to traditional web applications, since the page does not need to reload every time the user interacts with it. However, SPAs can be more complex to build and maintain, since they require more client-side code and may require additional server-side infrastructure to support the API.

## 3. JSX and Babel
JSX is a syntax extension for JavaScript that allows developers to write HTML-like code within their JavaScript code. It was developed by Facebook as part of the React library and is used extensively in React applications.

With JSX, developers can write code that looks like HTML, but is actually a combination of JavaScript and HTML. For example, instead of creating a DOM element using plain JavaScript like this:

```javascript

const element = document.createElement('div');
element.innerText = 'Hello, world!';
```
In JSX, the same code can be written as:

```javascript
const element = <div>Hello, world!</div>;
```
> JSX is not a separate language, but a syntax extension that is transformed into plain JavaScript by a compiler such as **Babel.**
### Babel:
Babel is a JavaScript compiler that allows developers to use modern JavaScript syntax and features while still supporting older browsers that do not support these features. Babel can compile JSX code into plain JavaScript code that can be run in any modern web browser.

In addition to transforming JSX code, Babel can also transform other modern JavaScript features such as arrow functions, template literals, and classes into code that can run in older browsers. Babel does this by analyzing the code and replacing any unsupported features with equivalent code that can be run by older browsers.

Overall, JSX and Babel are important tools in the React ecosystem, allowing developers to write modern, expressive code that can be run on a wide range of web browsers.

## 4. One Way Binding
* One-way data binding is a data flow mechanism in which the data flows only in one direction, from the data source to the UI element. This means that when the data changes, the UI element that is bound to the data is automatically updated to reflect the new data, but the reverse is not true.

* In one-way data binding, changes made to the UI element do not update the data source. If the user changes a value in the UI, the change is not automatically propagated back to the data source. Instead, the developer must explicitly update the data source based on the new value in the UI.
> One advantage of one-way data binding is that it can simplify the code and reduce the risk of unintended consequences. Since the data flow is unidirectional, it is easier to reason about the code and to track the source of changes. Additionally, one-way data binding can improve performance by reducing the number of updates that need to be made to the UI.

Example: 

```javascript
import React, { useState } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times.</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```
This is an example of one-way data binding, as the value of count flows from the state variable to the UI element (the paragraph element), but changes made to the UI element do not affect the state variable.

If we were using two-way data binding, we would need to define an event handler for the paragraph element to update the state variable when the user changes the text. However, in one-way data binding, the paragraph element is only used to display the current value of the 'count' variable, and does not update the variable when clicked or changed.

## 5. Component based
* Component-based architecture: React allows developers to build complex UIs by breaking them down into small, reusable components. Each component is responsible for rendering a small part of the UI, and can be composed together to create larger, more complex UIs.
* There are two types of components in React 
1. Class based components
2. Functional based components

## 6. Named export and default export
A named export allows you to export multiple values from a module, and each of those values can be imported individually by their name. A default export, on the other hand, allows you to export a single value from a module, and that value can be imported using any name.

Here's an example of a module with named exports:

```javascript
// math.js
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;
```
In this example, the math.js module exports two functions: add and subtract. These functions can be imported individually like this:

```javascript
import { add, subtract } from './math.js';
console.log(add(2, 3)); // Output: 5
console.log(subtract(5, 2)); // Output: 3
```
> Note that when importing named exports, you need to use the curly braces and specify the names of the exports you want to import.

Now, let's take a look at an example of a module with a default export:

```javascript
// greeting.js
const greeting = name => `Hello, ${name}!`;
export default greeting;
```
In this example, the greeting.js module exports a single function called greeting. This function can be imported using any name like this:

```javascript
import sayHello from './greeting.js';
console.log(sayHello('John')); // Output: Hello, John!
```
> Note that when importing a default export, you don't need to use curly braces and can specify any name for the import.

In summary, named exports allow you to export multiple values from a module, and default exports allow you to export a single value from a module.

## 7. Community support
React has a significant advantage of community support, which is one of the reasons for its popularity among developers. The React community is very active and passionate about the technology, and there are many resources available to help developers learn and solve problems.

Here are some ways in which the React community provides support:

*Documentation*: React has comprehensive documentation that is regularly updated with new features and changes. The documentation is clear and easy to follow, making it an excellent resource for both beginners and experienced developers.

*Online forums and communities*: There are many online forums and communities where developers can ask questions, share knowledge, and discuss best practices related to React. These communities include Stack Overflow, Reddit, GitHub, and more.

*Third-party libraries and tools*: The React community has created many third-party libraries and tools that can help developers work more efficiently with React. These include libraries for state management, routing, styling, testing, and more.

*Conferences and meetups*: There are many conferences and meetups dedicated to React, where developers can attend talks, workshops, and networking events. These events provide an opportunity to learn from experts in the field and connect with other developers.

*Open-source contributions*: React is an open-source project, which means that anyone can contribute to its development. The React community has a strong culture of open-source contributions, and many developers have contributed code, bug fixes, and documentation to the project.

## 8. Web and Mobile 
React is effective for both web and mobile development because it allows developers to write reusable code that can be shared between different platforms.

React Native, a mobile framework built on top of React, allows developers to write mobile applications using the same programming language and development concepts as web applications. This makes it easier for developers to transition between web and mobile development, and to build applications that work seamlessly across both platforms.

Some of the features that make React effective for both web and mobile development include:

*Cross-platform compatibility*: React's focus on reusable components and virtual DOM makes it possible to write code that works on both web and mobile platforms. This reduces development time and cost, and makes it easier to maintain code across multiple platforms.

*Third-party libraries and tools*: The React community has developed many third-party libraries and tools that can be used to build web and mobile applications. These tools include libraries for state management, routing, styling, testing, and more, which can help developers work more efficiently and effectively.

# Components
## Class Components:

In React, class-based components are a type of component that is defined using a JavaScript class. They are an older method of defining components, and have largely been replaced by functional components in modern React development. However, they are still commonly used in legacy code and in some specialized cases.

Class-based components are defined using the class keyword, and they extend the React.Component class. They define a render() method that returns a React element, which describes the UI that should be rendered to the screen.

Here is an example of a class-based component:

```javascript
import React from 'react';

class ExampleComponent extends React.Component {
  render() {
    return (
      <div>
        <h1>Hello, world!</h1>
      </div>
    );
  }
}
```
> In this example, we define a class-based component called `ExampleComponent`. It extends the `React.Component` class and defines a `render`() method that returns a `div` element containing an `h1` element.

Class-based components have a few advantages over functional components, such as the ability to define state and lifecycle methods. However, they also have some disadvantages, such as being more verbose and harder to understand for beginners.

In general, functional components are preferred for modern React development, as they are easier to write and maintain, and provide better performance. However, class-based components are still a valuable tool in the React developer's toolbox, and can be useful in some specialized cases.

### what is constructor and super key word?
**constructor** are used for 2 purposes : <br>
In React class components to initialize the component's state and to bind event handlers.<br>

**super()** is used to call the constructor of its parent class. If we would like to set a property or access this inside the constructor we need to call super() method. 

> It is not necessary to have a constructor in every component.

> It is necessary to call super() within the constructor. To set property or use 'this' inside the constructor it is mandatory to call super().


### React Component with Constructor
```javascript

import React from 'react'; 
import ReactDOM from 'react-dom'; 
class Main extends React.Component { 
  constructor() { 
    super(); 
    this.state = { 
      planet: "Earth" 
    } 
  } 
  render() { 
    return ( 
      < h1 >Hello {this.state.planet}!</h1> 
    ); 
  } 
} 
ReactDOM.render(<Main />, document.getElementById('root')); 
```
output:
```
Hello Earth          
```
<!-- In this example, we define a class-based component called `ExampleComponent`. We define a `constructor` method that calls the `super` method to initialize the component's `props` and sets the component's initial state to an object with two properties, `name` and `age`. We then use the `name` and `age` state properties in the `render` method to display a message on the screen. -->

This is a very basic example, but it demonstrates how the constructor and super keywords are used to initialize a React class component's state.

### React Component without Constructor 
```javascript
import React from 'react'; 
import ReactDOM from 'react-dom'; 
class Main extends React.Component { 
  state = { 
    planet: "Mars" 
  } 
  render() { 
    return ( 
      < h1 >Hello {this.state.planet}!</h1> 
    ); 
  } 
} 
ReactDOM.render(<Main />, document.getElementById('root')); 
```
output:
```
Hello Mars! 
```

## Functional component
In React, function-based components are a newer and more lightweight way to define components than class-based components. They are defined using JavaScript functions and can be considered as pure functions that take in props and return a React element.

Here is an example of a function-based component:

```javascript
import React from 'react';

function ExampleComponent(props) {
  return (
    <div>
      <h1>Hello, {props.name}!</h1>
    </div>
  );
}
```
In this example, we define a function-based component called `ExampleComponent`. It takes in a `props` parameter, which is an object containing any props that are passed to the component. It returns a `div` element containing an `h1` element that displays the `name` prop.

Function-based components have several **advantages** over class-based components:

* They are simpler and more lightweight than class-based components, which makes them easier to read, write, and maintain.

* They are less verbose than class-based components, which means less boilerplate code.

* They are easier to test because they are just plain functions that take in props and return a React element.

* They are faster than class-based components, because they don't have the overhead of a class instance and lifecycle methods.

In summary, function-based components are a simpler and more lightweight way to define components in React. They are easier to read, write, and maintain, and provide better performance than class-based components. For these reasons, they have become the preferred way to define components in modern React development.

### Q. Is there any reason to still use react class components?

Yes, there are still some reasons to use React class components, although function components are now the preferred way of writing components in React.

Here are a few reasons why you might still choose to use React class components:

1. Legacy Codebase: If you are working on a legacy codebase that uses class components, it might be more efficient to continue using class components rather than rewriting all of your code.

2. Lifecycle Methods: React class components have access to a number of lifecycle methods that are not available to function components. If you need to use one of these lifecycle methods, such as componentDidMount or componentDidUpdate, you will need to use a class component.

3. More Explicit: Some developers prefer the more explicit nature of class components. With class components, everything is defined in one place, making it easier to see what's going on in your code.

That being said, function components are generally considered the better choice for new React projects, as they offer better performance, simpler syntax, and easier testing. However, there are still some cases where class components might be the better option.

## Functional component Vs Class component



|     | Functional Components |	Class Components |
| :---| :---------------------| :----------------|
|`Definition`|	Defined as a JavaScript function |	Defined as a JavaScript class|
|`Stat-Management` |	Uses useState and useEffect hooks to manage state and lifecycle methods|	Uses state and lifecycle methods inside the class|
|`Props`|	Passed in as an argument to the function | Passed in as a property to the class|
|`Lifecycle-Methods`|	Uses useEffect hook to manage component lifecycle	|Has access to lifecycle methods such as componentDidMount and componentDidUpdate|
|`Performance`|	Generally faster because they do not have to create an instance of the component|	Slightly slower because they have to create an instance of the component|
|`Syntax`|	Simpler and easier to read and understand|	More verbose and complex|
|`Code-Reusability`|	Can be easily reused in other components	|Cannot be easily reused in other components|
|`Testing`|	Easier to test because they are pure functions|	More difficult to test because they have state and lifecycle methods|
|`Refs`|	Cannot use refs directly inside the component|	Can use refs directly inside the component|


## *DAY-2*


# State and Props
## State:
* In React, a "state" is an object that represents the internal data of a component. It is used to manage the component's dynamic behavior and to render the component with updated information.
* The data is passed within the components only.State can be modified. State can be used only in class component. 

* State can be changed by using the **setState()** method, which is provided by the React framework. When a component's state changes, React automatically re-renders the component with the updated information.

* State is typically used to handle user input, control component behavior, and store component-specific data.

* It's important to note that state is meant to be used only within the component it belongs to. It should not be passed down to child components as props, as this can make the code harder to maintain and debug.

## Props:
* React is a component-based library that divides the UI into little reusable pieces. In some cases, those components need to communicate (send data to each other) and the way to pass data between components is by using props.

* “Props” is a special keyword in React, which stands for properties and is being used for passing data from one component to another.

* But the important part here is that data with props are being passed in a uni-directional flow. (one way from parent to child)

* Furthermore, props data is read-only, which means that data coming from the parent should not be changed by child components.

### Props in class component
In a class component in React, props can be accessed via the this.props object. Here's an example of how to use props in a class component:

*#Greeting.js*
```javascript
import React from 'react';

class Greeting extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}

export default Greeting;
```
In this example, the `Greeting` class extends React.Component and defines a `render` method that returns a greeting message with the value of the name `prop` passed to it.

When the Greeting component is used in another component, the name prop can be passed as an attribute, like this:

*#App.js*
```javascript
import React from 'react';
import Greeting from './Greeting';

class App extends React.Component {
  render() {
    return (
      <div>
        <Greeting name="Alice" />
        <Greeting name="Bob" />
      </div>
    );
  }
}

export default App;
```
In this example, the App class extends React.Component and renders two instances of the Greeting component, each with a different name prop passed to it. When the Greeting component is rendered, it accesses the value of the name prop via this.props.name and uses it to render the greeting message.

### Props in functional component
Here's an example of how to use props in a functional component:

*#Greeting.js*
```javascript
import React from 'react';

function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

export default Greeting;
```
In this example, the Greeting component is a simple functional component that receives a name prop and uses it to render a greeting message.

When the Greeting component is used in another component, the name prop can be passed as an attribute, like this:

*#App.js*

```javascript
import React from 'react';
import Greeting from './Greeting';

function App() {
  return (
    <div>
      <Greeting name="Alice" />
      <Greeting name="Bob" />
    </div>
  );
}

export default App;
```

In this example, the `App` component is rendering two instances of the `Greeting` component, each with a different name prop. When the Greeting component is rendered, it will receive the name prop as an argument to its function, and the value of the name prop will be used to render the greeting message.

## Difference between State and Props

|Property|	State|	Props|
| :------| :-----| :-----|
|`Source`|	Defined and managed within a component|	Passed from a parent component to a child|
|`Mutability`|	Mutable and can be changed within a component	|Read-only and cannot be modified|
|`Ownership`|	Owned by the component that defines it|	Owned by the parent component|
|`Usage`|	Used to manage data within a component|	Used to pass data down the component tree|
|`Updates`|	Changes trigger a re-render of the component	|Changes trigger a re-render of the component|
|`DefaultValues`|	Must be initialized by the component itself	|Can have default values defined by the parent|
|`Scope`|	Should only be accessed and modified within component|	Can be accessed by child components|

## Update State and props using class component
1. Updating State:

* To update the state, you need to call the `setState` method.
* setState method accepts an object that contains the new values of the state properties you want to update.
* It's important to note that setState is asynchronous, so you should not rely on the current state or props values when updating state.
Here's an example:
```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0,
    };
  }

  handleClick = () => {
    this.setState({ count: this.state.count + 1 });
  };

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.handleClick}>Increment</button>
      </div>
    );
  }
}
```
2. Updating Props:

* Props are read-only and cannot be directly modified by the component that receives them.
* However, you can pass new props to a component by re-rendering it with new prop values.
* To update props, you need to call the `setState` method of the parent component that passed the props to the child component.
* When the parent component updates its state, it triggers a re-render of the child component with the new prop values.
Here's an example:
```javascript
class ParentComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: "John",
    };
  }

  handleClick = () => {
    this.setState({ name: "Mary" });
  };

  render() {
    return (
      <div>
        <ChildComponent name={this.state.name} />
        <button onClick={this.handleClick}>Change Name</button>
      </div>
    );
  }
}

function ChildComponent(props) {
  return <p>Hello {props.name}</p>;
}
```
In summary, to update state, you call the setState method with the new state values. To update props, you update the parent component's state, which triggers a re-render of the child component with the new prop values.

## Update State and props using functional component

1. Update State
* To update state in functional components, you need to use the useState hook provided by React.
* The useState hook returns an array with two values: the current state value and a function that can be used to update the state value.
* To update the state value, you call the function returned by the useState hook with the new state value.
Here's an example:
```javascript
import React, { useState } from "react";

function MyComponent() {
  const [count, setCount] = useState(0);

  const handleClick = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={handleClick}>Increment</button>
    </div>
  );
}
```
2. Updating Props:

* Props are read-only and cannot be directly modified by the component that receives them, regardless of whether it is a functional component or a class component.
* To update props in functional components, you need to pass new prop values from the parent component.
* When the parent component updates its state, it triggers a re-render of the child component with the new prop values.
Here's an example:
```javascript
import React from "react";

function ParentComponent() {
  const [name, setName] = useState("John");

  const handleClick = () => {
    setName("Mary");
  };

  return (
    <div>
      <ChildComponent name={name} />
      <button onClick={handleClick}>Change Name</button>
    </div>
  );
}

function ChildComponent(props) {
  return <p>Hello {props.name}</p>;
}
```
In summary, to update state in functional components, you use the useState hook to update the state value. To update props, you pass new prop values from the parent component.

### >How to pass data from parent to child? 
In React, you can pass data from a parent component to a child component using props. 

*#Parent Component:*

```javascript
import React from 'react';
import ChildComponent from './ChildComponent';

function ParentComponent() {
  const data = {
    name: 'John Doe',
    age: 25,
    city: 'New York',
  };

  return (
    <div>
      <ChildComponent data={data} />
    </div>
  );
}

export default ParentComponent;
```
*#Child Component:*

```javascript
import React from 'react';

function ChildComponent(props) {
  const { data } = props;

  return (
    <div>
      <p>Name: {data.name}</p>
      <p>Age: {data.age}</p>
      <p>City: {data.city}</p>
    </div>
  );
}
export default ChildComponent;
```
Output:
![parent to child](./p-to-c.png)
In this example, the ParentComponent passes the data object to the ChildComponent as a prop. The ChildComponent then receives the data object as a prop, and can access its properties using dot notation (data.name, data.age, data.city) within the function body.


## Conditional Rendering
* Conditional rendering is a technique in React that allows you to render different content or components based on certain conditions. 
* It's a powerful way to make your components more dynamic and responsive to user input.

```javascript

import React, { useState } from 'react';

function Example() {
  const [showText, setShowText] = useState(false);

  const handleClick = () => {
    setShowText(!showText);
  };

  return (
    <div>
      <button onClick={handleClick}>Toggle Text</button>
      {showText && <p>Some text to show when button is clicked</p>}
    </div>
  );
}
export default Example;
```
Output:
![conditional](./image%20(1).png)

* In this example, we use the useState hook to create a boolean state variable called `showText`. The initial value is false, which means the text won't be shown initially.

* We also define a function called `handleClick` that toggles the value of `showText` between true and false.

* In the return statement, we render a button with an `onClick` event listener that calls handleClick when clicked. 
* We also use a conditional statement to render the text only when `showText` is true. If `showText` is false, the text won't be rendered.

* When the user clicks the button, the handleClick function is called, which toggles the value of showText. This causes the component to re-render, and the text will be shown or hidden based on the new value of showText.

Note that the conditional statement used here is a shorthand way to write an if statement. The expression { showText && `<p>`Some text to show when button is clicked`</p>` } means "if showText is true, render the `<p>` element; otherwise, render nothing".

**There are several techniques for performing conditional rendering in React:**

1. If statements: You can use regular if statements to conditionally render content. For example:

```javascript
function MyComponent(props) {
  if (props.isLoggedIn) {
    return <p>Welcome back!</p>;
  } else {
    return <p>Please log in.</p>;
  }
}
```
2. Ternary operator: You can use a ternary operator to create a more concise if/else statement. For example:

```javascript
function MyComponent(props) {
  return (
    <div>
      {props.isMember ? <p>Welcome, member!</p> : <p>Please sign up.</p>}
    </div>
  );
}
```
3. Logical && operator: You can use the logical && operator to conditionally render content. For example:

```javascript
function MyComponent(props) {
  return (
    <div>
      {props.hasData &&
        <ul>
          {props.data.map(item => <li key={item.id}>{item.name}</li>)}
        </ul>
      }
    </div>
  );
}
```
4. Switch statement: If you have multiple conditions to check, you can use a switch statement to conditionally render content. For example:

```javascript
function MyComponent(props) {
  switch (props.status) {
    case 'loading':
      return <p>Loading...</p>;
    case 'error':
      return <p>Error: {props.errorMessage}</p>;
    case 'success':
      return <p>Success!</p>;
    default:
      return null;
  }
}
```

## *DAY-4*

# Life Cycle Methods:

In React, lifecycle methods are special methods that allow you to perform actions at specific stages in a component's lifecycle. These methods are called automatically by React at different points in the component's life.

There are three phases in the React component lifecycle: mounting, updating, and unmounting. Each of these phases has its own set of lifecycle methods.
1. **Mounting:** The component is ready to mount in the browser DOM. This phase covers initialization from
The phase covers initialization from
* constructor()
* render()
* componentDidMount()
2. **Updating:** In this phase, the component gets updated by, sending the new props and updating the state from setState()
This phase covers initialization From
The phase covers initialization from
* shouldComponentUpdate()
* render()
* componentDidUpdate()
3. **Unmounting:** In this phase, the component is not needed and gets unmounted from the browser DOM.
The phase covers initialization from
* componentWillUnmount()

## Mounting:
The mounting means to put elements into the DOM. React uses virtual DOM to put all the elements into the memory. It has four built-in methods to mount a component namely.
1. Constructor()
2. render()
3. componentDidMount()

**Constructor()**
method is called when the component is initiated and it’s the best place to initialize our state. The constructor method takes props as an argument and starts by calling super(props) before anything else.
```javascript
import React, { Component } from 'react'

export default class App extends Component {
  constructor(props){
    super(props)
    this.state = {
      name: 'Constructor Method'
    }
  }
  render() {
    return (
      <div>
       <p> This is a {this.state.name}</p>
      </div>
    )
  }
}
```
**render()**
* The render() function does not modify the component state, it returns the same result each time it’s invoked and is
responsible for describing the view to be rendered to the browser window.
* render() is called by React at various app stages, generally when the React component is first instantiated, or when there is a new update to the component state.

> Note : render() will not be invoked if shouldComponentUpdate() returns false.

**componentDidMount()**
The most common and widely used lifecycle method is componentDidMount. This method is called after the component is rendered.

```javascript
import React, { Component } from 'react'

export default class componentDidMountMethod extends Component {
  constructor(props){
    super(props)
    this.state = {
      name: 'This name will change in 5 sec'
    }
  }
  componentDidMount() {
    setTimeout(() => {
      this.setState({name: "This is a componentDidMount Method"})
    }, 5000)

  }
  render() {
    return (
      <div>
       <p>{this.state.name}</p>
      </div>
    )
  }
}
```
output:
```
This is a componentDidMount Method 
```
The above example will print This is a componentDidMount Method after 5 sec. This proves that the method is called after the component is rendered.

## Updating
This is the second phase of the React lifecycle. A component is updated when there is a change in state and props React basically has five built-in methods that are called while updating the components.
1. shouldComponentUpdate()
2. render()
3. componentDidUpdate()

**shouldComponentUpdate()**
 is used when you want your state or props to update or not. This method returns a boolean value that specifies whether rendering should be done or not. The default value is true.
 ```javascript
 import React, { Component } from 'react'

export default class shouldComponentUpdateMethod extends Component {
  constructor(props){
    super(props)
    this.state = {
      name: 'shouldComponentUpdate Method'
    }
  }
  shouldComponentUpdate() {
    return false; //Change to true for state to update
  }

  componentDidMount(){
    setTimeout(() => {
      this.setState({name: "componentDidMount Method"})
    }, 5000)
  }
  render() {
    return (
      <div>
       <p>This is a {this.state.name}</p>
      </div>
    )
  }
}
```
**componentDidUpdate** method is called after the component is updated in the DOM. This is the best place in updating the DOM in response to the change of props and state.

```javascript
import React, { Component } from 'react'

export default class componentDidUpdateMethod extends Component {
    constructor(props){
        super(props)
        this.state = {
            name: 'from previous state'
        }
    }
    componentDidMount(){
        setTimeout(() => {
            this.setState({name: "to current state"})
          }, 5000)
    }
    componentDidUpdate(prevState){
        if(prevState.name !== this.state.name){
            document.getElementById('statechange').innerHTML = "Yes the state is changed"
        }
    }
    render() {
        return (
            <div>
                State was changed {this.state.name}
                <p id="statechange"></p>
            </div>
        )
    }
}
```
In the above example, you will notice that first I have initialized the name state inside the constructor method and after that changed state using setState inside `componentDidMount` method. So basically the name state should be changed from "`shouldComponentUpdate` Method" to `“componentDidMount` Method” after `5` seconds but it didn’t change because of `shouldComponentUpdate` set to `false`, If you change that true the state will be updated.

**componentDidUpdate()**<br>
The componentDidUpdate method is called after the component is updated in the DOM. This is the best place in updating the DOM in response to the change of props and state.

```javascript
import React, { Component } from 'react'

export default class componentDidUpdateMethod extends Component {
    constructor(props){
        super(props)
        this.state = {
            name: 'from previous state'
        }
    }
    componentDidMount(){
        setTimeout(() => {
            this.setState({name: "to current state"})
          }, 5000)
    }
    componentDidUpdate(prevState){
        if(prevState.name !== this.state.name){
            document.getElementById('statechange').innerHTML = "Yes the state is changed"
        }
    }
    render() {
        return (
            <div>
                State was changed {this.state.name}
                <p id="statechange"></p>
            </div>
        )
    }
}
```
In the above example, I have set the name state to to current state So React will render the `name` state from State was changed from previous state to State was changed to current state after `5` seconds. Using the conditional checking of the current state with the previous state **prevState.name !== this.state.name** inside the `componentDidUpdate` method, we are updating the value of the id `statechange` to `Yes the state is changed .`


**componentWillUnmount()**<br>
If there are any cleanup actions like canceling API calls or clearing any caches in storage you can perform that in the componentWillUnmount method. You cannot use setState inside this method as the component will never be re-rendered.

```javascript

import React, { Component } from 'react'

export default class componentWillUnmount extends Component {
    constructor(props){
        super(props)
            this.state = {
                show: true,
            } 
    }
    render() {
        return (
            <>
              <p>{this.state.show ? <Child/> : null}</p>
               <button onClick={() => {this.setState({show: !this.state.show})}}>Click me to toggle</button>
            </>
        )
    }
}

export class Child extends Component{
    componentWillUnmount(){
        alert('This will unmount')
    }
    render(){
        return(
            <>
            I am a child component
            </>
        )
    }
}
```
In the above example, I have created a simple toggle button which will show our `Child component` if the state is set to true. 

So after clicking on the button an alert will popup displaying `This will unmount` The alert will popup because the component is about to be removed from the DOM which in our case is the Child component.

## *DAY-6*

## Events in react
<p>Event handling essentially allows the user to interact with a webpage and do something specific when a certain event like a click or a hover happens. </p>
<p>When the user interacts with the application, events are fired, for example, mouseover, key press, change event, and so on.</p>

![Alt text](events.PNG)

The actions to which JavaScript can respond are called events. Handling events with react is very similar to handling events in DOM elements.

Below are some general events that you would see in and out when dealing with React-based websites:  

* Clicking an element  
* Submitting a form 
* Scrolling page 
* Hovering an element  
* Loading a webpage 
* Input field change 
* User stroking a key 
* Image loading 

### DIFFERENCE BETWEEN HTML AND REACT EVENT HANDLING :
React event handling is similar to HTML with some changes in syntax, such as:

React uses camelCase for event names while HTML uses lowercase.

Instead of passing a string as an event handler, we pass a function in React.

Example:
In HTML:
```
<button onclick="clickHandler()">
  Clicked
</button>
```
In React js
```
<button onClick={clickHandler}>
  Clicked
</button>
```
Also, like in HTML, we cannot return false to prevent default behavior; we need to use preventDefault to prevent the default behavior.

In HTML
```
<form onsubmit="console.log('clicked'); 
   return false">
  <button type="submit">Submit</button>
</form>
```
In React js
```javascript
function Form() {
  function handleClick(e) {
    e.preventDefault();
    console.log('Clicked');
  }

  return (
    <form onSubmit={handleClick}>
      <button type="submit">Submit</button>
    </form>
  );
}
```
Here, e is a synthetic event. React events do not work exactly the same as native events. See the SyntheticEvent reference guide to learn more.

When using React, you generally don’t need to call addEventListener to add listeners to a DOM element after it is created. Instead, just provide a listener when the element is initially rendered.

**Changing state in onClick event listener:**

```javascript
function EventBind() {
  const [steps, setSteps] = useState(0);
  const clickHandler = () => {
    setSteps(steps + 1);
  };
  return (
    <>
      <div>{steps}</div> 
      <button onClick = {clickHandler}> Click </button>
    </>
  );
}
export default EventBind
```
**Let’s see some of the event attributes:**   

* onmouseover: The mouse is moved over an element 
* onmouseup: The mouse button is released 
* onmouseout: The mouse  is moved off an element 
* onmousemove: The mouse is moved 
* Onmousedown: mouse button is pressed  
* onload: A image is done loading 
* onunload: Existing the page  
* onblur: Losing Focus  on element  
* onchange: Content of a field changes 
* onclick: Clicking an object  
* ondblclick: double clicking an object  
* onfocus element getting a focus  
* Onkeydown: pushing a keyboard key 
* Onkeyup: keyboard key is released 
* Onkeypress: keyboard key is pressed  
* Onselect: text is selected 


## What are synthetic events in ReactJS ?

In order to work as a cross-browser application, React has created a wrapper same as the native browser in order to avoid creating multiple implementations for multiple methods for multiple browsers, creating common names for all events across browsers. Another benefit is that it increases the performance of the application as React reuses the event object.

It pools the event already done hence improving the performance.


 > `e.preventDefault()` prevents all the default behavior by the browser.

> `e.stopPropagation()` prevents the call to the parent component whenever a child component gets called.

Note: **Here ‘e’ is a synthetic event**, a cross-browser object. It is made with a wrapper around the actual event of the browser. 




# Higher Order Compoent


In React, a Higher-Order Component (HOC) is a function that takes a component as an input and returns a new component with additional functionality. Essentially, it's a way to reuse component logic and share it between different components.

To use a HOC, you simply pass your component as an argument to the function that defines the HOC. The function returns a new component with the added functionality.

So in this below example im going to create one counter and hover counter basically , whenever i hover over the text the counter should be updated by one. 


App.js 
```javascript
import React from "react";
import ClickCounter from "./ClickCounter";
import HoverComp from "./HoverComp";

const App = () => {
  return (
    <div>
      <ClickCounter />
      <HoverComp />
    </div>
  );
};

export default App;

```
ClickCounter.js 
```javascript
import React from "react";
import UpdatedComp from "./UpdatedComp";

const ClickCounter = ({ count, incrementCount }) => {
  console.log(incrementCount);
  return <button onClick={incrementCount}> Count {count} Times </button>;
};

export default UpdatedComp(ClickCounter);

```
HoverComp.js 
```javascript 
import React from "react";
import UpdatedComp from "./UpdatedComp";

const HoverComp = ({ count, incrementCount }) => {
  console.log(incrementCount);
  return <h2 onMouseOver={incrementCount}> Hovered {count} Times </h2>;
};

export default UpdatedComp(HoverComp);

```
UpdatedComp.js
```javascript
import React, { useState } from "react";

const UpdatedComp = (OriginalComponent) => {
  const NewComponent = () => {
    const [count, setCount] = useState(0);

    const incrementCount = () => {
      setCount(count + 1);
    };

    return <OriginalComponent count={count} incrementCount={incrementCount} />;
  };

  return NewComponent;
};

export default UpdatedComp;

```
Output:
![alt](./image%20(2).png)
So after hovering over the text and click on the button the counter will update by one.
![alt](./image%20(3).png)

In this code, the UpdatedComp function is the higher-order component. It takes a component as its argument and returns a new component with an added state `count` and a method `incrementCount` that updates the count. The OriginalComponent is rendered inside the NewComponent, and the count and `incrementCount` props are passed to it.

Both ClickCounter and HoverComp components are wrapped in the UpdatedComp higher-order component to enhance them with the count state and `incrementCount` method. Therefore, they have access to the count and `incrementCount` props, which they can use to update their state and re-render.

In summary, the higher-order component in this code is the UpdatedComp function that takes a component as an argument and returns a new component with added functionality. It is used to enhance the ClickCounter and HoverComp components with state and methods.

## *DAY-8*

# **HOOKS**

* In React, Hooks are functions that allow developers to use state and other React features in functional components without the need for class components. 

* Hooks were introduced in React version 16.8 to provide a simpler and more flexible way to manage state and side effects in React components.

* In class component we use different Life cycle methods but in functional components we use hooks instead.

* Hooks allows to use state and other features without writing a class. 

**Benefits of using Hooks and Why Hooks was introduced ?**

● In react class component, we split our work into different life-cycle methods like componentDidMount,
componentDidUpdate and componentWillUnmount, but in hooks, we can do everything in a single hook called useEffect.

● In the class component, we have to use this keyword and also we have to bind event listeners, which increases
complexity. This is prevented in react functional components.

**There is 2 rules to use Hooks.** 
1. Only call Hooks at the top level:-<p>
 Do not call hooks inside loops, conditions or nexted functions. Hooks should always be used at the top level of the react functions.

2. Only call hooks from React functions:- <p>
You can't call hooks from regular js functions instead you can call hooks from React functional component. 

There are several types of hooks in React such as: 
  * UseState
  * useEffect
  * useMemo
  * useRef
  * UseReducer
  * UseCallback
  * useContext
  * useParams 
  * useHistory 


## UseState
-> usestate hooks allows us to track state in a functional component.<p>
-> State generally refers to data or properties that need to be tracking in an application.<p>
-> usestate can be used to toggle between 2 values, usually true and false.

**How to use it**

first we have to import
```
import {usestate} from 'react'
```
then inside a function write
```
const[count.setCount]=usestate(0);
        |         |
        |         |
     (current    (Update the 
      state)     counter's state)
```
Example
```javascript
import React ,{useState} from "react";

function App() {
    const[Count,setCount]= useState(0);

    return(
        <>
        <h1> count:{Count}</h1>
        <button onClick={()=>setCount(Count+1)}>Click</button>
        </>
    )    
}
 export default App
```

In this example, we declare a state variable called count using the `useState` hook and initialize it to 0. We also declare a function called `setCount` which will be used to update the `count` state variable.

## useEffect
**->** The Effect Hook allows us to perform side effects (an action) in the function components. It does not use components lifecycle methods which are available in class components.

**->** In other words, Effects Hooks are equivalent to componentDidMount(), componentDidUpdate(), and componentWillUnmount() lifecycle methods.

**->** useEffect allows you to run side effects after the component has rendered, and also provides a way to clean up any side effects when the component is unmounted or updated. Here is an example of how to use useEffect:

Side effects have common features which the most web applications need to perform, such as:

* Updating the DOM,
* Fetching and consuming data from a server API,
* subscribing to events.

-> useEffect accepts 2 arguments (callback,[dependency])

> **The dependency array** is passed as the second argument to useEffect, and can contain one or more values. If the array is empty, the effect will only run once, when the component is mounted. If the array contains any values, the effect will re-run whenever one of those values changes.

```javascript
function App() {
    const[Count,setCount]= useState(0);
    const [num,setNum]= useState(0);

    useEffect(()=>{
        alert("clicked")
    })

    return(
        <>
        <h1> count:{Count}</h1>
        <button onClick={()=>setCount(Count+1)}>Click</button>
        <h1> Number:{num}</h1>        
        <button onClick={()=>setNum(num+1)}>Click</button>
        </>
    )    
}
export default App
```
Output:
![useeffect](./image%20(4).png)

Here we declare 2 states `setCount` and `setNum`. and add counter to both of them . And we use useeffect and alert. so when one user click on the both buttons in every render one alert will appear. 

Now lets use empty dependency
```javascript
  useEffect(()=>{
        alert("clicked")
    },[])
```
So we just add empty array dependency, now when ever the page is reload for the first time it will show alert. Then whenever we click on both buttons the alert will not popup.

```javascript
 useEffect(()=>{
        alert("clicked")
    },[num])
```    
Here we pass num state in the dependency.Now when we click on count state button the alert will not popup but whenever we click on num state button the alert will popup everytime we click on the button and simontaniouly the increment will occure.

## useMemo
useMemo is a React hook that allows you to memoize the result of a function, and recompute the result only when the dependencies of the function have changed.

In simple terms, useMemo can be used to optimize the performance of your React components by avoiding unnecessary re-renders.

```javascript
function App() {
  const [a, setA] = useState(0);
  const [b, setB] = useState(0);

  const result = useMemo(() => {
    console.log('Calculating result...');
    return a+b;
  }, [a,b]);

  return (
    <div>
      <p>Result: {result}</p>
      <button onClick={()=>setA(a+1)}>Increment A</button>
      <button onClick={()=>setB(b+1)}>Increment B</button>
    </div>
  );
}
```
Output:
![useMemo](./image%20(5).png)

In this example, we use useMemo to compute the sum of a and b, and store the result in the result variable. The useMemo function takes a callback function as its first argument, which is the function that we want to memoize. 

The second argument is an array of dependencies that useMemo will use to determine when to recompute the result.

useMemo can be used for more complex computations as well. For example, if you have a component that does a lot of expensive calculations, you can use useMemo to avoid recalculating those values every time the component re-renders.

> In summary, useMemo is a React hook that can be used to memoize the result of a function and optimize the performance of your components. By avoiding unnecessary re-renders, you can create faster and more efficient React applications.

## useCallback

useCallback will return a memoized version of the callback that only changes if one of the dependencies has changed. This is useful when passing callbacks to optimized child components that rely on reference equality to prevent unnecessary renders.

In simple terms, useCallback can be used to optimize the performance of your React components by avoiding unnecessary re-renders of child components.

```javascript
import React, { useState, useCallback } from 'react';

function MyComponent(props) {
  const [count, setCount] = useState(0);

  const handleClick = useCallback(() => {
    setCount(count + 1);
  }, [count]);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={handleClick}>Increment Count</button>
      <ChildComponent handleClick={handleClick} />
    </div>
  );
}

function ChildComponent(props) {
  return (
    <div>
      <p>Child component</p>
      <button onClick={props.handleClick}>Increment Count</button>
    </div>
  );
}

export default MyComponent;
```
Output:
![usecallback](./image%20(6).png)

In this example, we use useCallback to memoize the `handleClick` function that is passed as a prop to the ChildComponent. The useCallback function takes a callback function as its first argument, which is the function that we want to memoize. The second argument is an array of dependencies that useCallback will use to determine when to re-create the function.

In this case, the handleClick function is only re-created when the count state changes. This means that if the handleClick function is passed as a prop to a child component, and that child component re-renders, the handleClick function will not be re-created unless the count state changes.

### Advantage:
useCallback can be useful when you have a function that is passed down to multiple child components, and you want to avoid unnecessary re-renders of those components. By memoizing the function, you can ensure that it is only re-created when necessary, which can improve the performance of your React components.

> In summary, useCallback is a React hook that can be used to memoize a function and optimize the performance of your components. By avoiding unnecessary re-creation of functions, you can create faster and more efficient React applications.


## useRef
useRef is a React hook that allows you to create a mutable reference to an element or value, which persists across re-renders of your component.

 It returns an object with a single property, `current`, which initially holds the value passed as argument (or undefined if no argument is provided). We can modify the `current` property without triggering a re-render of the component. This makes it useful for managing mutable values and for accessing the underlying DOM elements.

In simple terms, useRef can be used to store values that don't change often and are not used for rendering purposes, such as DOM elements, timers, or any other mutable value.

```javascript

function App() { 
  const [inputValue, setInputValue] = useState(""); 
  const count = useRef(0); 
  useEffect(() => { 
    count.current = count.current + 1; }); 
    return ( 
      <> 
        <input type="text" 
        value={inputValue} onChange={(e) => 
        setInputValue(e.target.value)} /> 
        <h1>Render Count: {count.current}</h1> 
      </> ); 
      } 
      
export default App;
```
Output:
![useref](./image%20(7).png)
In the example,
The component has a local state variable called `inputValue` that is initialized with an empty string using useState. `setInputValue` is a function used to update the value of `inputValue` state variable when the input field changes.

The component also has a count variable initialized with a value of 0 using the `useRef` hook. count is used to keep track of the number of times the component has been rendered.

The useEffect hook is used to update the value of count variable whenever the component is rendered. The useEffect hook runs after the component has been rendered, and it updates the count variable by incrementing it by 1.

The component returns two elements: an input field and an h1 element that displays the current value of count. Whenever the input field is changed, the setInputValue function is called, which updates the inputValue state variable and causes the component to re-render. When the component is re-rendered, the useEffect hook runs and updates the value of count to reflect the new render count.


## useReducer
It does very similiar to setState, It's a different way to manage state using Redux Pattern. Instead of updating the state directly, we dispatch actions, that go to a reducer function, and this function figure out, how to compute the next state.

```javascript
 function App() { 
  const initial = 0; 
  const reducer = (state, action) => { 
    switch (action) { 
      case "add": return state + 1; 
      case "sub": return state - 1; 
      case "reset": return 0; 
      default: return 0; 
    } 
  } 
  const [value, dispatch] = useReducer(reducer, initial) return ( 
    <div> 
    <h2>{value}</h2> 
    <button onClick={() => dispatch("add")}>Add</button> 
    <button onClick={() => dispatch("sub")}>subtract</button> 
    <button onClick={() => dispatch("reset")}>reset</button> 
    </div> 
    ); 
  }
```
![usereducer](./image%20(8).png)
In this example,
The component initializes a constant `initial` with a value of 0. This is the initial value for the state managed by the `useReducer` hook. The component also defines a reducer function, which takes in the current state and an action object, and returns a new state based on the action.

The reducer function used in this component has a switch statement that checks the type of action passed in, and returns the updated state based on the action. In this case, there are three possible actions: "add", "sub", and "reset". 

If the action is "add", the reducer returns the current state plus one. If the action is "sub", the reducer returns the current state minus one. If the action is "reset", the reducer returns the initial value of 0.

The `useReducer` hook is used to initialize a state variable called value with the initial value of 0, and a `dispatch` function that allows you to dispatch actions to the reducer. The `useReducer` hook takes two arguments: the reducer function and the initial state value.

The component returns a `div` that contains an `h2` element that displays the current value of `value`, and three buttons that dispatch the corresponding actions to the reducer when clicked. 

When the buttons are clicked, the `dispatch` function is called with the appropriate action object, and the useReducer hook updates the state based on the action. The h2 element is re-rendered with the updated value of value.


## UseParams

The useParams hook is a built-in hook in React Router that allows you to access the parameters of the current route. It returns an object containing key-value pairs of the parameters.

Here's an example of how to use useParams:

```javascript
import { useParams } from 'react-router-dom';

function App() {
  const { productId } = useParams();

  return (
    <div>
      <h1>Product ID: {productId}</h1>
    </div>
  );
}
export default App
```
In the example above, useParams is used to get the productId parameter from the current route. This parameter can be accessed via the productId variable. For example, if the current URL is /products/123, the productId variable would be '123'.

## *DAY-9*

  # Routing
  ## What is a React Router ?
* React Router is a powerful routing library built on top of React that helps to flow your application incredibly quickly, while
keeping the URL in sync with what's being displayed on the page.

* When a user types a specific URL into the browser, and if this URL path matches any 'route' inside the router file, the user
will be redirected to that particular route.

* React Router Dom is used to build applications that have many pages or components but the page is never refreshed
instead the content is dynamically fetched based on the URL

**Q.What is the difference between react-router and react-router-dom ?**

In React Router v4, the React Router was broken into two: react-router and react-router-dom. react-router is the core, and
react-router-dom is the core plus the React Router elements such as
`<BrowserRouter>` and `<NavLink>`
Since react-router-dom is like a super-set of react-router, you only need to import react-router-dom.

### **What is BrowserRouter ?**
BrowserRouter is responsible for understanding the url and then going ahead and ensuring that ui that we have or component we have is as per that particular url

Installation
```
npm i react-router-dom
```
### **What is Routes ?**
The Routes component is used to define the routes for your application. It takes one or more Route components as its children and renders the first Route that matches the current URL. If none of the Route components match the current URL, the Routes component renders nothing.

### **What is Route ?**

The Route component is used to define a single route in your application. It takes two props: path and element. The path prop specifies the URL pattern that the Route should match, and the element prop specifies the component that should be rendered when the Route matches.

### **What is path ?**

The path prop is used to specify the URL pattern that a Route should match. It can be a string or a regular expression that matches the desired URL pattern. For example, if you want to match the URL /about with a Route, you would set the path prop to "/about".

### **What is Link in React ?**
Link is a primary way to allow users to navigate around your application from page to another without loading
The difference between link and anchor tag is that

● anchor tag when we navigate to another page there is a loading happen

● Link when we navigate to another page through link the page will not load.

**How to use links in React ?**

Initially we are on Home page , on click of Home we move to about page and there is a change in url(localhost:3000/about)


Here lets take one simple example how to perform routing .
We are taking 3 pages Home, About, Contact. And i place them in ul tag as a link so that whwnever we click on particular link it will redirect to that page.


*#index.js*

```javascript
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import { BrowserRouter } from 'react-router-dom';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <BrowserRouter>

    <App />
    
    </BrowserRouter>

  </React.StrictMode>
);
```

*#App.js*
```javascript
import './App.css';
import Home from './component/Home';
import About from './component/About';
import Contact from './component/Contact';
import {Routes,Route,Link} from 'react-router-dom'

function App() {
  return (
    <>
     <ul>
    <li><Link to="/">Home</Link></li>
    <li><Link to="/about">About</Link></li>
    <li><Link to="/contact">Contact</Link></li>
    </ul>
  
    <Routes>
      <Route path="/"  element={<Home/>}/>
      <Route path="/about"  element={<About/>} />
      <Route path="/contact"  element={<Contact/>}/>
    </Routes>
    </>
  );
}
export default App;
```

*./component/Home.js*

```javascript
import React from "react"

const Home=()=>{
    return (
        <>
        Home
        </>
    )
}
```
export default Home

*./component/About.js*

```javascript
import React from "react"

const About=()=>{
    return (
        <>
        About
        </>
    )
}
export default About
```

*./component/Contact.js*

```javascript
import React from 'react'

const Contact = () => {
  return (
    <div>Contact</div>
  )
}

export default Contact
```
Output:
<span>
![Home](./image%20(9).png) ![Home](./image%20(10).png) ![Home](./image%20(11).png)
</span>



## Dynamic params in Routing

Dynamic parameters in routing refer to a feature in React Router that allows you to define URL patterns with variable segments. This is useful when you want to create routes that can handle a wide range of inputs without having to define a separate route for each one.

Here's a simple example of how to use dynamic parameters in React Router:

// App.js
```javascript
import { BrowserRouter as Router, Routes, Route } from 'react-router-dom';
import Home from './Home';
import User from './User';

function App() {
  return (
    <Router>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/users/:id" element={<User />} />
      </Routes>
    </Router>
  );
}

export default App;
```

// Home.js
```javascript
import { Link } from 'react-router-dom';

function Home() {
  return (
    <div>
      <h1>Home</h1>
      <ul>
        <li><Link to="/users/1">User 1</Link></li>
        <li><Link to="/users/2">User 2</Link></li>
        <li><Link to="/users/3">User 3</Link></li>
      </ul>
    </div>
  );
}

export default Home;
```

// User.js

```javascript

import { useParams } from 'react-router-dom';

function User() {
  const { id } = useParams();

  return (
    <div>
      <h1>User {id}</h1>
      <p>This is the page for User {id}.</p>
    </div>
  );
}

export default User;
```

In this example, we have three components:

* App: The top-level component that defines the routing for the app using Routes and Route.
* Home: A simple component that displays a list of links to different user pages.
* User: A component that displays information about a specific user, based on the dynamic parameter id in the URL.

When a user clicks on a link to a user page, React Router will match the URL to the Route for User and pass the id parameter as a prop. The User component then uses the useParams hook to extract the id parameter and render information specific to that user.


## State Uplifing

* Often there will be a need to share state between different components. The common approach to share state between two components is to move the state to common parent of the two components. This approach is called as lifting state up in React.js

* With the shared state, changes in state reflect in relevant components simultaneously. This is a single source of truth for shared state components.

![Alt text](lift.png)

## Props drilling

* It is the process by which you pass data from one component of the React Component tree to another by going through other components that do not need the data but only help in passing it around.

* In a React component hierarchy, props can be passed down from a parent component to its child component, and then to its child's child component, and so on. When a component deep down in the hierarchy needs to access data or functionality that is only available in a higher-level component, the data or functionality must be passed down through all the intermediate components via props. This process is known as **"props drilling".**

![Alt text](props.png)

Example 1: (With Props drilling)
In this below example we are taking one Parent.js and we need to pass some datas from parent to ChildC. For that we need to pass data from parent to ChildA then ChildA to ChildB and then ChildB to ChildC.


// App.js

```javascript
import Parent from "./woUsecontext/Parent";
  
const App=()=> {
  return (
    <div className="App">
      <Parent />
    </div>
  );
}
export default App
```
// Parent.js
```javascript
import React, { useState } from "react";
import ChildA from "./ChildA";

const Parent = () => {
    const [fName, setfName] = useState("SP");
    const [lName, setlName] = useState("Acharya");
  return (
    <>
      <div>This is a Parent component</div>
      <br />
      <ChildA fName={fName} lName={lName} />
    </>
  )
}

export default Parent
```
//ChildA.js
```javascript
import React from 'react'
import ChildB from './ChildB';

function ChildA({ fName, lName }) {
    return (
      <>
        This is ChildA Component.
        <br />
        <ChildB fName={fName} lName={lName} />
      </>
    );
  }

export default ChildA
```
// ChildB.js
```javascript
import React from 'react'
import ChildC from './ChildC';

function ChildB({ fName, lName }) {
    return (
      <>
        This is ChildB Component.
        <br />
        <ChildC fName={fName} lName={lName} />
      </>
    );
  }

export default ChildB
```
//ChildC.js
```javascript
import React from 'react'

function ChildC({ fName, lName }) {
    return (
      <>
        This is ChildC component.
        <br />
        <h3> Data from Parent component is as follows:</h3>
        <h4>{fName}</h4>
        <h4>{lName}</h4>
      </>
    );
  }

export default ChildC
```
Output:

![Alt text](a.png)

Demonstrating the Data initialized in Parent, Needed in last component(Child C) have to passed down each level known as Prop Drilling.

Props drilling can have several drawbacks, including:

1. Prop pollution: 

As props are passed down through multiple layers of components, it can result in the accumulation of unnecessary or irrelevant props in components that don't actually need them. This can make the code more complex and harder to maintain.

2. Tight coupling: 

Passing down props through multiple layers of components can lead to tight coupling between components. If a parent component needs to be modified, it may require changes to be made in all the child components that rely on its props. This can make it harder to refactor or modify the code in the future.

3. Performance: 

Passing down props through multiple layers of components can affect the performance of the application. If the application has a large component tree with many nested components, it can slow down the rendering process and affect the user experience.

To overcome these drawbacks, alternative state management solutions such as **context, Redux, or GraphQL** can be used to manage the state and data more efficiently and avoid excessive props drilling.

### Example 2: With Usecontext hook and Context API

The problem with Prop Drilling is that whenever data from the Parent component will be needed, it would have to come from each level, Regardless of the fact that it is not needed there and simply needed in last.

A better alternative to this is using useContext hook. The useContext hook is based on Context API and works on the mechanism of Provider and Consumer. Provider needs to wrap components inside Provider Components in which data have to be consumed. Then in those components, using the useContext hook that data needs to be consumed.

// App.js

```javascript
import Parent from "./woUsecontext/Parent";
  
const App=()=> {
  return (
    <div className="App">
      <Parent />
    </div>
  );
}
export default App
```
//Parent.js

```javascript
import React, { useState, useContext } from "react";

let context = React.createContext(null);
function Parent() {
const [fName, setfName] = useState("SP");
const [lName, setlName] = useState("Acharya");
return (
	<context.Provider value={{ fName, lName }}>
	<div>This is a Parent component</div>
	<br />
	<ChildA />
	</context.Provider>
);
}

function ChildA() {
return (
	<>
	This is ChildA Component.
	<br />
	<ChildB />
	</>
);
}

function ChildB() {
return (
	<>
	This is ChildB Component.
	<br />
	<ChildC />
	</>
);
}

function ChildC() {
const { fName, lName } = useContext(context);
return (
	<>
	This is ChildC component.
	<br />
	<h3> Data from Parent component is as follows:</h3>
	<h4>{fName}</h4>
	<h4>{lName}</h4>
	</>
);
}

export default Parent;
```
![Alt text](a.png)

Same output but this time instead of passing data through each level, It is directly consumed in the component required using useContext Hook.


## Dynamic Context Example 

**->** Here we are taking one simple example where in dynamic context we are using some movie names , images and rating.



//MovieContext.js

```javascript
import React from 'react';

const MovieContext = React.createContext();

export default MovieContext;
```
//MovieProvider.js

```javascript
import React, { useState } from 'react';
import MovieContext from './MovieContext';

const MovieProvider = (props) => {
  const [movies, setMovies] = useState([
    { name: "The Shawshank Redemption", image: "shawshank.jpg", rating: 9.3 },
    { name: "The Godfather", image: "godfather.jpg", rating: 9.2 },
    { name: "The Dark Knight", image: "darkknight.jpg", rating: 9.0 }
  ]);

  return (
    <MovieContext.Provider value={{ movies }}>
      {props.children}
    </MovieContext.Provider>
  );
}

export default MovieProvider;
```
//MovieList.js

```javascript
import React, { useContext } from 'react';
import MovieContext from './MovieContext';

const MovieList = () => {
  const { movies } = useContext(MovieContext);

  return (
    <div>
      {movies.map(movie => (
        <div key={movie.name}>
          <img src={movie.image} alt={movie.name} />
          <h2>{movie.name}</h2>
          <p>Rating: {movie.rating}</p>
        </div>
      ))}
    </div>
  );
}

export default MovieList;
```
//App.js

```javascript
import React from 'react';
import MovieProvider from './MovieProvider';
import MovieList from './MovieList';

const App = () => {
  return (
    <MovieProvider>
      <MovieList />
    </MovieProvider>
  );
}

export default App;
```

Output:

![movies](b.png)

In this example, we create a separate file for each component.

The `MovieContext` component is responsible for creating the context object using the `React.createContext()` method.

The `MovieProvider` component defines the state variable movies and passes it down to its children components through the context object using the `MovieContext.Provider` component.

The `MovieList` component retrieves the movies data from the context object using the `useContext()` hook and maps over the array to render a list of movie items.

Finally, the App component renders the MovieProvider component as a parent of the MovieList component, so that the MovieList component can access the movies data from the context object.


# Axio Vs Fetch

**Axios :**

* Axios is a Javascript library used to make HTTP requests from node.js or XMLHttpRequests from the browser and it supports the Promise API that is native to JS ES6. 
* It can be used intercept HTTP requests and responses and enables client-side protection against XSRF. It also has the ability to cancel requests.   EX: axios.get('url') .then((response) => 

**Fetch:**

* The Fetch API provides a fetch() method defined on the window object. It also provides a JavaScript interface for accessing and manipulating parts of the HTTP pipeline (requests and responses). 
* The fetch method has one mandatory argument- the URL of the resource to be fetched. This method returns a Promise that can be used to retrieve the response of the request. EX:: fetch('path-to-the-resource-to-be-fetched') .then((response) => { 
  
  
  
|Axios |Fetch|
|:-----|:----|
|Axios has url in request object. |Fetch has no url in request object.|
|Axios is a stand-alone third party package that can be easily installed.| Fetch is built into most modern browsers; no installation is required as such.|
|Axios enjoys built-in XSRF protection.| Fetch does not. |
|Axios uses the data property. |Fetch uses the body property. |
|Axios’ data contains the object.| Fetch’s body has to be stringified.|
|Axios request is ok when status is 200 and statusText is ‘OK’. |Fetch request is ok when response object contains the ok property. |
|Axios performs automatic transforms of JSON data. |Fetch is a two-step process when handling JSON data- first, to make the actual request; second, to call the .json() method on the response. |
|Axios allows cancelling request and request timeout.| Fetch does not.|
|Axios has the ability to intercept HTTP requests. |Fetch, by default, doesn’t provide a way to intercept requests. |
|Axios has built-in support for download progress. |Fetch does not support upload progress.|


### axios and fetch are both used for making HTTP requests to servers, but they have some differences. Here are some of the main differences:

1. **Syntax:** axios uses a simple syntax and provides a higher level of abstraction over the XMLHttpRequest object. On the other hand, fetch uses a lower-level syntax and requires more configuration to use effectively.

2. **Error Handling:** axios handles errors better than fetch. In axios, any response code that falls outside the range of 2xx will trigger an error, which can be easily handled using a catch block. In fetch, a response with a 404 or 500 status code will still resolve successfully, requiring additional checking of the response status.

3. **Cross-Origin Requests:** axios automatically includes credentials and headers for cross-origin requests, whereas with fetch you need to manually set the mode and credentials to include.

Here's an example of how to use `axios` to make a GET request:

```javascript
import axios from 'axios';

axios.get('https://jsonplaceholder.typicode.com/todos/1')
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.log(error);
  });
```

And here's an example of how to use `fetch` to make a GET request:

```javascript
fetch('https://jsonplaceholder.typicode.com/todos/1')
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    return response.json();
  })
  .then(data => {
    console.log(data);
  })
  .catch(error => {
    console.log(error);
  });
```
As you can see, the axios code is simpler and easier to read, and the error handling is more straightforward. The fetch code requires additional error checking and handling, making it slightly more complex.


### **Q. What is HTTP ?**
HTTP (Hypertext Transfer Protocol) is a protocol that is used to transfer hypertext from client end to server end .

**What are HTTP request Methods ?**
* Get: This method retrieves information from a given server using a given URL
* Post: Post method sends the data to server Example: need to update the phone number of user we will use post method
* Put: It is used to replace all current representations of target resources with uploaded content
* Delete: It is used to remove all the current representations of the target resource which is given by URL


## Lazy Loading

Lazy loading in React is a technique that allows developers to defer loading certain components or resources until they are actually needed. This can help reduce the initial load time of a web page or application, as well as improve performance by only loading the necessary components when they are required.

**Advantages of Lazy Loading** 

* Reduces initial loading time by reducing the bundle size.
* Reduces browser workload.
* Improves application performance in low bandwidth situations.
* Improves user experience at initial loading.
* Optimizes resource usage.

**Disadvantages of Lazy Loading**

* Not suitable for small-scale applications.
* Placeholders can slow down quick scrolling.
* Requires additional communication with the server to fetch resources.
* Can affect SEO and ranking.

To perform lazy loading in React, there are a few different methods you can use depending on your specific needs:

**React.lazy() function:-** This method allows you to lazily load a component. You can use this function to load a component asynchronously when it is needed by the application. 

Here's an example:
```javascript
const MyComponent = React.lazy(() => import('./MyComponent'));
```

**React.Suspense component:-** This method allows you to specify a fallback component while the lazily loaded component is being loaded. 

Here's an example:
```javascript
import React, { Suspense } from 'react';

const MyComponent = React.lazy(() => import('./MyComponent'));

function App() {
  return (
    <div>
      <Suspense fallback={<div>Loading...</div>}>
        <MyComponent />
      </Suspense>
    </div>
  );
}
```
In this example, the` <Suspense>` component is used to wrap the `<MyComponent>` component, and the fallback prop specifies the component to render while the `<MyComponent>` component is being loaded.

**React Loadable library:-** This is a third-party library that allows you to perform more advanced lazy loading, such as loading multiple components at once or specifying custom loading indicators. 

Here's an example:
```javascript
import Loadable from 'react-loadable';

const LoadableMyComponent = Loadable({
  loader: () => import('./MyComponent'),
  loading: () => <div>Loading...</div>,
});

function App() {
  return (
    <div>
      <LoadableMyComponent />
    </div>
  );
}
```
In this example, the Loadable function is used to lazily load the `<MyComponent>` component, and the loading prop specifies the component to render while it is being loaded.


## Memory Leak

In React, a memory leak can occur when a component allocates memory and fails to release it after it's no longer needed. This can lead to an accumulation of unused memory, which can cause performance issues and even crash the application.

**Here are a few scenarios in which memory leaks can occur in React:**

1. **Improper use of state and props:** When a component's state or props are updated frequently, it can lead to a buildup of memory. For example, if a component has a setInterval() method that updates the state every second, the state object will keep growing, eventually leading to a memory leak.

2. **Event listeners:** When a component registers event listeners, such as mouse clicks or key presses, it can create a memory leak if it doesn't remove the listeners when the component is unmounted. This can cause the event listeners to accumulate, leading to memory issues.

3. **Improper use of useEffect():** The useEffect() hook is used to perform side effects in functional components. If the hook is not used correctly, it can lead to memory leaks. For example, if a component sets up a timer in useEffect() and doesn't clear it when the component unmounts, the timer will continue running, causing a memory leak.

**To prevent memory leaks in React, it's important to follow best practices, such as:**

* Use the useMemo() hook to memoize expensive calculations and prevent unnecessary re-renders.

* Use the useCallback() hook to memoize event handlers and prevent unnecessary re-renders.

* Use the useRef() hook to create references that persist across renders.

* Use the useEffect() hook to clean up any resources, such as event listeners or timers, when the component unmounts.

By following these best practices, you can prevent memory leaks in your React applications and ensure optimal performance.



# State Management

## The Four Kinds of React State to Manage :
When we talk about state in our applications, it’s important to be clear about what types of state actually matter.

There are four main types of state you need to properly manage in your React apps:

1. Local state
2. Global state
3. Server state
4. URL state



### **Local (UI) state** – 
* Local state is data we manage in one or another component.
* Local state is most often managed in React using the useState hook.
* For example, local state would be needed to show or hide a modal component or to track values for a form component, such as form submission, when the form is disabled and the values of a form’s inputs.

### **Global (UI) state** – 
* Global state is data we manage across multiple components.
* Global state is necessary when we want to get and update data anywhere in our app, or in multiple components at least.
* A common example of global state is authenticated user state. If a user is logged into our app, it is necessary to get and change their data throughout our application.
* Sometimes state we think should be local might become global.

### **Server state** – 
* Data that comes from an external server that must be integrated with our UI state.
* Server state is a simple concept, but can be hard to manage alongside all of our local and global UI state.
* There are several pieces of state that must be managed every time you fetch or update data from an external server, including loading and error state.
* Fortunately there are tools such as SWR and React Query that make managing server state much easier.

### **URL state** – 
* Data that exists on our URLs, including the pathname and query parameters.

* URL state is often missing as a category of state, but it is an important one.
* In many cases, a lot of major parts of our application rely upon accessing URL state. Try to imagine building a blog without being able to fetch a post based off of its slug or id that is located in the URL!


# **REDUX Toolkit**

Redux Toolkit is a set of libraries and tools that make it easier to manage state in React applications using Redux. 

It provides a simpler API for creating and managing Redux stores, includes helpful development tools, improves performance optimization, improves type safety, and provides a clear and consistent architecture for managing application state. 

Overall, Redux Toolkit helps streamline the development process and improve the performance, maintainability, and scalability of your React applications that use Redux.

Store:
The Redux store is the main, central bucket which stores all the states of an application. It should be considered and maintained as a single source of truth for the state of the application.

Action:
The only way to change the state is to emit an action, which is an object describing what happened

reducers:
Reducers, as the name suggests, take in two things: previous state and an action. Then they reduce it (read it return) to one entity: the new updated instance of state.

So reducers are basically pure JS functions which take in the previous state and an action and return the newly updated state.



> **Redux is a global state** 

> **You may need Redux if you don't want to do props drilling (passing props too deep).**


![redux](https://www.ceos3c.com/wp-content/uploads/2022/01/redux-toolkit-2.gif)

**Here are some advantages of using Redux Toolkit in React:**

I. Simplified Code:-

 Redux Toolkit provides a simplified API for creating and managing Redux stores. It also includes a number of utilities for common Redux tasks, such as creating reducers, handling asynchronous actions, and creating immutable state.

II. Improved Developer Experience:-

 Redux Toolkit comes with helpful development tools, including an integration with the Redux DevTools Extension, which makes it easier to debug and inspect the state of your application.

III. Performance Optimization: -

Redux Toolkit includes a utility called "createSlice" that automatically generates optimized Redux reducer functions based on the initial state and action types you provide. This can help improve performance by reducing the amount of unnecessary work done by your reducers.

IV. Improved Type Safety:-

 Redux Toolkit comes with built-in TypeScript types, which can help catch errors at compile time rather than runtime. This can improve the stability and maintainability of your codebase.

V. Scalability:-

 Redux Toolkit makes it easier to manage complex Redux applications by providing a clear and consistent architecture for managing application state. This can help you scale your application as it grows and becomes more complex.

### Data flow in Redux
Redux follows a unidirectional data flow. Redux has 3 major components: ‘actions’, ‘reducers’ and the ‘store’.
![redux dataflow](https://www.eternussolutions.com/wp-content/uploads/2020/12/redux-2.png)



Here is a simple example of how to implement and what are ther step of redux.

**->** Firstly Install the required packages:-

  Install the redux and react-redux packages along with redux-toolkit package in your React application using npm.
```javascript
npm install redux react-redux @reduxjs/toolkit
```


**->** **react Redux reducers:-**

 Create your reducers using the `createSlice` function provided by Redux Toolkit. This function generates a `reducer` function for you, based on the initial state and the actions you define.


// countSlice.js
```javascript
import { createSlice } from '@reduxjs/toolkit';

const initialState = 0;

const countSlice = createSlice({
  name: 'count',
  initialState,
  reducers: {
    add: (state, { payload }) => state += payload,
    reset: (state) => state = initialState
  }
});

export const { add, reset } = countSlice.actions;
export default countSlice.reducer;
```
const countSlice = createSlice({...}): This line uses the `createSlice` function to define a new slice of the store called "count". The `createSlice` function takes an object with several properties:

~name: A string name for the slice.

~initialState: The initial state of the slice.

~reducers: An object with functions that define how the slice should respond to actions that are dispatched to the store.
reducers: {...}: This section defines the two reducers for the "count" slice:

~ add: This reducer takes the current state and a `payload` argument (which is the value passed to the action) and returns a new state with the `payload` value added to it.

> **Payload:-** While action types allow you tell your reducer what action it should take, the payload is the data that your reducer will use to update the state. This lesson shows you how to pass an action payload along with your action type to update the state.

~ reset: This reducer takes the current state and sets it back to the initial state.

~ *export const { add, reset } = countSlice.actions;*

 This line exports the add and reset action creators from the "count" slice. These action creators are functions that return action objects with a type property and a payload property (if applicable).

~ *export default countSlice.reducer;:-*
 This line exports the "count" slice's reducer function, which takes the current state and an action object and returns the new state.


**->** **Create a Redux store:-**

 In your store.js file, create a Redux store using the `configureStore` function provided by Redux Toolkit. This function takes an object with a reducer property and an optional middleware property.

 > **configureStore** is only accepting one parameter, which is an Object, which is called ConfigureStoreOptions.

// store.js
```javascript
import { configureStore } from '@reduxjs/toolkit';
import countReducer from './countSlice';

const store = configureStore({
  reducer: {
    count: countReducer
  }
});

export default store;
```
import countReducer from './countSlice';: This line imports the "count" slice's reducer function from the countSlice.js file.

*const store = configureStore({...}):-*

 This line uses the `configureStore` function to create a new Redux store. The `configureStore` function takes an object with several properties:

> **reducer**: An object with key-value pairs where the keys are the names of the slices in the store and the values are the reducer functions for those slices.

reducer: {...}: This section defines the reducers for the store. In this case, there is only one slice called "count", so the `countReducer` function is associated with it.

**->** **This code sets up the Redux store for use in the React app:**

 In index.js file, import Provider from react-redux. The Provider component from the react-redux library is used to provide the Redux store to the app. The store object is imported from the ./store file.

// index.js
```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';

import { Provider } from 'react-redux';
import store from './store';

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById('root')
);
```

**->** **Connect Redux to React components:**

 Use the `useSelector` and `useDispatch` hooks provided by the react-redux package to connect your React components to the Redux store.

// App.js
```javascript
import { useDispatch, useSelector } from "react-redux";
import { add, reset } from "./countSlice";

function App() {
  const dispatch = useDispatch();
  const { count } = useSelector(state => state);

  function addOneToCount() {
    dispatch(add(1));
  }

  function resetCount() {
    dispatch(reset());
  }

  return (
    <div>
      Count: {count}
      <button onClick={addOneToCount}>
        +1
      </button>
      <button onClick={resetCount}>
        RESET
      </button>
    </div>
  )
}

export default App
```

Output:
![redux](./image%20(12).png)

This code defines the App component, which displays the current count and two buttons to add to the count and reset it. The `useSelector` hook is used to extract the count state from the Redux store. The `useDispatch` hook is used to dispatch the add and reset actions to modify the count state.

> **useSelector:** 
* useSelector and useDispatch are two hooks provided by the react-redux library that are commonly used in conjunction with Redux Toolkit to manage state in a React application.
* useSelector is used to select data from the Redux store. It takes a function as an argument that defines how to extract the data from the store, and returns the selected data.

>**useDispatch:** 
* useDispatch is used to dispatch actions to the Redux store. It returns a reference to the dispatch function.
* if we want to modify the global state we need to useDispatch and the action that we already created in slice.


### Summary:
we have 6 steps to implement the Redux Toolkit to our react project:

* Install Redux Toolkit and React-Redux Packages
* Create a Redux Store
* Include the Redux Store to App.js parent
* Create a Redux State Slice
* Add Slice Reducers to the Store
* Implementing useSelector and useDispatch in React Components


## CURD operation in Redux

Here's a simple example of how to perform CRUD operations in Redux using a simple counter app.



**First, let's define the Redux store with an initial state of 0:**

```javascript
import { createStore } from 'redux';

const store = createStore(counterReducer);

export default store;


const initialState = {
  count: 0
};

const counterReducer = (state = initialState, action) => {
  switch (action.type) {
    case 'INCREMENT':
      return { ...state, count: state.count + 1 };
    case 'DECREMENT':
      return { ...state, count: state.count - 1 };
    case 'RESET':
      return { ...state, count: 0 };
    default:
      return state;
  }
};


```
In this example, we define a simple reducer that handles three actions: INCREMENT, DECREMENT, and RESET. The INCREMENT and DECREMENT actions modify the count property of the state by incrementing or decrementing it by 1, while the RESET action resets the count property to 0.

**->** Now that we have our store, let's define our CRUD operations. In this example, we will perform the following operations:

* Create: Set the counter to a specific value
* Read: Get the current value of the counter
* Update: Increment or decrement the counter by 1
* Delete: Not applicable to this app

**Next, let's create three action creators to handle the three actions:**

```javascript
export const increment = () => {
  return {
    type: 'INCREMENT'
  };
};

export const decrement = () => {
  return {
    type: 'DECREMENT'
  };
};

export const reset = () => {
  return {
    type: 'RESET'
  };
};
```
These action creators simply return an object with a type property that corresponds to the action type.

**Now, let's create a simple React component that displays the current count and allows the user to perform CRUD operations on it:**

```javascript
import React from 'react';
import { useSelector, useDispatch } from 'react-redux';
import { increment, decrement, reset } from './actions';

const Counter = () => {
  const count = useSelector(state => state.count);
  const dispatch = useDispatch();

  return (
    <div>
      <h1>Counter: {count}</h1>
      <button onClick={() => dispatch(increment())}>Increment</button>
      <button onClick={() => dispatch(decrement())}>Decrement</button>
      <button onClick={() => dispatch(reset())}>Reset</button>
    </div>
  );
};

export default Counter;
```
In this example, we use the `useSelector` hook to retrieve the count property from the Redux store, and the `useDispatch` hook to dispatch the increment, decrement, and reset actions.

The component simply displays the current count and provides buttons to increment, decrement, and reset the count.

And that's it! With this simple example, we can see how to perform CRUD operations in Redux using a simple counter app.



## Redux Thunk:

* The most common use case for Redux Thunk is for communicating asynchronously with an external API to retrieve or save data. Redux Thunk makes it easy to dispatch actions that follow the lifecycle of a request to an external API.

* Redux Thunk is middleware that allows you to return functions, rather than just actions, within Redux. This allows for delayed actions, including working with promises.

* One of the main use cases for this middleware is for handling actions that might not be synchronous, for example, using axios to send a GET request. 

* Redux Thunk allows us to dispatch those actions asynchronously and resolve each promise that gets returned.

### Example:
Suppose you have an application that needs to fetch data from an API and display it in the UI. You can use Redux-thunk to handle asynchronous actions in Redux.

First, you would define your Redux store with the redux-thunk middleware:

```javascript
import { createStore, applyMiddleware } from 'redux';
import thunk from 'redux-thunk';
import rootReducer from './reducers';

const store = createStore(
  rootReducer,
  applyMiddleware(thunk)
);
export default store
```
Next, you would create an action creator that makes an API request and dispatches actions to update the Redux store:

```javascript
import axios from 'axios';

export const fetchPosts = () => {
  return (dispatch) => {
    dispatch({ type: 'FETCH_POSTS_REQUEST' });
    axios.get('https://jsonplaceholder.typicode.com/posts')
      .then(response => {
        const posts = response.data;
        dispatch({ type: 'FETCH_POSTS_SUCCESS', payload: posts });
      })
      .catch(error => {
        dispatch({ type: 'FETCH_POSTS_FAILURE', error });
      });
  };
};
```
In this example, `fetchPosts` is a `thunk` action creator that returns a function instead of an object. The function takes `dispatch` as an argument, which allows it to dispatch multiple actions.

When `fetchPosts` is called, it dispatches a **FETCH_POSTS_REQUEST** action to indicate that the API request is starting. It then makes an API request using the axios library. When the request is successful, it dispatches a **FETCH_POSTS_SUCCESS** action with the response data as the payload. If the request fails, it dispatches a **FETCH_POSTS_FAILURE** action with the error object.

Finally, you would use this action creator in your component to fetch the data and update the Redux store:

```javascript
import React, { useEffect } from 'react';
import { useDispatch, useSelector } from 'react-redux';
import { fetchPosts } from './actions';

const Posts = () => {
  const dispatch = useDispatch();
  const posts = useSelector(state => state.posts);
  const isLoading = useSelector(state => state.isLoading);

  useEffect(() => {
    dispatch(fetchPosts());
  }, [dispatch]);

  if (isLoading) {
    return <div>Loading...</div>;
  }

  return (
    <div>
      {posts.map(post => (
        <div key={post.id}>
          <h2>{post.title}</h2>
          <p>{post.body}</p>
        </div>
      ))}
    </div>
  );
};

export default Posts;
```
In this example, the Posts component uses the `useDispatch` and `useSelector` hooks from the react-redux library to interact with the Redux store. It dispatches the `fetchPosts` action when the component mounts using the `useEffect` hook. It also uses the `isLoading` state to show a loading indicator while the API request is in progress. Once the request is complete, it displays the fetched data in the UI.

That's a simple example of how Redux-thunk can be used to handle asynchronous actions in Redux.

## Thunk Vs Saga

Saga middleware is a library for handling side effects in React applications using Redux. Side effects are any operations that are not pure functions, such as making API calls, accessing browser storage, or handling asynchronous code. These effects can be difficult to manage in Redux, and Saga provides a way to handle them in a declarative and testable way.

|Redux-Thunk |	Redux-Saga |
|:-----------|:------------|
|Less boilerplate code|	More boilerplate code|
|Easy to understand as compared to redux-saga|	Difficult to understand as there are multiple concepts to learn like generator functions and redux-saga effects|
|May be difficult to scale up	|Easy to scale as compared to redux-thunk|
|Action creators may hold too much async logic	|Action creators stay pure|
|May get difficult to test|	Comparatively easy to test as all your async logic remains together|

> In summary, Thunk is a simple and lightweight library that is good for handling basic asynchronous operations, while Saga is a more powerful and flexible library that can handle more complex async scenarios.


**Thunk example:**

Let's say we have a todo list application, and we want to fetch the list of todos from an API endpoint when the application starts. Here's how we could do it with a thunk:

// actions.js

```javascript
import axios from 'axios';

export const fetchTodos = () => {
  return dispatch => {
    dispatch({ type: 'FETCH_TODOS_REQUEST' });
    axios.get('/api/todos')
      .then(response => {
        dispatch({ type: 'FETCH_TODOS_SUCCESS', payload: response.data });
      })
      .catch(error => {
        dispatch({ type: 'FETCH_TODOS_FAILURE', payload: error });
      });
  };
};
```

// reducer.js
```javascript
const initialState = {
  todos: [],
  loading: false,
  error: null
};

const reducer = (state = initialState, action) => {
  switch (action.type) {
    case 'FETCH_TODOS_REQUEST':
      return { ...state, loading: true };
    case 'FETCH_TODOS_SUCCESS':
      return { ...state, todos: action.payload, loading: false };
    case 'FETCH_TODOS_FAILURE':
      return { ...state, error: action.payload, loading: false };
    default:
      return state;
  }
};
```
In this example, we define a fetchTodos action creator that returns a function (i.e., a thunk) that dispatches multiple actions in response to the async operation. The first action dispatched indicates that the request is being made, and the second action is dispatched if the request is successful, passing the fetched data as payload. If the request fails, the third action is dispatched with the error as payload. The reducer handles these actions and updates the state accordingly.

**Saga example:**

Let's say we want to implement a feature that allows users to search for todos by keyword. Here's how we could do it with a saga:

// actions.js

```javascript
export const searchTodos = keyword => {
  return { type: 'SEARCH_TODOS_REQUEST', payload: keyword };
};

export const searchTodosSuccess = results => {
  return { type: 'SEARCH_TODOS_SUCCESS', payload: results };
};

export const searchTodosFailure = error => {
  return { type: 'SEARCH_TODOS_FAILURE', payload: error };
};
```

// sagas.js
```javascript
import { takeLatest, call, put } from 'redux-saga/effects';
import axios from 'axios';

function* searchTodosSaga(action) {
  try {
    const response = yield call(axios.get, '/api/todos', {
      params: { q: action.payload }
    });
    yield put(searchTodosSuccess(response.data));
  } catch (error) {
    yield put(searchTodosFailure(error));
  }
}

function* rootSaga() {
  yield takeLatest('SEARCH_TODOS_REQUEST', searchTodosSaga);
}

export default rootSaga;
```

// reducer.js
```javascript
const initialState = {
  todos: [],
  loading: false,
  error: null
};

const reducer = (state = initialState, action) => {
  switch (action.type) {
    case 'SEARCH_TODOS_REQUEST':
      return { ...state, loading: true };
    case 'SEARCH_TODOS_SUCCESS':
      return { ...state, todos: action.payload, loading: false };
    case 'SEARCH_TODOS_FAILURE':
      return { ...state, error: action.payload, loading: false };
    default:
      return state;
  }
};
```
In this example, we define a searchTodos action creator that takes a keyword as parameter and dispatches a SEARCH_TODOS_REQUEST action with the keyword as payload. 