The useCallback and useMemo Hooks are similar. The main difference is that useMemo returns a memoized value and useCallback returns a memoized function.
The React useCallback Hook returns a memoized callback function.


App.js


      import { useCallback, useReducer, useState } from "react";
      import Title from "./Title";
      import Agec from "./Agec";
      import Salaries from "./Salaries";

      function App() {
        const [age, setAge] = useState(25);
        const [salary, setSalary] = useState(10000);

        const incrementAge = useCallback(() => {
          setAge(age + 1)
        }, [age])

        const incrementSalary = useCallback(() => {
          setSalary(salary + 1000);
        }, [salary])

        return (
          <>
            <center>
              <Title />
              <Agec text='Age' value={age} />
              <button onClick={incrementAge}>Increment Age</button>
              <Salaries text='Salary' value={salary} />
              <button onClick={incrementSalary}>Increment Salary</button>
            </center>
          </>
        )
      }


      export default App;
      
     
Title.js


    import React from 'react'

    const Title = () => {
        console.log('Title')
        return (
            <div>
                <h3>Title</h3>
            </div>
        )
    }

    export default React.memo(Title);
    
    
Agec.js

    import React from 'react'

    const Agec = ({ text, value }) => {
        console.log('Age component');
        return (
            <div>
                <h2>{text}-{value}</h2>
            </div>
        )
    }

    export default React.memo(Agec);
    
 
salaries.js

    import React from 'react'

    const Salaries = ({ text, value }) => {
        console.log('Salary component');
        return (
            <div>
                <h3>{text} -{value}</h3>
            </div>
        )
    }

    export default React.memo(Salaries)


