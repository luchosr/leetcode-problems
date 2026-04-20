# Create Hello World Function

## Description

Write a function `createHelloWorld`. It should return a new function that always returns `"Hello World"`.

## Examples

### Example 1

- **Input:** `args = []`
- **Output:** `"Hello World"`

**Explanation:**

```javascript
const f = createHelloWorld();
f(); // "Hello World"
```

The function returned by `createHelloWorld` should always return `"Hello World"`.

### Example 2

- **Input:** `args = [{},null,42]`
- **Output:** `"Hello World"`

**Explanation:**

```javascript
const f = createHelloWorld();
f({}, null, 42); // "Hello World"
```

Any arguments could be passed to the function but it should still always return `"Hello World"`.

## Constraints

- `0 <= args.length <= 10`

## Solution

```javascript
var createHelloWorld = function () {
  return function (...args) {
    return 'Hello World';
  };
};
const f = createHelloWorld();
f(); // "Hello World"
```

The **time complexity** is $O(1)$ (constant time) because the function performs a single operation regardless of the input. Even with the spread operator for arguments, they are never processed.

The **space complexity** is also $O(1)$ (constant space). While it creates a closure, it doesn't store any data that scales with the input size, and the return value is a static string.
