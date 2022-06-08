* useReducer -> use to store state values to local const variable.
* The useReducer Hook is similar to the useState Hook.
* It allows for custom state logic.
* If you find yourself keeping track of multiple pieces of state that rely on complex logic, useReducer may be useful.
* The useReducer Hook accepts two arguments.

syntax

    useReducer(<reducer>, <initialState>)
    
* The reducer function contains your custom state logic and the initialState can be a simple value but generally will contain an object.
* The useReducer Hook returns the current state and a dispatch method.

Example

      import { useReducer } from "react";

      const initialState = { count: 0 };

      function reducer(state, action) {
        switch (action.type) {
          case 'INCREMENT':
            return { count: state.count + 1 }
          case 'DECREMENT':
            return { count: state.count - 1 }
          default:
            return state;
        }
      }

      function App() {
        const [state, dispatch] = useReducer(reducer, initialState);
        return (
          <>
            Count: {state.count}
            <button onClick={() => dispatch({ type: 'DECREMENT' })} >-</button>
            <button onClick={() => dispatch({ type: 'INCREMENT' })} >+</button>
          </>
        )
      }


      export default App;



