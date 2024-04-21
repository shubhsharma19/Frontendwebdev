## Arrays

- Arrays can hold many values at the same time. In other programming languages, Arrays could only store similar type of data but in JS arrays can even hold different types of values.
- Arrays start with index 0.
- Declaring an array in JS
    - `const array = [elements, elements, elements];`
- Assigning values to the end of the arrays: `array[last index] = value;`
- Note: We can manipulate values of an array declared with a const but we can’t reassign it.
    - **For example:**


    ```jsx
    const array = [1,3,4];
    
    // possible
    array[1]=2;
    array[2]=3;
    
    // not possible because its reassigning the entire array.
    array = [4,5,6];
    ```
    
- One more way to initialize an array is to use constructors
    - `const array = new Array(1,2,3);` This is because an array is an object in JS which means we can create its instance and use a constructor for that.

**Manipulating values of the array**

- We can use push method to push values at the last index of the array.
    - `array.push(element);`
- To delete last value from the array we can use pop method.
    - `array.pop(element);`
- To add the element in the beginning of the array
    - `array.unshift(element);`
- To check the values inside the array
    - `Array.isArray(arrayName);`
- To get the index of a specific element
    - `.indexof(element);`

**Some more useful array methods**
- `slice()`
- `splice()`
- `indexof()`
- `join('')`
- `flat()`
- `Array.from()`
- `Array.of()`
- `spread operator` -> `(...)` not a method but very useful in many cases.

> In situations where you want to data scrap `Array.from(”string”)` can be used to convert that data into array but if it takes an object then it might not work as expected.


## Destructuring arrays

Destructuring arrays is a way of taking out values out of an array without manipulating it.

```js
const arr = [1,2,3,4,5,6,7,8];

let [a,b,c] = arr; // 1, 2, 3

// skipping values with a comma
const [a, , c] = arr; // 1, 3

// swapping values
[a,c] = [c,a];

console.log(a, c) // 3, 1

function filteredArr (arr) {
  const newarr = arr.filter(val => val % 2 === 0)
  return newarr
}

// catching values from the function call and then destructuring
const [a, b, , c] = filteredArr (arr);
console.log(a, b, c); // 2, 4, 8

// destructuring nested values from arrays
const nestedArr = [2, 3, [4, 5, 6], [7, 8, 9]]
const [two,, [four,, six], [, eight]] = nestedArr; 
// [2, skipped3, [four, skipped5, six], [skipped7, eight]]

console.log(two, four, six, eight);
```
