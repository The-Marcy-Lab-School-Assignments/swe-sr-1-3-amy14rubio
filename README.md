# swe-sr-1-3

## Setup

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/how-tos/working-with-assignments#how-to-work-on-assignments).

Here are some useful commands to remember.

```sh
npm i                   # install dependencies
git checkout -b draft   # switch to the draft branch before starting

git add -A              # add a changed file to the staging area
git commit -m 'message' # create a commit with the changes
git push                # push the new commit to the remote repo
```

## Question 1

Read the documentation for `findIndex` and `indexOf` on MDN:

- [findIndex](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex)
- [indexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf).

Explain the difference between the methods and explain when you would choose one over the other. Provide examples to enhance your response.

### Response

The main difference between `findIndex()` and `indexOf()` is that `findIndex()` allows you to define a **custom condition to locate an element**, while `indexOf()` searches for a **specific value in an array**. According to MDN, both array methods return the index of the **first matching element** and return `-1` when there is **no match found**.

### What are the parameters?

`indexOf()` accepts two parameters:

- `searchElement`: the desired element to be found in the array
- `fromIndex` (optional): the index to start searching from

`findIndex()` accepts:

- `callbackFn`: a function that iterates through each element of the array and returns true when a specific condition is met. This function receives three arguments:
  - `element`: the current element being iterated
  - `index`: the index of the current element
  - `array`: the array being iterated through
- `thisArg` (optional): the value to be used as `this`, in case you are to use it inside the callback function

### Here are some examples

If we want to check if an array of numbers contains a specific value, in this case the number 2, we could use both methods:

```js
const num = [1, 53, 9, 34, 2, 7];

num.findIndex((num) => num === 2); // → 4
num.indexOf(2); // → 4
```

However, the `findIndex()` method provides more flexibility when we want to test for a specific condition. For example, to find the first odd number:

```js
const num = [1, 56, 9, 21, 2, 7];

num.findIndex((num) => num % 2 !== 0); // → 0
```

Or we can be more specific and test to find the first odd number divisible by 7:

```js
const num = [1, 56, 9, 21, 2, 7];

num.findIndex((num) => num % 2 !== 0 && num % 7 === 0); // → 3
```

### When should each method be used?

- Use indexOf() when you need to find the position of a specific known value
- Use findIndex() when you need to find an element based on a condition or test
