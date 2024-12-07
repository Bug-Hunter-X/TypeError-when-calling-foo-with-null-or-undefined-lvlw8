# JavaScript Bug: Handling Nullish Values

This repository demonstrates a common JavaScript error related to handling nullish values (null or undefined). The original `foo` function throws a `TypeError` if it receives `null` or `undefined` as input because it tries to access the `.length` property of a nullish value. The solution shows how to handle this using optional chaining or nullish coalescing.

## Bug

The `bug.js` file contains the erroneous function:

```javascript
function foo(a) {
  if (a == null) {
    return 0; 
  }
  return a.length; 
}
```

Calling `foo(null)` or `foo(undefined)` will result in a `TypeError`.

## Solution

The `bugSolution.js` file provides a corrected version of the function that gracefully handles nullish values:

```javascript
function foo(a) {
  return a?.length ?? 0; 
}
```

This revised version uses optional chaining (`?.`) and the nullish coalescing operator (`??`) to safely access the `.length` property and provide a default value if `a` is null or undefined.  No `TypeError` will be thrown.