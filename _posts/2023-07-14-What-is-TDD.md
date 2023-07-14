# What is TDD 

Test Driven Development aka TDD is a software development practice that focuses on creating unit test before developing the actual code. <br>
So you don't write a single line of program until you have the test.

##  Examples
So if you want to write a program that adds number. You will need to write the test cases first.

----------------
Writing the unit test with `jest` first
`sum.test.js`
```js
const sum = require("./sum");

test("properly adds two numbers", () => {
   expect(sum(1, 2)).toBe(3);
   expect(sum(0, 0)).toBe(0);
   expect(sum(-4, 2).toBe(-2);
   expect(sum(0.5, 0.1).toBe(0.6);                                                                               
   // other cases needed to
});
```

And write the program you wanted
`sum.js`
```js
function sum(a, b) {
  return a + b;
}

function helper() {
  console.log("Helper");
}

module.exports = sum;
```











