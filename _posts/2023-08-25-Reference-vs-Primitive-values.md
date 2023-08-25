# Reference vs Primitive values

This topic is very important when it comes to value management in Javascript. <br>
Because in programming we manage datas and values, it's important to copy and deliver correct data. <br>
So we have to understand what's the difference in between reference and primitive value when it comes to copying values.

## What are those values

| Primitive     | Reference |
| ------------- | --------- |
| String        | Object    |
| Number        | -> Array  |
| Boolean       |           |
| Undefined     |           |
| Null          |           |
| Symbol        |           |
|----------------|----------|
| **Stack**     | **Heap**  |

### What's different
So long story short, primitive values can be copied in a shallow way as a new value. <br>
But reference value has to be deep cloned to become a new value. Therefore, if you shallow copy a reference value, you are copying the pointer of the original value. so you will have to deal with original value being changed in the future in anytime.

### Example
- Primitive value
```js
let color = 'Blue';
let secondColor = color; 
color = 'Pink';

console.log(secondColor); //Blue
console.log(color); //Pink

- Reference value
```js
let obj = {color: 'Blue, number: 3, list: [1, 2, 3]}
let obj2 = obj; // Pointer of obj is getting copied
obj.color = 'Pink';

console.log(obj2) // {color: 'Blue, number: 3, list: [1, 2, 3]}
```

### How should I copy the actual value
- slice()
- spread operator
- Object.assign()

(If you have a nested array or an object you must manually clone every layer)






















