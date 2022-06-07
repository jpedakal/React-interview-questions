* The React useState Hook allows us to track state in a function component.
* State generally refers to data or properties that need to be tracking in an application.
* The useState Hook can be used to keep track of strings, numbers, booleans, arrays, objects, and any combination of these!
* Do not call Hooks inside loops, conditions, or nested functions. Hooks should always be used at the top level of the React functions. This rule ensures that Hooks are called in the same order each time a components renders.
* You cannot call Hooks from regular JavaScript functions. Instead, you can call Hooks from React function components. Hooks can also be called from custom Hooks.


      import { useState } from "react";
      import ReactDOM from "react-dom/client";
      function FavoriteColor() {
        const [color, setColor] = useState("red");

        return (
          <>
            <h1>My favorite color is {color}!</h1>
            <button
              type="button"
              onClick={() => setColor("blue")}
            >Blue</button>
          </>
        )
      }

      const root = ReactDOM.createRoot(document.getElementById('root'));
      root.render(<FavoriteColor />);
      
      
