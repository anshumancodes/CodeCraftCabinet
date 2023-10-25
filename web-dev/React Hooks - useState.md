`useState` is a React Hook that lets you add a state variable to your component.

syntax:

```const [state, setState] = useState(initialState);```

note: you need to call useState on the top level of your component!

now lets understand how it works:

the syntax basically says ``` [something ,setSomething]``` basically it is something to begin with but set it as "something", using array Destructuring.

the parameters are set like``` [initialState,nextState]``` , initialState is the value the state initially it is passed as a parameter/arg in   ```useState(initialState)```



`useState` returns an array with exactly two values:

1. The current state. During the first render, it will match the `initialState` you have passed.
2. The [`set` function](https://react.dev/reference/react/useState#setstate) that lets you update the state to a different value and trigger a re-render.

## Pitfall

Calling the `set` function **does not** change the current state in the already executing code.It only affects what `useState` will return starting from the _next_ render.

```
function handleClick() {  

setAge(age + 1); // setAge(42 + 1)  

setAge(age + 1); // setAge(42 + 1)  

setAge(age + 1); // setAge(42 + 1)  

}
```

for the above code block:

Suppose the `age` is `42`. This handler calls `setAge(age + 1)` three times:

However, after one click, `age` will only be `43` rather than `45`! This is because calling the `set` function does not update the `age` state variable in the already running code. So each `setAge(age + 1)` call becomes `setAge(43)`.

To solve this problem, **you may pass an _updater function_** to `setAge` instead of the next state like this :

```
function handleClick() {  

setAge(a => a + 1); // setAge(42 => 43)  

setAge(a => a + 1); // setAge(43 => 44)  

setAge(a => a + 1); // setAge(44 => 45)  

}
```





https://react.dev/reference/react/useState