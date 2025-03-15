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

Trees are a data structure that link nodes in a parent/child relationship, in the sense that there are nodes that depend on or come off other nodes. - [freeCodeCamp](https://www.freecodecamp.org/news/data-structures-in-javascript-with-examples/#heading-trees)

A `Tree` represents a hierarchical tree structure, made up of root nodes, edges, parent & child nodes, leaves (leaf nodes), and more.

**Term definitions:**

- `Root`: The top node of a tree, it has no parent
- `Edge`: Arrows/Lines that connect nodes in a tree together
- `Child`/`Children`: Nodes linked by a parent node
- `Parent`: A node that links to another node
- `Sibling`: Nodes that share the same parent
- `Leaf Nodes`: Nodes at the end of branches with no children
- `Internal Nodes`: Nodes that have at least one child
- `Depth`: The distance between the root node and a given node
- `Height`: THe length of the longest path from a node to a leaf node - maximum `depth`

The code example below shows the creation of a Tree. We create a class called `TreeNode` to represent a single node in the tree. Each node has a value (`this.value`), a left pointer (`this.left`), and a right pointer (`this.right`). We initially set it to `null` until we give it a value.

Then, we build out the tree:

- We create a root node with the value `1`
- We assign children to it:
  - Left child → `2`
  - Right child → `3`
- Then, we add more children:
  - `2` has left child `4` and right child `5`.
  - `3` has left child `6` and right child `7`.

_Code example:_

```JavaScript
class TreeNode {
    constructor(value) {
        // data (value), left, right
        this.value = value;
        this.left = null;
        this.right = null;
    }
}

// creating the Tree
const root = new TreeNode(1);
root.left = new TreeNode(2);
root.right = new TreeNode(3);
root.left.left = new TreeNode(4);
root.left.right = new TreeNode(5);
root.right.left = new TreeNode(6);
root.right.right = new TreeNode(7);

/*
    the Tree looks like this:
          1
         / \
        2   3
       / \ / \
      4  5 6  7
*/
```

## Prompt 3

Any iterative function can be written recursively. Provide an example of an iterative function and the same function written recursively. Then, explain the benefits and/or drawbacks of each approach.

### Response 3

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
