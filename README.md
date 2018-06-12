# react-cheatsheet
Cheatsheet for learnings on React and the various resources

# React

## Unidirectional Data flow


## React Resources
[Sandbox for editing React code] (https://codesandbox.io/s/new)

[Sandbox for editing React code] (https://reactjs.org/docs/thinking-in-react.html#step-4-identify-where-your-state-should-live)
[Sandbox for editing React code] (https://reactjs.org/docs/components-and-props.html)
[Sandbox for editing React code] (https://tylermcginnis.com/imperative-vs-declarative-programming/)
[Sandbox for editing React code] (https://medium.com/@dan_abramov/react-components-elements-and-instances-90800811f8ca

### React Courses
Styling React http://stylingreact.com/

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
