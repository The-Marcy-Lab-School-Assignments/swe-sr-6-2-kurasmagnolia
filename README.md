<!-- @format -->

# Technical Writing Assignment

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

## Prompt 1

Imagine you are giving a brief lesson on Recursion to a relatively new programmer. In your lesson make sure to include the following:

- A formal definition of recursion (feel free to quote an official source like MDN)
- An example in code.
- An explanation of the code example.
- An explanation of the kinds of functions that are best solved using recursion.

### Response 1

## Prompt 2

Imagine you are giving a brief lesson on the Tree data structure to a relatively new programmer. In your lesson make sure to include the following:

- A formal definition of a Tree (feel free to quote an official source like MDN)
- Definitions for key terms like **root**, **leaf**, **depth**, and **height** as they relate to Trees
- An example in code.
- An explanation of the code example.

### Response 2

## Prompt 3

Any iterative function can be written recursively. Provide an example of an iterative function and the same function written recursively. Then, explain the benefits and/or drawbacks of each approach.

The benefits of using the `iterative` approach is it being more efficient, where it generally runs faster by avoiding the overhead of function calls and call stack usage. It's also easier to debug and understand because of developers familiarity with the approach. However, a drawback is that it can be verbose in some problems that can be more naturally expressed recursively, making the function need extra data structures.

For `recursion`, a benefit is that it divides problems into smaller subproblems naturally (divide-and-conquer method). This is useful for algorithms like quick sort and binary search, make it easier to solve and understand. As for its drawbacks, recursive approaches can lead to high memory usage, because every recursive call adds a new function call to the call stack, consuming memory. Additionally, each function call adds a new frame to the call stack, leading to potential stack overflow if the recursion depth is too large.

_Iterative approach:_

```JavaScript
const reverseString = (str) => {
    let reversed = "";
    for (let i = str.length - 1; i >= 0; i--) {
        reversed += str[i]; // append characters in reverse order
    }
    return reversed;
}

console.log(reverseString("hello")); // output: "olleh"
```

_Recursive method:_

```JavaScript
const reverseString = (str) => {
    if (str.length === 0) return ""; // base case: empty string
    return str[str.length - 1] + reverseStringRecursive(str.slice(0, -1)); // take last char + recurse on the rest
}

console.log(reverseString("hello")); // output: "olleh"

```

### Response 3

## Prompt 4

Depth-first-search is an algorithm of traversing through a tree that explores as far as possible along a single branch before backtracking and exploring other branches. The three approaches for depth-first-search are "inorder", "preorder", and "postorder".

Using this tree as an example, explain the differences between these three approaches, providing implementations of each (recursive or iterative, its up to you but one of them is definitely cleaner).

```
    A
   / \
  B   C
 / \   \
D   E   F
```

### Response 4
