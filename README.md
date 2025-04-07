# Technical Writing Assignment

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

Michael Stawowski: Questions 1 & 4

## Prompt 1

Imagine you are giving a brief lesson on Recursion to a relatively new programmer. In your lesson make sure to include the following:

- A formal definition of recursion (feel free to quote an official source like MDN)
- An example in code.
- An explanation of the code example.
- An explanation of the kinds of functions that are best solved using recursion.

### Response 1

Recursion is a programming technique for iterating over an operation by having function call itself repeatedly until it reaches a base case.

Here is an example in Javascript below:

```js
const factorial = (n) => {
  if (n === 0) {
    return 1;
  } else {
    return n * factorial(n - 1);
  }
};
```

In the code above, factorial calls itself with the arguments "n - 1" until it reaches the base case "n===0". This breaks the problem into smaller parts, multiplying the numbers until the full factorial is determined. Recursion is best used for problems that can be broken down into similar sub problems i.e factorial, fibonacci and traversing a tree structure.

## Prompt 2

Imagine you are giving a brief lesson on the Tree data structure to a relatively new programmer. In your lesson make sure to include the following:

- A formal definition of a Tree (feel free to quote an official source like MDN)
- Definitions for key terms like **root**, **leaf**, **depth**, and **height** as they relate to Trees
- An example in code.
- An explanation of the code example.

### Response 2

## Prompt 3

Any iterative function can be written recursively. Provide an example of an iterative function and the same function written recursively. Then, explain the benefits and/or drawbacks of each approach.

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

The three approaches to depth-first-search are inorder, preorder and postorder. The main difference in these three approaches is when the current node is visited. **Preorder** visits the node before the children, **Inorder** visits the node between the children and **Postorder** visits the node after children.

```js
function preorder(node) {
  if (!node) return;
  console.log(node.val);
  preorder(node.left);
  preorder(node.right);
}

function inorder(node) {
  if (!node) return;
  inorder(node.left);
  console.log(node.val);
  inorder(node.right);
}

function postorder(node) {
  if (!node) return;
  postorder(node.left);
  postorder(node.right);
  console.log(node.val);
}
```
