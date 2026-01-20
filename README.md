# JAVASCRIPT-LOOPS

A for...in loop
  - Used when you need to loop over the properties or keys of an object.
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
