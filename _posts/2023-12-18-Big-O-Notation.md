# Big-O Notation

### why learn big o? 
Best algorithm, solution -> enhance performance

### what does better mean?
- Faster?
- Less memory-intensive?
- More readable?
-> First two will be important

### The problem with time
- different machines will record diff times
- the same machine will record different times
- For fast algorithms, speed measurements may not be precise enough?

#### That's why we learn Big-O since we can't do time test for everything

### What is Big-O
Counting the number of simple operations the computer has to perform  
It allows us to talk formally about how the runtime of an algorithm grows as the inputs grow  
Counting operation  

linear f(n) = n
quadratic f(n) = n*2
constant f(n) = 1

##### Time complexity
- Arithmetic operations are constant
- Variable assignment is constant
- Acessing elements in an array (by index) or object (by key) is constant
- In a loop, the complexity is the length of the loop times the complexity of whatever happens inside of the loop

##### auxiliary space complexity 

###### Space complexity in JS (Rules of Thumb)
- Most primitives (booleans, numbers, undefined, null) are constant space
- Strings require O(n) space (where n is the string length)
- Reference types are generally O(n), where n is the length(for arrays) or the number of keys (for objects)

##### Logarithms
logn
