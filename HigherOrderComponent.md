* A Higher order compoent(HOC) is an advanced technique in react for reusing component logic.
* HOC is a pure function with zero side effects and doesn't modify the input component.
* HOC is a function that takes a component and returns a new component.

![hoc](https://user-images.githubusercontent.com/40006634/172774011-6f5aae0d-5d2e-490b-9291-71598a6bb755.png)


App.js

    import React from 'react'
    import Hoc from './Hoc'

    const App = () => {
      return (
        <div>
          <h1>Welcome to User</h1>
        </div>
      )
    }

    export default Hoc(App)
    
    
Hoc.js

    import React from 'react'

    const Hoc = (Inputcomponent) => {
        return (
            class extends React.Component {
                state = {
                    auth: false
                }
                render() {
                    return (
                        <div>
                            {this.state.auth ? <Inputcomponent /> : <h1>Please Login</h1>}
                        </div>
                    )
                }
            }
        )
    }

    export default Hoc;
