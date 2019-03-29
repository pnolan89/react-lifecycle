# The React Component Lifecycle

Every component created in React has a lifecycle. This involves (1) the component being created, (2) its state and props changing from updates, and (3) being unmounted (removed) from the DOM.

React provides a number of methods that hook into these different phases, called lifecycle methods. These methods are a powerful way of controlling component behavior at different points in its lifecycle.

This document will explain the phases of the React Component Lifecycle, and some common lifecycle methods associated with each phase.

### Phase 1: Mounting
The **mounting phase** is where the React component is first created. The code that constitutes the component, along with React's internals, are inserted into the DOM.

Lifecycle methods triggered during the mounting phase include:

#### constructor()
This is the first method to be called during the mounting phase. It is only called once in the entire lifecycle of a component. It sets up the component's state and other initial variables.

#### render()
This prepares the element that gets mounted to the DOM. A required method for all React components.

#### componentDidMount()
This method is invoked immediately after the component **did** mount on the browser DOM. This is typically where API calls and other asynchronous functions can be invoked.

### Phase 2: Updating
Once the component has been mounted to the DOM, it can continue to change and grow by receiving updates. It can be updated by either (a) changing its current state, or (b) receiving new props from parent components.

Lifecycle methods triggered during the updating phase include:

#### render()
As with the mounting phase, this prepares the updated element that gets mounted to the DOM.

#### componentDidUpdate()
This method is invoked immediately after the newly updated element has been updated in the DOM. Similar to componentDidMount(), it is useful for syncing API calls or other third party libraries with every update.

### Phase 3: Unmounting
When the component is no longer needed, the unmounting phase removes it from the DOM.

There is only one lifecycle method triggered during the unmounting phase:

#### componentWillUnmount()
This is the final method in the lifecycle, triggered just before the component gets removed from the DOM. It is usually used to run cleanup before removing the component. For example, when a user logs out, this method may remove any user details and auth tokens before unmounting the component.

### Error Handling
While not technically a lifecycle phase, React also has several methods that automatically trigger when an error is thrown by a descendant (child) component.

Some of the methods triggered during error handling include:

#### static getDerivedStateFromError()
This is the first method invoked in error handling. The value returned from this method is used to update the component's state.

#### componentDidCatch()
This method is invoked immediately after the error has been thrown. Similar to componentDidMount(), this method is used to make asynchronous function calls, such as logging the error details to an external service.


## Conclusion
A working understanding the component lifecycle is an essential building block to creating robust and intuitive applications using React. This document was just a brief introduction to the major phases and commonly-used lifecycle methods.

For a useful visual overview of the lifecycle, visit the [React Lifecycle Methods Diagram](http://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/) project. For more detailed information, please review [the official documentation](https://reactjs.org/docs/state-and-lifecycle.html).