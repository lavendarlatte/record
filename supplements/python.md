## Python

||Code Snippet|
|-|-|
|Checking null|if a == None: or if not a:|
|Sort|sorted(iterables, reverse=True) (returns list) or list.sort() (in-place)|
|Loop with index|for i, val in enumerate(list):
|Integer division| a // 2|
|Setting max value| ans = float("inf")|
|Boolean|True/False|
|Reverse list|list(reversed(list)) or list.reverse() (in-place)|
|Join list|''.join(list) <-> list.split("/")|
|Map|map(int, list)|
|Set|set(string), s.add(a)|
|Counter|collections.Counter(list)|
|Ternary|val if cond else val2|
|Range comparison|if low <= root.val <= high:|
|Lambda|min(a, b, key = lambda x: abs(target-x))|
|Inner function|can access variables in outer function|
|Square|a**2|
|Key check| key in dic|
|Building set from list| set(nums) is O(n)|
|Case|string.lower() and s.upper()|
|Split string|s.split("/"), O(N), will include empty string if char was repeated|
|ASCII|ord('a')|
there is recursion limit? be aware of this for dfs

list is dynamic
string is immutable so operation is O(n)
append to list is amortized O(1)

