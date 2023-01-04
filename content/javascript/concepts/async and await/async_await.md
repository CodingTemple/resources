# Async and Await

Asynchronous code can become difficult to follow when it has a lot of things going on. <mark>async</mark> and <mark>await</mark> are two keywords that can help make asynchronous read more like synchronous code. This can help code look cleaner while keeping the benefits of asynchronous code.

To demonstrate asynchronous code a bit easier, we'll be utilizing the Pokemon API!

For example, the two code blocks below do the exact same thing. They both get information from a server, process it, and return a promise.

```js
const getPokemonData = () => {
    fetch('https://pokeapi.co/api/v2/pokemon/charizard')
    .then((response) => {
        return response.json()
    })
    .then((data) => {
        console.log(data)
    })
}
```
```js
const getPokemonData = async () => {
    const response = await fetch('https://pokeapi.co/api/v2/pokemon/charizard')
    const data = await response.json()
    console.log(data)
}
```

## The async keyword

The <mark>async</mark> keyword is what lets the JavaScript engine know that you are declaring an asynchronous function. This is required to use <mark>await</mark> inside any function. When a function is declared with <mark>async</mark>, it automatically returns a promise; returning in an <mark>async</mark> function is the same as resolving a promise. Likewise, throwing an error will reject the promise.

An important thing to understand is <mark>async</mark> functions are just syntactical sugar for promises.

The <mark>async</mark> keyword can also be used with any of the ways a function can be created. 

For example:

* Asynchronous Arrow Function
```js
const getPokemonData = async () => {
    const response = await fetch('https://pokeapi.co/api/v2/pokemon/charizard')
    const data = await response.json()
    console.log(data)
}
```

* Asynchronous Function Declaration
```js
async function getPokemonData() {
    const response = await fetch('https://pokeapi.co/api/v2/pokemon/charizard')
    const data = await response.json()
    console.log(data)
}
```

## The await keyword
The <mark>await</mark> keyword tells JavaScript to wait for an asynchronous action to finish before continuing the function. It’s like a ‘pause until completed’ keyword. The <mark>await</mark> keyword is used to get a value from a function where you would normally use .then(). Instead of calling .then() after the asynchronous function, you would simply assign a variable to the result using <mark>await</mark>. Then you can use the result in your code as you would in your synchronous code.

## Error Handling
Handling errors in <mark>async</mark> functions is very easy by using the <mark>try/catch</mark> block! If you want to handle the error directly inside the <mark>async</mark> function, you can use <mark>try/catch</mark> just like you would inside synchronous code.
```js
const getPokemonData = async () => {
    try {
        const response = await fetch('https://pokeapi.co/api/v2/pokemon/charizard')
        const data = await response.json()
        console.log(data)
    } catch (error) {
        // Handle the error here however you like!
    }
}
```