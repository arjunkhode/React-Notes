# React basics

## Components

Components are the building blocks of a React app.
A component is a single DOM element or it could be a group of DOM elements.
Take spotify for example, if Spotify were made in React, each song would be a component, the search bar would be a component, the menu on the left would be a component as well as the entire display on the right could be one component. And finally, the entire window would be one component.

Every component in React can be rendered.
When we render a component, it is displayed in whichever element it is rendered.
So to think of it, we always have one 'root' element in our index.html. 
This root is defined as a component in our js file and <Root/> is rendered in the 'main' element in HTML.

	In our Index.js file:
	```
		render(<Root/>, document.querySelector('#main'));
	```

## Functional Vs Class based Components

Components can be simple JavaScript functions.

	```
		function Welcome() {
			return(Hello!);
		}
	```
Everything inside the return function is JSX. JSX is used to write HTML making use of just JavaScript.

Components can also be ES6 classes.

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

## Props

Conceptually, components accept arbitrary inputs (called "props") and return React elements describing what should appear on the screen.

Think of props like attributes to our custom made HTML tags that go by the name of our components. For example, if we have a Welcome component, it can be used in JSX as follows:
	
	```
	<Welcome prop1="This is a prop" />
	```

Here, Welcome is a component and prop1 is the prop.

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