## What is the output of x ? and why ?
```js
    function sum(){ return 1 + 1; }
    function multi(){ return 2 * 2; }

    let x = (sum(),multi());

    console.log(x) // output will be 4
```
**Why ?**   
`let x = (sum(), multi());`
This line is using the comma operator, which evaluates multiple expressions from left to right and returns the result of the last expression that is `multi() = 4`

```javascript

console.log(sum(), multi()); 

// output will be 2 4
```