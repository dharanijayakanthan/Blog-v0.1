---
title: Symbols in javascript
date: "2016-09-01T23:46:37.121Z"
layout: post
draft: false
path: "/posts/symbols-in-js/"
category: "Javascript"
tags:
  - "Symbols"
description: "You can not create a symbol using new keyword, You can have description for symbols and You can create symbol and use it inside a object like you do with other data types"
---



















### Symbol are new primitive data type introduced in es5 

    - Note that symbols are not objects they are primitives
        
        1. You can not create a symbol using new keyword
        
        2. You can have description for symbols
        
        3. You can create symbol and use it inside a object like you do with other data types
        
        4. You can not use symbols inside loop  for...in or foreach

        5. Symbols are unique

        6. If you create a symbol with for method if that symbol already exists it will return only the reference to it


##### Two methods of creating symbol

1. Using symbol function

```JAVASCRIPT

let x = Symbol('description');
console.log('symbol using symbol function :', x);

```
2. Using for 

```JAVASCRIPT

 let x = Symbol.for('description');
 console.log('symbol using for :', x);

```
 
> If we create two symbols which are same using the function way they will not be equal


```JAVASCRIPT

let x = Symbol('description');
let y = Symbol('description');
console.log('equal ?', x==y); //false

```

But if we create two symbols which are same using for method it will be equal the reason is because the for method will return us a reference to the existing symbol if both are same

```JAVASCRIPT

let x = Symbol.for('description');
let y = Symbol.for('description');
console.log('equal ? :', x==y); //true

```

##### We can add a symbol to an object

```JAVASCRIPT

let x = Symbol();
let obj = {name : 'danny', say : 'yo yo'};
obj[x] = 'this is symbol';
console.log('obj :', obj);

```

> Note*  you will not be able to iterate through and object and find symbol like you find with other keys

```JAVASCRIPT

let x = Symbol();
let obj = {name : 'danny', say : 'yo yo'};
obj[x] = 'this is symbol';
for (const key in obj) {
    if (obj.hasOwnProperty(key)) {
        const element = obj[key];
        console.log('key - has own property :', key); 
    }
    console.log('key property :', key); 
}
// will not have symbol in keys
console.log(Object.keys(obj));

```

##### Symbol are unique

```JAVASCRIPT

let x = Symbol('desc');
x = [1,2,1,21,2];
let y = Symbol('desc');
y = [1,2,1,21,2];
console.log('x == y :', x == y); //FALSE

```

    You can write a function to prototype method with a symbol and you can call it like Array[includes]();

> Note* you will not be able to use dot method which will call the inbuilt includes

```javascript

let keys = Symbol();

Object.prototype[keys] = () => {
    return 'this is not inbuilt keys method'
}

let obj = {name : 'danny', say : 'yo yo'};

console.log('Object.keys(obj) :',Object.keys(obj));
console.log('Object["keys"](obj) :',Object["keys"](obj));
console.log('Object[keys](obj) :',Object[keys](obj));

```










