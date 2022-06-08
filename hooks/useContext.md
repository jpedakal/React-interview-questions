* React Context is a way to manage state globally.
* It can be used together with the useState Hook to share state between deeply nested components more easily than with useState alone.

<b>The Problem</b>
* State should be held by the highest parent component in the stack that requires access to the state.
* To illustrate, we have many nested components. The component at the top and bottom of the stack need access to the state.
* To do this without Context, we will need to pass the state as "props" through each nested component. This is called "prop drilling".

<b>The Solution</b>
* The solution is to create context.
* To create context, you must Import `createContext` and initialize it:
* Next we'll use the Context Provider to wrap the tree of components that need the state Context.
* Wrap child components in the `Context Provider` and supply the state value.
* Now, all components in this tree will have access to the user Context.


        import { useState, createContext, useContext } from "react";
        const userContext = createContext();

        function App() {
          const [user, setUser] = useState('Krishna');
          return (
            <userContext.Provider value={user}>
              <h1>Hello {user}</h1>
              <Component1 />
            </userContext.Provider>
          )
        }

        function Component1() {
          return (
            <>
              <h1>Component1</h1>
              <Component2 />
            </>
          )
        }

        function Component2() {
          return (
            <>
              <h1>Component2</h1>
              <Component3 />
            </>
          )
        }

        function Component3() {
          return (
            <>
              <h1>Component3</h1>
              <Component4 />
            </>
          )
        }

        function Component4() {
          const user = useContext(userContext)
          return (
            <>
              <h1>Hello {user} again</h1>
            </>
          )
        }

        export default App;
        
        
output will be

      Hello Krishna
      Component1
      Component2
      Component3
      Hello Krishna again
