Homework 20th May 2019.

Part 1
What are actions used for?
It triggers the reducer to calculate the new state by passing data.

What type of object must an action be?
The action is a plain object such as a button click.

At a minimum, what is the one property the action should have? And what is this property used for?
The action should have a type property to indicate what action is to be performed.

What is the responsibility of the reducer?
The reducer accepts the previous state and an action to produce a new state and keep that.

What is the responsibility of the store?
It is to store a single version of the state within the application.

Part 2
When working with Redux, the reducers must be pure functions. One of the qualities that makes a function pure is that is doesn't modify (or 'mutate') objects outside their scope. When a reducer is passed the state, it must not mutate the state, but instead return a newly created state object. Read the following page on common ways patterns for not mutating state in reducers:

https://redux.js.org/recipes/structuring-reducers/immutable-update-patterns

Which of the following functions are pure:

const reducer1 = (action, state) => {
return state + 1;
}

const reducer2 = (action, state) => {
state.push("Cat");
return state;
}

This function is pure
const reducer3 = (action, state) => {
return [...state, "Dog"];
}

const reducer4 = (action, state) => {
return state.map(pet => {
pet.price /= 2;
return pet;
});
}

This function is pure

const reducer5 = (action, state) => {
return state.map(pet => {
return { ...pet, pet.price: pet.price / 2 }
});
}
