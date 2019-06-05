## Redux

Hello, React extraordinaires! Today we are complementing React with a nifty little design pattern (and technology) called Redux. Remember how hard it was to implement undo with Flux architecture? In every single handler we had to account for undo. Yucky! Redux solves this problem by merging all of our handlers into one single function. This allows us to update our history object with just one big function. But do not think that this is all it does. Redux solves many more design challenges and makes it easy to build complex web applications on top of React. Behold!

Today your task is to implement Redux architecture into your todo app.

## Release 0

Start by watching [this video](https://www.youtube.com/watch?v=1w-oQ-i1XB8). [This](https://egghead.io/courses/getting-started-with-redux) is also a really good tutorial if you have the time for it.

## Release 1

Implement Redux in Todos.

* Setup Redux according to the protocol specified in the [docs](https://redux.js.org/).
* Convert all of your handlers to Redux actions and update state with a reducer. EVERY SINGLE ACTION THAT UPDATES STATE SHOULD BE AN ACTION. YOU SHOULD NOT SEE `setState` ANYWHERE IN YOUR APPLICATION.
* Be sure to keep your state immutable by making a new copy of state in your reducer with `JSON.parse(JSON.stringify())`. (Stretch: Implement [Immutable JS](https://facebook.github.io/immutable-js/) instead to ensure that your state remains immutable. Note that you'll probably have to make a lot of small tweaks within your code to successfully implement Immutable.)
* If you have time: implement undo (this should be pretty easy now!)

## Release 2

In this release, you'll learn how to interact with servers. We're getting closer to linking our API to the frontend! Woo!

* First, we need to learn about [Redux Thunk](https://github.com/reduxjs/redux-thunk). Out of the box, we can only dispatch synchronous actions to Redux. However, Redux Thunks allow us to dispatch asynchronous actions and then update the store only when the function resolves. Woohoo!
* Now it's time to grab some data from our server and load it into our app. We don't have an API running (yet), so we are going to grab our todo list from this link: `https://raw.githubusercontent.com/asalexanderlee/bootcamp-6/master/todos.json`. The action should first fetch the JSON object from the link (our fake server). Once the fetch promise resolves, it should dispatch an action typed `LOAD_TODOS` that adds the todos to the store. Note, that if you need to change the structure of todos.json, checkout your own branch, update the JSON file, push it up, and then update the `githubusercontent.com` link. (The link is RESTful so you should know how to do this!). Once the data has loaded, you should be able to edit the todo list as normal. However, any of the edits that you make will not save to the server. We will get to that tomorrow!

## Release 3

* Whit's Custard on me!

_**In the interest of time, please skip the below release!**_
## Release 4

Many of the application you will make will require some sort of web form. Despite seeming simple, forms are actually beasts. What if the user types in incorrect data? What if they forget a required field? What if you want to auto-populate a dropdown based on a user's login information? What if you want to enable/disable parts of a field based on a user's response?

Although, it's not a silver bullet, Redux Forms is a great package that does A LOT of work for you. Your job is to use Redux Form to handle all of your input fields in your todo app, including (but not limited to!) the following:

* Description
* Date
* Stars
* Complete
