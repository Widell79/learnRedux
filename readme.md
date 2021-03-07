# Learn Redux

Our app can handle adding/removing todo/goal items as well as toggling an item (as complete or incomplete)!

## How ut works

Whenever dispatch is called, we invoke our app function. The app function will then invoke the todos reducer as well as the goals reducer. Those will return their specific portions of the state. And then, the app function will return a state object with a todos property (the value of which is what the todos reducer returned) and a goals property (the value of which is what the goals reducer returned).

We use JavaScript constants instead of strings to call our actions.
Our `.dispatch()` calls special functions called action creators, instead of passing in unique objects directly to them.

## UI

We connect our functioning state application with a front-end UI. There are form fields and buttons on the UI that can be used to add new Todo items and Goal items to the state. Updating the state will also cause the entire application to re-render so that the visual representation of the application matches that of the info stored in the state object.

## DOM-manipulation

- accessing elements with `document.getElementById()`
- adding listeners with `.addEventListener()`
- accessing the `.value property on an element`
- creating a new element with `.createElement()`
- adding new content with `.appendChild()`
