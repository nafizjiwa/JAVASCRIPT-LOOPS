# JAVASCRIPT-LOOPS
### for loop
- Repeats a block of code certain # of times.

        for (initialization; condition; increment or decrement) {
          // code block to be executed
        }
#### 3 PARTS:
* initialization - initialize a counter variable to keep track of # of loops run.
  * before loop starts
+ condition - evaluates true to continue loop.
  * before each iteration
- increment or decrement statement - increase or decrease counter variable
  * after each iteration
### nested for loops

### for...of loop
- To loop over values in ARRAYS, and STRINGS. (iterables)

      for (const variable of iterable) {
        // code block to be executed
      }
- Variable is the value from the iterable being looped and examine
    1. A value in array
        *const numbers = [1,2,3,4,5];
          
          for (const num of numbers) {
            console.log(num);
          }
    2. A character in a string
       * const str = 'gooogle';
          
          for (let char of str) {
            console.log(char);
          }

 
- Example

        function getVowelCount(sentence) {
              const vowels = 'aeiouAEIOU'
              let number = 0;
              for(let char of sentence){
                if(vowels.includes(char)){
                  number += 1;
                }   
              }
           return number;
        }
          
### A for...in loop
  - To loop over the `PROPERTIES` or `KEYS` of an object.
  - Not good for elements of an array use for...of loop or forEach, map, filter, reduce

      for (property in object) {
        // code block to be executed
      }

      const person = {
          name: 'John',
          age: 30,
          address: {
            street: '123 Main St',
            city: 'Anytown',
            state: 'CA'
            }
        };

        function isObject(obj) {
          return typeof obj === 'object' && !Array.isArray(obj) && obj !== null;
        }
        
        for (const prop in person) {
          //check if the property is an object as address it
          //address has nested properties
          if (isObject(person[prop])) {
            for (const nestedProp in person[prop]) {
              console.log(person[prop][nestedProp]);
            }
          } else {
            console.log(person[prop]);
          }
        }

### A while loop 
  - Runs a block of code if condition is true.
  - All while loops are used when the # of code blocks to run is unknown 

    while (condition) {
      // code block to be executed
    }
    
    let counter = 0;
    while(counter < 5) {
      console.log(counter);
      counter++;
    }
- check if condition is true then run the block of code

### do...while loop
  - Execute the code at least once

    let counter = 0;
    do {
      console.log(counter);
      counter++;
     } while (counter < 5);
- Run the code in the do block then check condition

### break and continue statements
#### break
- break statement to `EXIT` a loop early
- In an array, use it exit the loop once you find the value.

    for (let i = 0; i < 10; i++) {
      if (i === 5) {
        break;
      }
      console.log(i);
    }

- Use labels to specify which loop you want to break or continue.

      outerLoop: for (let i = 0; i < 3; i++) {
        innerLoop: for (let j = 0; j < 3; j++) {
          if (i === 1 && j === 1) {
            break outerLoop;
          }
          console.log(`i: ${i}, j: ${j}`);
        }
      }
#### continue
- continue statement to `SKIP` the current iteration and move to the next one.

      for (let i = 0; i < 10; i++) {
        if (i === 5) {
          continue;
        }
        console.log(i);
      }
