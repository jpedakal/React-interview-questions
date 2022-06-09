<b>Controlled component</b>
Element data can be controlled by parent component through callbacks like onChange()

<b>Uncontrolled component</b>
Element's data can be controlled by the DOM itself.


Controlled component Example:
-----------------------------

App.js

    import React from 'react'
    import Controlled from './Controlled'

    const App = () => {
      return (
        <div>
          <Controlled />
        </div>
      )
    }

    export default App;
    
    
Controlled.js

    import React, { useState } from 'react'
    import Test from './Test';

    const Controlled = () => {
        const [num, setNum] = useState(10);

        const handleChange = (e) => {
            setNum(e.target.value)
        }

        return (
            <div>
                <center>
                    num: {num}<br />
                    <input type='text' onChange={handleChange} />
                    <Test data={handleChange} />
                </center>
            </div>
        )
    }

    export default Controlled;

Test.js

    import React from 'react'

    const Test = (props) => {
      return (
        <div>
            <input type='text' onChange={props.data}  />
        </div>
      )
    }

    export default Test
