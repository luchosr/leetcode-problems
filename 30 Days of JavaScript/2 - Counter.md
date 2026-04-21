# Counter

## Description

Write a function `createHelloWorld`. It should return a new function that always returns `"Hello World"`.

Given an integer `n`, return a `counter` function. This counter function initially returns `n` and then returns 1 more than the previous value every subsequent time it is called (`n`, `n + 1`, `n + 2`, etc).

## Examples

### Example 1

- **Input:** `n = 10`, `["call","call","call"]`
- **Output:** `[10,11,12]`

**Explanation:**

```
counter() = 10 // The first time counter() is called, it returns n.
counter() = 11 // Returns 1 more than the previous time.
counter() = 12 // Returns 1 more than the previous time.
```

### Example 2

- **Input:** `n = -2`, `["call","call","call","call","call"]`
- **Output:** `[-2,-1,0,1,2]`

**Explanation:**

```
counter() initially returns -2. Then increases after each subsequent call.
```

## Constraints

- `-1000 <= n <= 1000`
- `0 <= calls.length <= 1000`
- `calls[i] === "call"`

## Solution

```javascript
var createCounter = function (n) {
  let count = n;
  return function () {
    return count++;
  };
};
```

The **Time Complexity** is $O(1)$ per call because incrementing a variable and returning it is a constant time operation.

The **Space Complexity** is $O(1)$. However, it's important to note that this is a stateful closure. The variable count stays in memory as long as the returned function exists, but since it only stores a single numeric value, the space required does not scale with the input $n$ or the number of calls.
