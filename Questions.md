What is React?
----------------
React is an `open-source front-end JavaScript library` that is used for building user interfaces, especially for single-page applications. It is used for handling view layer for web and mobile apps.

What are the major features of React?
-------------------------------------
The major features of React are:

* It uses VirtualDOM instead of RealDOM considering that RealDOM manipulations are expensive.
* Supports server-side rendering.
* Follows Unidirectional data flow or data binding.
* Uses reusable/composable UI components to develop the view.

What is JSX?
------------
JSX is a XML-like syntax extension to ECMAScript (the acronym stands for JavaScript XML). Basically it just provides syntactic sugar for the React.createElement() function, giving us expressiveness of JavaScript along with HTML like template syntax.

In the example below text inside `<h1>` tag is returned as JavaScript function to the render function.

    class App extends React.Component {
      render() {
        return(
          <div>
            <h1>{'Welcome to React world!'}</h1>
          </div>
        )
      }
    }

How to create components in React?
---------------------------------
There are two possible ways to create a component.

<b>Function Components</b>: This is the simplest way to create a component. Those are pure JavaScript functions that accept props object as the first parameter and return React elements:

    function Greeting({ message }) {
      return <h1>{`Hello, ${message}`}</h1>

    }
    
<b>Class Components</b>: You can also use ES6 class to define a component. The above function component can be written as:

    class Greeting extends React.Component {
      render() {
        return <h1>{`Hello, ${this.props.message}`}</h1>
      }
    }

What is the difference between state and props?
-----------------------------------------------
* Both props and state are plain JavaScript objects.
* While both of them hold information that influences the output of render, they are different in their functionality with respect to component. 
* Props get passed to the component similar to function parameters whereas state is managed within the component similar to variables declared within a function.

what is the difference between element and component ?
------------------------------------------------------

An Element is a plain object describing what you want to appear on the screen in terms of the DOM nodes or other components. Elements can contain other Elements in their props. Creating a React element is cheap. Once an element is created, it is never mutated.

The object representation of React Element would be as follows:

    const element = React.createElement(
      'div',
      {id: 'login-btn'},
      'Login'
    )
    
The above React.createElement() function returns an object:

    {
      type: 'div',
      props: {
        children: 'Login',
        id: 'login-btn'
      }
    }
    
And finally it renders to the DOM using `ReactDOM.render()`:

    <div id='login-btn'>Login</div>
    
Whereas a component can be declared in several different ways. It can be a class with a render() method or it can be defined as a function. In either case, it takes props as an input, and returns a JSX tree as the output:

    const Button = ({ onLogin }) =>
      <div id={'login-btn'} onClick={onLogin}>Login</div>
      
Then JSX gets transpiled to a React.createElement() function tree:

    const Button = ({ onLogin }) => React.createElement(
      'div',
      { id: 'login-btn', onClick: onLogin },
      'Login'
    )
    
What is reconciliation?
----------------------
When a component's props or state change, React decides whether an actual DOM update is necessary by comparing the newly returned element with the previously rendered one. When they are not equal, React will update the DOM. This process is called reconciliation.


