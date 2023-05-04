Q1. What is index pagination?
--> Pagination in React JS is a function of apps that allows them to show data on a series of pages rather than showing on same page. The pagination is very usefull in case where a large data set might not fit into the provided space to render on screen.

Q2. Difference between let var const?

```
var- The scope of a var variable is functional scope.
     It can be updated and re-declared into the scope.
     It can be declared without initialization.
     It can be accessed without initialization as its default value is “undefined”.
     hoisting done, with initializing as ‘default’ value
let- The scope of a let variable is block scope.
     It can be updated but cannot be re-declared into the scope.
     It can be declared without initialization.
     It cannot be accessed without initialization otherwise it will give ‘referenceError’.
     Hoisting is done, but not initialized (this is the reason for the error when we access the let variable before declaration initialization)
const - The scope of a const variable is block scope.
     It cannot be updated or re-declared into the scope.
     It cannot be declared without initialization.
     It cannot be accessed without initialization, as it cannot be declared without initialization.
     Hoisting is done, but not initialized (this is the reason for error when we access the const variable before declaration/initialization)

```

Q3. Print numbers from 1 to 5 after some time like after 1s 1 ,2s 2..

```js
const print = (i) => {
  setTimeout(() => {
    console.log(i);
  }, 1000 * i);
};

for (let i = 1; i < 4; i++) {
  print(i);
}
```

Q4 Explain Jwt token authentication system.
-->
JWT, or JSON Web Token, is an open standard used to share information between two parties securely — a client and a server. In most cases, it’s an encoded JSON containing a set of claims and a signature. It’s usually used in the context of other authentication mechanisms like OAuth, OpenID to share user-related information. It’s also a popular way to authenticate/authorize users in a microservice architecture.

Q5 Explain Login logout system
-->
During login -> We need to compaire the user password with the pass in database if the data is correct then we will send a token to client and will store that token in localstorage

```js
//Frontend
const onClickSignIn = () => {
  axios
    .post("#urltoBackend", {
      User: UserDetails,
    })
    .then((response) => {
      toast.success("🦄 Login successful");
      localStorage.setItem("Token", JSON.stringify(response.data.token));
      navigate("/user/profile");
    })
    .catch((error) => {
      console.log(error);
      toast.error(error.response.data.message);
    });
};
//Backend
const doseExist = await User.findOne({ Email: req.body.User.Email });
console.log(doseExist);
if (doseExist) {
  const check = await bcrypt.compare(plainPass, doseExist.Pass);
  if (check) {
    jwt.sign({ doseExist }, process.env.SECRET_KEY, (err, token) => {
      if (err) {
        throw new Error(err);
      } else {
        res.status(200).json({
          status: "Success",
          UserID: doseExist._id,
          UserName: doseExist.Name,
          token,
        });
      }
    });
  } else {
    res.status(400).json({
      status: "fail",
      message: "userName or Pass is incorrect",
    });
  }
} else {
  res.status(400).json({
    status: "fail",
    message: "userName or Pass is incorrect",
  });
}
```

During Logout -> we need to remove the token stored in local storage

```js
//Frontedn
const onClickSignOut = () => {
  SetUser({ status: false });
  localStorage.removeItem("Token");
  navigate("/SignIn");
};
```

Q6. About brief explanation about my project
-->
E-commers App - In this app user can create his own profile and place orders from the app. this app is functionality wise copy of any e-commers app such as FlipCart, Amazon, Ebay etc..

Q7.what is Redux ?
-->
Redux is a state management library that helps you manage the state of your application in a predictable and centralized way. Here are the basics of how Redux works:

    1. Store: The store is the centralized state of your application. It holds the entire state tree of your application and exposes a few methods to interact with it, like getState, dispatch, and subscribe. You create a store by passing in a reducer function that describes how the state should be updated.

    2. Actions: Actions are plain JavaScript objects that describe the changes that should be made to the state. They typically have a type property that describes the type of action being performed, and an optional payload property that contains any data needed to perform the action. Actions are created using action creator functions, which return the action object.

    3. Reducers: Reducers are functions that take the current state and an action as arguments, and return a new state based on the action. They should be pure functions that do not mutate the state directly. Instead, they should return a new state object that represents the updated state of the application.

    4. Dispatch: Dispatching an action is the only way to modify the state in Redux. When you dispatch an action, it is sent to the store, which in turn sends it to the reducer. The reducer then calculates the new state based on the action, and returns the updated state.

    5. Subscribe: Subscribing to the store allows you to listen for changes to the state. Whenever the state changes, the callback function you provide will be called with the updated state. You can use this to update your UI or trigger other side effects.
```js
    import React from 'react';
    import { createStore } from 'redux';

    // Define the initial state
    const initialState = {
    count: 0
    };

    // Define the reducer
    function counterReducer(state = initialState, action) {
    switch (action.type) {
        case 'INCREMENT':
        return { ...state, count: state.count + 1 };
        case 'DECREMENT':
        return { ...state, count: state.count - 1 };
        default:
        return state;
    }
    }

    // Create the store
    const store = createStore(counterReducer);

    function Counter() {
    const count = store.getState().count;

    function handleIncrement() {
        store.dispatch({ type: 'INCREMENT' });
    }

    function handleDecrement() {
        store.dispatch({ type: 'DECREMENT' });
    }

    return (
        <div>
        <p>Count: {count}</p>
        <button onClick={handleIncrement}>Increment</button>
        <button onClick={handleDecrement}>Decrement</button>
        </div>
    );
    }

    export default Counter;
```

Q8. What is Cloures in JS ?
-->
In JavaScript, a closure is a function that has access to variables in its outer lexical environment even after the outer function has returned. In other words, a closure is formed when a function is defined inside another function, and the inner function has access to variables in the outer function's scope.

    Here's an example of a closure in JavaScript:
  ```js
      function outerFunction() {

    const outerVariable = 'I am outside!';

    function innerFunction() {
    console.log(outerVariable);
    }

    return innerFunction;
    }

    const innerFunc = outerFunction();
    innerFunc();
 ```
Q9 What is display flex ?
-->
    display: flex is a CSS property that defines a flexible container for layout design. When you set the display property of a container element to flex, it creates a flex container and turns all of its direct children into flex items.

Q10. Write the code for below statetments
A.Swap 2 number 
```js
    const swap = (a,b)=>{
    console.log("Before swap a->",a," b->",b);
    let c = a;
    a = b;
    b = c;
    console.log("After swap a->",a," b->",b);
    }
    let a =10;
    let b = 20
    swap(a,b);
```

 B. Swap 2 no. without third variable

 ```js
    const swapWithout = (a,b)=>{
    console.log("Before swap a->",a," b->",b);
        a = b+a;
        b = a - b;
        a = a - b;
        console.log("After swap a->",a," b->",b);
    }

    let a =10;
    let b = 20
    swapWithout(a,b);
 ```

 Q11. Different routers in react
 -->
    React Router is the most commonly used router in React, and it provides several different types of routers that can be used for client-side routing, including the BrowserRouter:

        BrowserRouter: This is the most commonly used router in React Router, and it provides client-side routing using the HTML5 history API. It's typically used for single-page applications that have a complex UI and require dynamic rendering based on the URL.

        HashRouter: This is another router provided by React Router that uses the URL hash to manage routing. It's useful for simpler applications or situations where server-side routing is not available.

        MemoryRouter: This is a router that keeps the routing information in memory rather than in the URL. It's useful for testing and other situations where you need to manage routing programmatically.

        StaticRouter: This is a router that's used for server-side rendering in React. It allows you to render components based on a static URL and is useful for creating SEO-friendly web pages.

        NativeRouter: This is a router that's used for React Native applications. It provides routing for mobile applications and allows you to manage the navigation stack and pass props to the components.

    Each of these routers has its own use case and is suitable for different types of applications. It's important to choose the right router based on the requirements of your project and the features and functionality that you need.

Q12. Hooks in react
-->
    Hooks are a new feature introduced in React 16.8 that allow you to use state and other React features in functional components. Hooks provide a way to reuse stateful logic between components and to manage state in a more flexible and intuitive way.

    Here are some of the most commonly used hooks in React:

    useState: This hook allows you to add state to a functional component. It takes an initial value and returns an array with two values: the current state value and a function to update the state.

    useEffect: This hook allows you to perform side effects in a functional component. It takes a function and runs it after every render. You can use this hook to fetch data, update the DOM, or perform other side effects.

    useContext: This hook allows you to access a context object created by the Context API. It takes a context object and returns its current value.

    useRef: This hook allows you to create a reference to a DOM node or a value that persists between renders. It takes an initial value and returns an object with a current property that holds the current value.

    useCallback: This hook allows you to memoize a function and reuse it between renders. It takes a function and an array of dependencies and returns a memoized version of the function.

    useMemo: This hook allows you to memoize a value and reuse it between renders. It takes a function and an array of dependencies and returns a memoized version of the value.

    There are many other hooks available in React, and they provide a powerful way to manage state and side effects in functional components. Hooks are designed to be composable and reusable, and they allow you to write more expressive and declarative code.

Q13. useMemo and useCallback ?
-->
    useMemo and useCallback are two hooks in React that are used to optimize performance by memoizing values and functions.
    useMemo takes two arguments: a function that returns a value, and an array of dependencies. The function is only called when the dependencies change, and the result is memoized (cached) so that it doesn't need to be recalculated on subsequent renders. This can be useful for expensive calculations or when you need to prevent unnecessary re-renders.
    
```js
    import React, { useMemo } from 'react';

    function MyComponent(props) {
    const { data } = props;

    const sortedData = useMemo(() => {
        return data.sort();
    }, [data]);

    return (
        <div>
        <ul>
            {sortedData.map((item) => (
            <li key={item}>{item}</li>
            ))}
        </ul>
        </div>
    );
    }
```
useCallback is similar to useMemo, but it's used for memoizing functions instead of values. It takes a function and an array of dependencies, and returns amemoized version of the function. This can be useful for preventing unnecessary re-renders of child components when a function is passed down as a prop.
Here's an example of using useCallback:
```js
import React, { useCallback } from 'react';

    function MyComponent(props) {
    const { onButtonClick } = props;

    const handleClick = useCallback(() => {
        onButtonClick('clicked');
    }, [onButtonClick]);

    return (
        <div>
        <button onClick={handleClick}>Click me</button>
        </div>
    );
    }
```

Q14. what is the use ContextApi in place redux ?
-->
  Context API is a feature in React that allows you to share data between components without having to pass props down the component tree manually. It provides a way to pass data through the component tree without having to pass props down manually at every level.
     You can use the Context API as a replacement for Redux in certain cases, especially when your application doesn't have complex state management needs. Redux can be overkill for small to medium-sized applications, and using the Context API can simplify your code and reduce the amount of boilerplate.
Here's an example of using the Context API to manage state:
```js
import React, { createContext, useState } from 'react';

const MyContext = createContext();

function MyProvider(props) {
  const [count, setCount] = useState(0);

  const increment = () => {
    setCount(count + 1);
  };

  const decrement = () => {
    setCount(count - 1);
  };

  return (
    <MyContext.Provider value={{ count, increment, decrement }}>
      {props.children}
    </MyContext.Provider>
  );
}

function MyComponent() {
  const { count, increment, decrement } = useContext(MyContext);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>Increment</button>
      <button onClick={decrement}>Decrement</button>
    </div>
  );
}

function App() {
  return (
    <MyProvider>
      <MyComponent />
    </MyProvider>
  );
}
```

Q15. what are eventloop ?
-->
In JavaScript, the event loop is a mechanism for handling asynchronous operations. It's a fundamental part of the JavaScript runtime, and it's responsible for coordinating the execution of code in a way that allows for non-blocking I/O and asynchronous processing.

The event loop is a loop that continually checks the call stack and the task queue. When the call stack is empty, the event loop checks the task queue for any tasks that need to be executed. If there are tasks in the task queue, the event loop moves them to the call stack and executes them. This process continues until the task queue is empty.

Here's an example of how the event loop works:
```js
console.log('1');

setTimeout(() => {
  console.log('2');
}, 1000);

console.log('3');
```
In this example, we're logging the numbers 1, 2, and 3 to the console, with a 1-second delay before logging the number 2. Here's what happens:

`1.The first console.log statement logs the number 1 to the console.`
`2.The setTimeout function is called, which adds a task to the task queue to log the number 2 to the console after a 1-second delay.`
`3.The second console.log statement logs the number 3 to the console.`
`4.The call stack is now empty, so the event loop checks the task queue and finds the task to log the number 2 to the console.`
`5.The event loop moves the task from the task queue to the call stack, and the number 2 is logged to the console.`
`6.The task is removed from the call stack, and the event loop checks the task queue again. Since the task queue is now empty, the event loop stops checking and the program ends.`

This is a simple example of how the event loop works, but it's important to understand how it operates in order to write effective and efficient asynchronous JavaScript code.


