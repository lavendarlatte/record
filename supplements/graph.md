## Trees and Graphs

Use recursion!

**DFS**: go deep first 
```
def dfs(node):
    if node == None:
        return

    dfs(node.left)
    dfs(node.right)
    return
```
preorder: parent -> left -> right
inorder: left -> parent -> right
postorder: left -> right -> parent

**BFS**: go wide first