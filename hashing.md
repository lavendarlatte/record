### Hashing
```python
from collections import defaultdict
counts = defaultdict(int)
len(counts)
for key in counts:
```
```python
counts = {}
counts.get(key, 0 /* default value */)
dictionary.values() doesn't actually return a list, but actually a view object. We need to convert it to a list first.
```
```
array = []
max(array) -> O(n)
sorted(array)
integer division: //
enumerate(array)

sorted(string) returns list
''.join(sorted(word))

ans = float("inf")

digit sum: key = sum(map(int,list(str(num))))
```

dict is HashMap in Python - uses open addressing.


#### Counting
sliding window is for max and prefix sum hash map is for counting.