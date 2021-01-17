# react--interview--questiom
why need a react?
-React allows developers to create large web applications that can change data, without reloading the page. The main purpose of React is to be fast, scalable, and simple. It works only on user interfaces in the application. This corresponds to the view in the MVC template.

how virtual dom works? 
there are three simple steps 
A-whenever any underlying data changes,the entire ui is re-rendered in virtual dom representation.
B-then the difference between the previous dom representaion and the new one is calculate.
C-once the calculations is done, the real dom will be updated with only things that have actually change.

what is the difference between shadow dom and virtual dom?
-the shadow dom is a browser technology designed primarily for scoping variable and css in web components. the virtual dom is a concept implimented by libaries in javascripton top of browser APIs.

what is react fiber?
-  fiber is  the reconciliation engine. the goal of react fiber is  to increase its suitability for areas like animation, layout, and gestures. Its headline feature is incremental rendering: the ability to split rendering work into chunks and spread it out over multiple frames.
what are controlled component?
-a component that control that input elements within the froms on subsequent user input is called controlled component.ie,
that is every state mutation will have an associated handler function.

What are uncontrolled components?
-the Uncontrolled Components are the ones that store their own state internally, and you query the DOM using a ref to find its current value when you need it. This is a bit more like traditional HTML.

What is the difference between createElement and cloneElement?
-JSX elements will be transpiled to React.createElement() functions to create React elements which are going to be used for the object representation of UI. Whereas cloneElement is used to clone an element and pass it new props.

What is Lifting State Up in React?
-when the several components need to share the some change data thet is a recommended to lift the shared state up to their closest common ancestor.That means if two child components share the same data from its parent, then move the state to parent instead of maintaining local state in both of the child components.

What are the different phases of component lifecycle?
The component lifecycle has three distinct lifecycle phases:

Mounting: The component is ready to mount in the browser DOM. This phase covers initialization from constructor(), getDerivedStateFromProps(), render(), and componentDidMount() lifecycle methods.

Updating: In this phase, the component get updated in two ways, sending the new props and updating the state either from setState() or forceUpdate(). This phase covers getDerivedStateFromProps(), shouldComponentUpdate(), render(), getSnapshotBeforeUpdate() and componentDidUpdate() lifecycle methods.

Unmounting: In this last phase, the component is not needed and get unmounted from the browser DOM. This phase includes componentWillUnmount() lifecycle method.

It's worth mentioning that React internally has a concept of phases when applying changes to the DOM. They are separated as follows

Render The component will render without any side-effects. This applies for Pure components and in this phase, React can pause, abort, or restart the render.

Pre-commit Before the component actually applies the changes to the DOM, there is a moment that allows React to read from the DOM through the getSnapshotBeforeUpdate().

Commit React works with the DOM and executes the final lifecycles respectively componentDidMount() for mounting, componentDidUpdate() for updating, and componentWillUnmount() for unmounting.

 explain the purpose of render() in react.
- every component in render(),should be pure component,it return  single react element which is represent to react native dom, html element inside render() must be enclose by encolose tag like <from>,<div> ,<grou> etc.
  
  explain props in react.
  -props are short of properties. only read only, are pure i.e immutable ,always pass-down parent to child component,used to render dynamic data.
  
  how can you update state in react component?
  - using this.setState() you can change in state of the component.
  
  what is arrow function? how to used.
  -also called fat arrow function(=>), allow to bind to context components proporly auto binding is not avialable by defaults in Es6,make to easy hoc function.

What are the recommended ways for static type checking?
-Normally we use PropTypes library (React.PropTypes moved to a prop-types package since React v15.5) for type checking in the React applications. For large code bases, it is recommended to use static type checkers such as Flow or TypeScript, that perform type checking at compile time and provide auto-completion features.

What is the use of react-dom package?
-The react-dom package provides DOM-specific methods that can be used at the top level of your app. Most of the components are not required to use this module. Some of the methods of this package are:

render()
hydrate()
unmountComponentAtNode()
findDOMNode()
createPortal()

What is ReactDOMServer?
-The ReactDOMServer object enables you to render components to static markup (typically used on node server). This object is mainly used for server-side rendering (SSR). The following methods can be used in both the server and browser environments:

renderToString()
renderToStaticMarkup()
For example, you generally run a Node-based web server like Express, Hapi, or Koa, and you call renderToString to render your root component to a string, which you then send as response.

How to use innerHTML in React?
-The dangerouslySetInnerHTML attribute is React's replacement for using innerHTML in the browser DOM. Just like innerHTML, it is risky to use this attribute considering cross-site scripting (XSS) attacks. You just need to pass a __html object as key and HTML text as value.

In this example MyComponent uses dangerouslySetInnerHTML attribute for setting HTML markup:

function createMarkup() {
  return { __html: 'First &middot; Second' }
}

function MyComponent() {
  return <div dangerouslySetInnerHTML={createMarkup()} />
}

How events are different in React?
-Handling events in React elements has some syntactic differences:

React event handlers are named using camelCase, rather than lowercase.
With JSX you pass a function as the event handler, rather than a string.


