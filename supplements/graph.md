## Trees and Graphs



**DFS**: go deep first

Use recursion!
```
def dfs(node):
    if node == None:
        return

    dfs(node.left)
    dfs(node.right)
    return
```
* preorder: parent -> left -> right
* inorder: left -> parent -> right
* postorder: left -> right -> parent

Use stack if asked to do iterative approach.
O(n) time complexity and O(height) space complexity.

**BFS**: go wide first
Use queue.
```
queue = deque([root])
while queue:
    nodes_in_current_level = len(queue)
    # do some logic here for the current level

    for _ in range(nodes_in_current_level):
        node = queue.popleft()
        
        # do some logic here on the current node
        print(node.val)

        # put the next level onto the queue
        if node.left:
            queue.append(node.left)
        if node.right:
            queue.append(node.right)
```
O(n) time complexity and O(max node in level) space.

**BST**:
search, add, remove is O(height)
inorder traversal is sorted array.