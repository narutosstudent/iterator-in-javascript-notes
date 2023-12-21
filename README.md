# Iterable Protocol

- An **iterable** is an object that can return an iterator using the `[Symbol.iterator]()` method.

## Iterator Protocol

- An **iterator** is an object that knows how to access items from a collection one at a time, while keeping track of its current position within that sequence.
- An iterator must implement a `next()` method, which returns an object with two properties:
  - `value`: the next value in the iteration sequence.
  - `done`: a boolean value indicating whether or not there are more values to iterate over.

## Example of an Iterator

Consider an array in JavaScript; it is an iterable because it has a `[Symbol.iterator]()` method:

```javascript
const array = [10, 20, 30];
const iterator = array[Symbol.iterator]();

console.log(iterator.next()); // { value: 10, done: false }
console.log(iterator.next()); // { value: 20, done: false }
console.log(iterator.next()); // { value: 30, done: false }
console.log(iterator.next()); // { value: undefined, done: true }
```

In this example, the `iterator` variable is an iterator object for the array. Each call to `iterator.next()` returns the next element in the array until there are no more elements, at which point it returns `{ value: undefined, done: true }`.
