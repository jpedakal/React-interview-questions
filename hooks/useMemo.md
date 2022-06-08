* useMemo hook help us to improve the performance of an application when we are performing most expensive operation.
* useMemo will not run for every re-render happens.
* It will run during the first render and when its dependency value changes.

useEffect vs useMemo
--------------------
<b>useEffect</b>: useEffect will run after render of the component.

<b>useMemo</b>: useMemo will run during the render of the component.


      const App = ({ data }) => {
        const [num, setNum] = useState(0);
        const [digit, setDigit] = useState(5);

        const Fact = useMemo(() => factorial(digit), [digit]);

        return (
          <>
            <h3>Count: {num}</h3>
            <button onClick={() => setNum(num + 1)}>Num</button>
            <button onClick={() => setDigit(digit+1)}>Factorial</button>
            <h3>Factorial: {Fact}</h3>
          </>
        );
      };

      let output = 1;
      const factorial = (n) => {
        for (let i = n; i > 0; i--) {
          output *= i;
        }
        console.log("factorial is running");
        return output;
      };
      
      
      
* To fix this performance issue, we can use the useMemo Hook to memoize the factorial function. 
* This will cause the function to only run when needed.
* We can wrap the factorial function call with useMemo.
* The useMemoHook accepts a second parameter to declare dependencies. The factorial function will only run when its dependencies have changed.


