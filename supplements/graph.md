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
search, add, remove is O(height).
Inorder traversal is sorted array.

**Graph**: can be represented with array of edges, adjacency list/matrix, or general matrix where each (row, col) is node. We can use DFS but need to keep "seen" set to avoid infinite cycle.
O(n+e) time and space complexity.