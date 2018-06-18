# react-cheatsheet
Cheatsheet for learnings on React and the various resources

# React

## What's special about React?
##### Compositional Model
* Simple functions combined to create another function  
* Declarative Nature  
Car temp analogy is:  
 Imperative - you fiddle with hot/cold dial to get the right temp  
Declarative - car has temp setting. You tell it, it keeps it there

##### Unidrectional Data Flow
* React is undirectional - data flows one way, down to components, simplifying flows.
* Data updates are sent to the parent and flow back down
* Angular & Ember are bidirectional

#### Web 2.0
* Because of the composition of a page using components, updates only re-render that components whose state/data has changed, avoiding the need to send the whole page back and forth between the browser and server.

###### React is really just javascript
* Enough said  

### React Resources
[ReactJs.org - the definitive guide](https://reactjs.org/)
[ReactJS - A great place to start](https://reactjs.org/docs/hello-world.html)
[Sandbox for editing React code](https://codesandbox.io/s/new)  


[Thinking in React](https://reactjs.org/docs/thinking-in-react.html)
[Components and Props](https://reactjs.org/docs/components-and-props.html)  
[Imperative vs declarative Programming](https://tylermcginnis.com/imperative-vs-declarative-programming/)  
[9 things every React Beginner Should Know](https://camjackson.net/post/9-things-every-reactjs-beginner-should-know)  
[How Virtual-DOM and diffing works in React](https://medium.com/@gethylgeorge/how-virtual-dom-and-diffing-works-in-react-6fc805f9f84e)  
[Optimizing Performance](https://reactjs.org/docs/optimizing-performance.html#avoid-reconciliation)

### React Courses
[Styling React](http://stylingreact.com/)

## Creating React Applications

### Create-React-App
This is a great starting place for creating React applications. This is Facebooks tool for creating a bare skeleton react application. This only provides the view layer and does not include any DB or API layer, which you'll need to build independently. This requires more work than the Meteor option but you'll learn it at a deeper level.



### Meteor
An end-to-end Javascript framework. This is one of the best ways to be highly productive(one of may favorites). The only downside Meteor abstracts a lot of the details away making for an easy-to-use and highly productive framework, but you want learn the in-depth details of making API or DB calls on your own. 



## Components and Props
Components allow you to decompose the UI into indepent, reusable pieces. React components typically fall into two categories: Containers and Presentational Components. Containers gather the data needed for the presentational components. When using Redux this is the component that is connected to the store. Presentational components are clueless as to where the data comes from. They simply take the data given and render it. This allows the presentational components to be used with different containers.


### Components and Props - Resources
[React Components and Elements](https://medium.com/@dan_abramov/react-components-elements-and-instances-90800811f8ca)  

## State
State is data that changes based on events in the application. This is different than data that comes from outside sources such as an API or Db call. 



### State resources
[Thinking in React](https://reactjs.org/docs/thinking-in-react.html#step-4-identify-where-your-state-should-live)  
[State and Lifecycle](https://reactjs.org/docs/state-and-lifecycle.html)  
[You Probably Don't Need Derived State
](https://reactjs.org/blog/2018/06/07/you-probably-dont-need-derived-state.html)
[React setState usage and gotchas
](https://itnext.io/react-setstate-usage-and-gotchas-ac10b4e03d60)  

## Pure components

### Pure Components - resources
[React JS: what is a PureComponent?](http://lucybain.com/blog/2018/react-js-pure-component/)



# React Router


### React Router resources  
https://reacttraining.com/react-router/web/example/auth-workflow



### `How to get state and force render`
```bash   
class App extends React.Component {
  componentDidMount () {
    const { store } = this.props

    store.subscribe(() => this.forceUpdate())
  }
  render() {
    const { store } = this.props
    const { todos, goals } = store.getState()
```


### React-Redux
- Provides a single source of truth for the application state
- Helps provide Separation of Concerns(SOC) between the state of the application from the presentation
- Reduces complexity by providing centralized management of state
- Provides controlled access to the state
- Increases performance by shared usage of state and avoiding costly db/disk request. 

## Principles Redux follows
- Redux follows the "Flux" pattern
- State is contained in a store

- State is read only
  - State is accessed via subscribe
  - Access to modify the state is only dispatching an action

- Reducer maintains the state
  - Reducer should be a pure function
  - It takes in the previous state and action
  - It returns a new state

## What to put in Redux?
Put in redux state that:
 - shared by multiple components
 - persisted over route changes

 Don't put in Redux data that a single component receives and renders

 The creator of Redux, Dan Abramov, provides the following advice on what to put in Redux: "Use Redux for state that matters globally or is mutated in complex ways… The rule of thumb is: do whatever is less awkward."

### Using React Redux
You can uses Redux and its store with the it various functions: 
* creatStore(), 
* (subscribe()), 
* getState, 
* dispatch(). 
To access only the part of state needed you can use a Provider component with a connect() function, which the creators of redux have included in the react-redux package. 

### Principles of State Normalization
It's recommended that when using nested data with Redux the it should be managed in a normalized form.

The Redux principles of state normalization are: 
* Each type of data gets its own "table" in the state.
* Each "data table" should store the individual items in an object, with the IDs of the items as keys and the items themselves as the values.
* Any references to individual items should be done by storing the item's ID.
* Arrays of IDs should be used to indicate ordering.
(from)[https://redux.js.org/recipes/structuring-reducers/normalizing-state-shape]

### React-Redux Resources
[Redux Documentation](https://redux.js.org/)
[Usage Redux with React](https://redux.js.org/basics/usage-with-react)
[Organizing State](https://redux.js.org/faq/organizing-state)
[How to choose between Redux's store and React's state? #1287](https://github.com/reduxjs/redux/issues/1287)

## Redux Middleware
What is Redux middleware?
REdux middleware  allows injection of functionality between the calling of the dispatch and running of the reducer. It allows data checks, logging, etc. Middleware is in the chain of events after dispatch andbefore the store is updated.

## Calling Redux Middleware


## Redux Thunk
Redux by itself only supports the synchronous flow of data. Redux Thunk is called via a Redux middleware and provides asynchronicity support for Redux applications. The helps provide cleaner code by moving the dispatch logic for asynchronous calls to the action creators, making the action creators the sole source of changes to state and api calls to persist the state change (to a Db or whatever datastore is being used).


### Other tools similiar to Thunk
[Saga](https://hackernoon.com/moving-api-requests-to-redux-saga-21780f49cbc8)
[Axios](https://github.com/svrcekmichal/redux-axios-middleware)
[What is the right way to do asynchronous operations in Redux?](https://decembersoft.com/posts/what-is-the-right-way-to-do-asynchronous-operations-in-redux/)

### Redux Thunk Resources
[Redux Thunk on GitHub](https://github.com/reduxjs/redux-thunk)  
[Async Flow](https://redux.js.org/advanced/async-flow)  
[Dan Abramov's Stack Overflow on Redux Thunk](https://stackoverflow.com/questions/35411423/how-to-dispatch-a-redux-action-with-a-timeout/35415559#35415559)


### Redux Resources
https://css-tricks.com/learning-react-redux/
https://blog.pusher.com/the-what-and-why-of-redux/
https://medium.com/netscape/component-state-vs-redux-store-1eb0c929277
https://medium.com/netscape/component-state-vs-redux-store-1eb0c929277
https://medium.com/prod-io/react-redux-architecture-part-1-separation-of-concerns-812da3b08b46
