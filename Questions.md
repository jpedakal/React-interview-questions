What is React?
----------------
React is an open-source front-end JavaScript library that is used for building user interfaces, especially for single-page applications. It is used for handling view layer for web and mobile apps.

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
