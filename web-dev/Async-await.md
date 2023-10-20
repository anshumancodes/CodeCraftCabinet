#async-function
The **`async function`** declaration creates a binding of a new async function to a given name. The `await` keyword is permitted within the function body, enabling asynchronous, promise-based behavior to be written in a cleaner style and avoiding the need to explicitly configure promise chains.

#Syntax

`async function name(param0) {  statements}
`async function name(param0, param1) {statement}`
`async function name(param0, param1, /* …, */ paramN) {statements}`


#await-keyword
with the use of await we can store the value of that the promise returns and use it later in the program,await is also useful because it stops the executing further until the promise resolves - this prevents errors when another variable or function is dependent on the value of the specific promise further in the program.

Example:

```
```function resolveAfter2Seconds() {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve('resolved');
    }, 2000);
  });
}

async function asyncCall() {
  console.log('calling');
  const result = await resolveAfter2Seconds();
  console.log(result);
  // Expected output: "resolved"
}

asyncCall();


```

Everytime you use the `async function` it will return a promise chained value!

even if for something like this :

```
async function asyncCall() {
  return 911
}


```

An asynchronous function always returns a promise, so in this case, the function returns a promise that resolves to `911`.

You can call this function and handle its resolved value using the `then` method of the returned promise, or use the `async/await` syntax.

Here's an example using the `then` method:

```
asyncCall().then(value => {
  console.log(value); // This will log 911
});


```

And here's an example using the `async/await` syntax:

```
(async () => {
  const value = await asyncCall();
  console.log(value); // This will log 911
})();

```

note: To use `await`, you need to be inside an `async` function.