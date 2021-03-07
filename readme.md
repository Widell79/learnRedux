# Learn Redux

Our app can handle adding/removing todo/goal items as well as toggling an item (as complete or incomplete)!

## How Redux Works

**Single Source of Truth:** Redux has what it calls the store. A store is an object that contains your whole application state. The different pieces of state are stored in an object tree. This makes it easier to implement Undo/Redo.

### The Store

The store object itself has a very small API with only four methods:

- `store.dispatch(action)`
- `store.subscribe(listener)`
- `store.getState()`
- `replaceReducer(nextReducer)`

There’s no method for setting state. Therefore, dispatching an action is the only way for the application code to express a state change.

**State is read-only:** The state cannot be changed directly by the view or any other process. In order to change the state, you must express your intent by emitting an action. An action is a plain object describing your intent, and it contains a type property and some other data. Actions can be logged and later replayed which makes it good for debugging and testing purpose

**Reducer:** The reducers are responsible for figuring out what state changes need to happen and then transforming it to reflect the new changes. Reducer is a pure function that takes in the previous (the current state about to be changed) and an action, determine how to update the state based on the action type, transforms it and returns the next state (the updated state).

There are things you should never do inside a reducer:

- Mutate its arguments.
- Perform side effects like API calls and routing transitions.
- Call non-pure functions.

### Pure Functions

- It does not make outside network or database calls.
- Its return value depends solely on the values of its parameters.
- Its arguments should be considered “immutable”, meaning they should not be changed.
- Calling a pure function with the same set of arguments will always return the same value.

## Reducer composition

We have two main properties on our state tree: todos and goals. Naturally, we'd create an individual reducer for both of those and then create a single root reducer using Redux's `combineReducers` method.

`combineReducers`, is responsible for invoking all the other reducers, passing them the portion of their state that they care about. We're making one root reducer, by composing a bunch of other reducers together.

## Redux Middleware

Redux makes state management predictable: in order to change the store’s state, an action describing that change must be dispatched to the reducer. In turn, the reducer produces the new state. This new state replaces the previous state in the store. So the next time `store.getState()` is called, the new, most up-to-date state is returned.

Between the dispatching of an action and the reducer running, we can introduce code called **middleware** to intercept the action before the reducer is invoked.

What's great about middleware is that once it receives the action, it can carry out a number of operations, including:

- producing a side effect (e.g., logging information about the store)
- processing the action itself (e.g., making an asynchronous HTTP request)
- redirecting the action (e.g., to another piece of middleware)
- dispatching supplementary actions

## UI

We connect our functioning state application with a front-end UI. There are form fields and buttons on the UI that can be used to add new Todo items and Goal items to the state. Updating the state will also cause the entire application to re-render so that the visual representation of the application matches that of the info stored in the state object.

## DOM-manipulation

- accessing elements with `document.getElementById()`
- adding listeners with `.addEventListener()`
- accessing the `.value property on an element`
- creating a new element with `.createElement()`
- adding new content with `.appendChild()`
