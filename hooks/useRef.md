* In general, we want to let React handle all DOM manipulation.
* But there are some instances where useRef can be used without causing issues.

In React, we can add a ref attribute to an element to access it directly in the DOM.

    function App() {
      const data = useRef(null);
      function submitHandler(e){
        e.preventDefault();
        console.log(data.current.value)
      }
      return (
        <>
          <center>
            <form onSubmit={submitHandler} >
              <input ref={data} type="text" placeholder="Enter your name" />
              <br />
              <input type="submit" />
            </form>
          </center>
        </>
      );
    }


Use useRef to focus the input:

      const App = () => {
        const data = useRef(null);

        const submitHandler = (e) => {
          e.preventDefault();
        };

        useEffect(() => {
          data.current.focus();
        });

        return (
          <div>
            <center>
              <form onSubmit={submitHandler}>
                <input ref={data} type="text" placeholder="Enter name" />
                <br />
                <input type="submit" />
              </form>
            </center>
          </div>
        );
      };
