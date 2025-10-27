## Heaps

```
add o(log n)
remove min O(log n)
find min O(1) - min heap

# In Python, we will use the heapq module
# Note: heapq only implements min heaps
from heapq import *

# Declaration: heapq does not give you a heap data structure.
# You just use a normal list, and heapq provides you with
# methods that can be used on this list to perform heap operations
heap = []

# Add to heap
heappush(heap, 1)
heappush(heap, 2)
heappush(heap, 3)

# Check minimum element
heap[0] # 1

# Pop minimum element
heappop(heap) # 1

# Get size
len(heap) # 2

# Bonus: convert a list to a heap in linear time
nums = [43, 2, 13, 634, 120]
heapify(nums) -> O(n)

# Now, you can use heappush and heappop on nums
# and nums[0] will always be the minimum element

binary tree where parent node is always smaller than child node.
can access heap[0] without pop
max heap can be made with negative values. but be careful when using the value.

don't forget heap building time complexity
heap[1] is not second smallest!

heapq.heappush(heap, (val, key))
sorted_arr = sorted(arr, key = lambda num: abs(x - num))