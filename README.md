# work-application

1.) **What is functional programming** : Functional programming is a way of create reusable blocks of code and one good advantage of this is that it helps you with less repetition of code .
with the example provided below
```javascript
  //imaging you having a task of adding two numbers everyday
  let numone = 10, numTwo =30;
  let sum = numOne + numTwo //this process repeats everyday but with functional programming and is not maintainable or reusable
  
  function sumTwoNumbers(num1, num2){
    return num1 + num2
  }
  //the above code is going to return the result of two number everytime you invoke it
  sumTwoNumbers(10, 30) //returns 40
```

2.) **How do you update an array keeping functional programming principles in mind**: In javascript the `Array` datatype structure is mutable and has methods(functions) that we can use to 
manipule data or update data with.
```javascript
  
  const items = [
    {
      id: 1,
      name: 'Orange Juice'
    },
     {
      id: 2,
      name: 'Grape Juice'
    },
     {
      id: 3,
      name: 'Fresh Pickles'
    },
     {
      id: 4,
      name: 'Banana'
    },
  ]
  
  //create a function to update Banana to Water Melon Juice
  /**
 * @param {array} array array data to update
 * @param {string} value the value to update
 * @param {string} updateValue the update for value 😔(out of variable keywords to use)
 */
const updateItem = (array, value, updateValue) => {
  //filter element to find if the item exists in the array
  let exists = array.findIndex((element) => {
    return element.name === value.toLowerCase();
  });

  if (exists < 0) {
    return new Error(`${value.toLowerCase()} does not exist`);
  }

  //if value is present
  let newData = array.map((element) => {
    if (element.name === value.toLowerCase()) {
      return {
        ...element,
        name: updateValue.toLowerCase(0),
      };
    }
    return element;
  });
  return newData;
};

let example = updateItem(items, 'banana', 'creame juice');

console.log(example);

```
