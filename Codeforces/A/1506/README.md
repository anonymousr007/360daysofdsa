# A. Strange Table

* To find the cell number in a different numbering, you can find (r,c) coordinates of the cell with the number x in the numbering "by columns":
* r=((x−1)modr)+1, where amodb is the remainder of dividing the number a by the number b;
* c=⌈x/n⌉, where ⌈a/b⌉ is the division of the number a to the number b rounded up.
* Then, the cell number in numbering "by lines" will be equal to (r−1)∗m+c.

```python
from sys import stdin
import math

for i in range(int(stdin.readline())):
    table = list(map(int, stdin.readline().split()))
    X = math.ceil(table[2] / table[0])
    Y = table[2] - (X - 1) * table[0]
    print((table[1] * (Y - 1)) + X)
```
