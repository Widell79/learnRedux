# Learn Redux

Our app can handle adding/removing todo/goal items as well as toggling an item (as complete or incomplete)!

## Reducer composition

We have two main properties on our state tree: todos and goals. Naturally, we'd create an individual reducer for both of those and then create a single root reducer using Redux's `combineReducers` method.

`combineReducers`, is responsible for invoking all the other reducers, passing them the portion of their state that they care about. We're making one root reducer, by composing a bunch of other reducers together.

## UI

We connect our functioning state application with a front-end UI. There are form fields and buttons on the UI that can be used to add new Todo items and Goal items to the state. Updating the state will also cause the entire application to re-render so that the visual representation of the application matches that of the info stored in the state object.

## DOM-manipulation

- accessing elements with `document.getElementById()`
- adding listeners with `.addEventListener()`
- accessing the `.value property on an element`
- creating a new element with `.createElement()`
- adding new content with `.appendChild()`
