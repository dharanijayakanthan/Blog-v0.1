---
title: Currying in javascript
date: "2016-09-01T23:46:37.121Z"
layout: post
draft: false
path: "/posts/currying-in-js/"
category: "Javascript"
tags:
  - "Currying"
  - "Function currying"
description: "impliment a function like this 
add(1)(2)(3)(4)(5)(10);"
---
### CURRYING WITH RECURSION


Recenetly in an interview the guy interviewed me asked me tgo impliment a function like this 

```JAVASCRIPT
//output must be the sum of numbers passed as return arguments
add(1)(2)(3)(4)(5)(10); 
```


>If you are not familier with the way the function is called its currying. Its just the way of implementing a function where the result of the one function can be passed to the other.

*lets impliment a simple curry function*

```javascript
let add = (a) => {
    return function(b){
        console.log('a,b :', a, b);
        return a+b;
    }
}

console.log(add(2)(4));
```

*The above code printed six but how*


- Initially the add(2)(4) function call called add with the first argument
- Then the returned function is called with the secound argument 
- Since the returned function has access to both a and b it prints the sum




When adding another argument like add(2)(4)(6) we will get a type error we can actually have another function inside it and make it return a function which takes 'c'.

```javascript
let add = (a) => {
    return function(b){
        return function(c){
            return a+b+c;
        }
     }
 }

console.log(add(2)(4)(6));
```


Works perfectly but in order to add one more argument like add(1)(2)(3)(4), we need to again write a function and return it which is no way feasible and the number of arguments called with the returned function will change anytime.



>We can use something like recursion to solve this, We can call the add function inside the returned function with a base condition.



```javascript
let add = (a) => {
    return function(b){
        if(b == undefined) { return a;}
        return add(a+b)
    }
}

let x = add(2)(4)(6)(10)(32)(1);
console.log(x());
```

This will work perfectly for n number of classes the base codition 
checks if the b is undefined return last sum.






