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


dict is HashMap in Python - uses open addressing.
key needs to be immutable.

#### Counting
sliding window is for max and prefix sum hash map is for counting.

* [Python]() -> sort, reverse
a.sort()
and sorted(a)
"True" "False"
* [Algorithms]()
convert to Set to check unique O(n)