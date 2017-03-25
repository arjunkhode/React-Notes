# React basics

## Structure of Files

We first have `Package.json` which defines all the dependencies of React.

We can `npm install` the package.json file to install all the necessary components for React.

For React apps, we need index.html as usual, it is placed in the `public` folder.

We have `src` folder as a sibling of `public` folder.

`src` contains index.js file, which is the main JavaScript file for react.
`src` additionally contains the `components` folder, which contains all the .js files for our components.

## Components

Components are the building blocks of a React app.
A component is a single DOM element or it could be a group of DOM elements.
Take Spotify for example, if Spotify were made in React, each song would be a component, the search bar would be a component, the menu on the left would be a component as well as the entire display on the right could be one component. And finally, the entire window would be one component. Components can be nested.

Every component in React can be rendered.
When we render a component, it is displayed in whichever element it is rendered.
So to think of it, we always have one 'root' element in our index.html. 
This root is defined as a component in our js file and `<Root/>` is rendered in the 'main' element in HTML.

In our Index.js file:
```
	render(<Root/>, document.querySelector('#main'));
```
This renders the Root component in the div with the id of main in index.html

## Functional Vs Class based Components

Components can be simple JavaScript functions. These are called functional components. Also, they don't care about lifecycle methods or have their own internal state.

```
	function Welcome() {
		return(Hello!);
	}
```

Components can also be ES6 classes. These are called class based components.

```
class Welcome extends React.Component{
	render(){
		return(
			Hello!
			);
	}
}
```

Class based components have extra features, like STATE. Every class based component has a STATE.

## Import and Export

We can import components using ES6.

This can be done as follows:

```
import React from 'react';
import Welcome from './components/welcome';
```

Notice how we do not need to mention the extension of the file in the single quotes.

Here, React and Welcome are components, or 'ES6 Modules'.

We can export components using the export keyword. We add the export statement at the end of the Welcome.js file:

```
function Welcome() {
	return(Hello!);
}

export default Welcome;
```

Once a component is exported, it can be imported by other components.

## Props

Conceptually, components accept arbitrary inputs (called "props") and return React elements describing what should appear on the screen.

Think of props like attributes to our custom made HTML tags. For example, if we have a Welcome component, it can be used in JSX as follows:

```
<Welcome prop1="This is a prop" />
```

Here, Welcome is a component and prop1 is the prop. We can store data in props and pass them to other components inside our React.js code.

Props can be passed in functional components as follows:

```
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```	

Props can be passed in class based components using an additional keyword `this`:

```
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

## State

* STATE is an object used to record and react to events

* Each class based component has state

* Everytime state is changed, render() is run again.

STATE must be initialized in constructor

Remember to pass props as argument to the constructor and to super

then define a state

```
this.state = {key: value};
```

Functional components do not have STATE

* In the render, say there is an input element

* we can put an event on it like ‘onChange’

```
onChange = {(event) => {this.setState(key: event.target.value) }}
```

* Thus, on every onChange in the input, the ‘this.state.term’ will be updated with the value inside the input box

* setState() tells react that the value has changed

* we can reference this state variable in JSX
```
Value of input : {this.state.key}
```

## Props Vs State

Props are immutable. State can be changed.

Functional components can have props, state is only had by class based components.
