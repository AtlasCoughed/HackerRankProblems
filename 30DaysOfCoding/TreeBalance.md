### Given a binary tree, determine if it is height-balanced.

### For this problem, a height-balanced binary tree is defined as:

### A binary tree in which the depth of the two subtrees of every node never differ by more than 1.

## Example 1:

Given the following tree [3,9,20,null,null,15,7]:
```
    3
   / \
  9  20
    /  \
   15   7
   ```
Return true.

## Example 2:

Given the following tree [1,2,2,3,3,null,null,4,4]:
```
       1
      / \
     2   2
    / \
   3   3
  / \
 4   4
 ```
Return false.

### Thinking:

Can't be lopsided by more than one level. We can keep track by dividing the tree in half.
Read left to right.

```
const badValue = -1;
const checkHeight = (root) => {
    if(root === null){
        return badValue;
    }
    const leftHeight = checkHeight(root.left);
    if(leftHeight === badValue){
        return badValue;
    }
    
    const rightHeight = checkHeight(root.right);
    if(rightHeight === badValue){
        return badValue;
    }
    
    const heightDiff = leftHeight - rightHeight;
    if(Math.abs(heightDiff) > 1){
        return badValue;
    } else {
        return Math.max(leftHeight, rightHeight) + 1;
    }
}

const isBalanced = (root) => {
    return checkHeight(root) !== badValue;
}
```
** Optomized For Speed

```
const ans;

const isBalanced = function(root) {
    ans = true;
    dfs(root);
    return ans;
};

function dfs(root){
    if(!root) return 0;
    
    const a = root.left ? dfs(root.left) : 0;
    const b = root.right ? dfs(root.right) : 0;
 
    if(Math.abs(a-b) >1){
        ans = false;
    }
    return Math.max(a,b)+1;
}
```
