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

[Components and Props](https://reactjs.org/docs/components-and-props.html)  
[Imperative vs declarative Programming](https://tylermcginnis.com/imperative-vs-declarative-programming/)  
[9 things every React Beginner Should Know](https://camjackson.net/post/9-things-every-reactjs-beginner-should-know)  
[How Virtual-DOM and diffing works in React](https://medium.com/@gethylgeorge/how-virtual-dom-and-diffing-works-in-react-6fc805f9f84e)  
[Optimizing Performance](https://reactjs.org/docs/optimizing-performance.html#avoid-reconciliation)

### React Courses
[Styling React](http://stylingreact.com/)

## Creating React Applications

Create-React-App
This is a great starting place for creating React applications

Meteor
An end-to-end Javascript framework. This is one of the best ways to be highly productive(one of may favorites). The only downside is you'll be using Node.JS, but Meteor abstracts a lot of it away making it easy to use and productive, but you want learn Node.JS in-depth.

## Components and Props


### Components and Props - Resources
[React Components and Elements](https://medium.com/@dan_abramov/react-components-elements-and-instances-90800811f8ca)  

## State


### State resources
[State and Lifecycle](https://reactjs.org/docs/state-and-lifecycle.html)  
[You Probably Don't Need Derived State
](https://reactjs.org/blog/2018/06/07/you-probably-dont-need-derived-state.html)
[Thinking in React](https://reactjs.org/docs/thinking-in-react.html#step-4-identify-where-your-state-should-live)  
[React setState usage and gotchas
](https://itnext.io/react-setstate-usage-and-gotchas-ac10b4e03d60)  

## Pure components

### Pure Components - resources
[React JS: what is a PureComponent?](http://lucybain.com/blog/2018/react-js-pure-component/)



# React Router


### React Router resources  
https://reacttraining.com/react-router/web/example/auth-workflow




# Redux with React
- Provides a single source of truth
- Separation of Concerns(SOC) between the state of the application from the presentation

## Advantages of using Redux are:
- Reduces complexity by providing centralized management of state
- Provides controlled access to the state
- Increases performance by shared usage of state and avoiding costly db/disk request. Can use


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
## Redux Middleware
What is Redux middleware?
REdux middleware  allows injection of functionality between the calling of the dispatch and running of the reducer. It allows data checks, logging, etc. Middleware is in the chain of events after dispatch andbefore the store is updated.

## Calling Redux Middleware

### Redux Resources
https://css-tricks.com/learning-react-redux/
https://blog.pusher.com/the-what-and-why-of-redux/
https://medium.com/netscape/component-state-vs-redux-store-1eb0c929277
https://medium.com/netscape/component-state-vs-redux-store-1eb0c929277
https://medium.com/prod-io/react-redux-architecture-part-1-separation-of-concerns-812da3b08b46
