# ExpenseTrackerWeb
section 3 & 4

section 3

React basics & working with components

- module introduction
    React core syntac & JSX
    working with componets
    working with data

- React
    Make building complex, interactive and reactive user interfaces simpler.

- Component 
    React is all about "Components"

    - What is Components? ....
    - Why components? 
        - Reusability : Don't repeat.
        - Separation of Concerns : keeping easily

        "Split big chunks of code into multiple smaller functions"

    - How is a component built?
        - in general) HTML + css + javaScript
        - React - combined.
            React allows you to create re-usable and reactive components consisting of HTML and JavaScript + (css). -> Declarative approach.
            Define the desired target state and let React figure out the actual JavaScript DOM instructions.
    
    - Create React App ) basic step for make react app. recommend

    - node.js - make the react runs out of the browser.

    - react 
        - css를 js file에서 import 가능
        - html code 혼용 사용하는 것 처럼 -> 전달 전 변환이 일어난다.
        - Using only one html file -> it means react working on the same html file.
        - react-dom

    - JSX
        - extension of Javascript grammar. 
        - This is only work because of this processdoes NPM start process which we started, //sources로 부터
        - npm (modules which is included Node.js)

    - Build your own, custom HTML Elements -> components
    - build a component tree -> <App /> 부터.. 가지치기
    - react component -> javascript function
    - create component -> export -> import -> make code. <sth></sth>

    - props : Components can't just use data stored in other components.
        - no limit
        - props are our way of passing data from components A to B.(to direct child components)
        - children is reserved name. -> wrapping 
    
    - react is a js function with some JSX twist.
    - if there is no content : self -closing.


- Summary 3 (Components)
    - React core syntax & JSX
    - Working with Components.(props)
    - Working with Data(props)

section 4

- from start to now, the program is static. we can make dynamic.
- Using EventhandlerListener
- using "on" and adding function
    <button onClick={()=>{console.log('Clicked')}}></button>

- keep in mind component is a function
- Some function returns JSX
- By using our components in JSX code, we make React aware of our component functions.
- The reason for this is that calling this state updating function actually doesn't change the value right away, but instead schedules this state update.
- Do not need to import React from react. but make clearly that JSX is under the JSX, they are imported.

- difference between JS and JSXi
    JSX looks like HTML.
    JSX is a language that makes react components.
    When we use .js file, it doesn't rendering automatically, so we use JSX.
    When react build, HTML modify to js.

- setTitle recall that function.
- At the eventHandler, we don't execute that, just pointing.

- Default vanilla js event Handler
    document.getExementById('').addEventListener('click', (event) => {});
- React
    <input type="text" onChange={titleChangeHandler}/>
    const titleChangeHandler =(event)=>{}; ...

- target // useful.. to input box!!

- to make multiple event handler: just adding useState() multiple times
- Want to handle together just use object and be careful the other data losted.
    const [userInput, setUserInput] = useState({
    enteredTitle: "",
    enteredAmount: "",
    entertedDate: "",
  });

  const titleChangeHandler = (event) => {
    // setEnteredTitle(event.target.value);
    setUserInput({
        ...userInput,
        enteredTitle: event.target.value, 
    })
};

- event handler
    - setUserInput({
        ...userInput,
    });

    - setUserInput((prevState)=>{
        return { ...prevState, enteredTitle: event.target.value}
    });
    can garantee the latest snapshot

- submit and clear
    - just use <input type="text" value = {enteredTitle} onChange={titleChangeHandler} />
    and in the submit handler we call setEnteredTitle('') <- the empty string.

- How you communicate with up!
    - using your own components, to execute up's function!! with props.