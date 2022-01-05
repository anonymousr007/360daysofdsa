# A. Alexey and Train

**Solution:** 

* The solution of this task is to basically implement what was written in the statement.
* Let dep_i be the moment of train departure from the station i (dep[0]=0 initially).
* Then train arrives at the current station i at moment ar[i] = dep[i] − 1 + (a[i] − b[i] − 1) + tm[i]
* Departure at moment dep[i] = max(b[i], ar[i] + b[i] − a[i] + 12).
* The answer is ar[n].

```python
for _ in range(0, int(input())):
    n = int(input())
    s = []
    for i in range(0, n):
        s.append(list(map(int, input().split())))
    times = list(map(int, input().split()))
    flag = 0
    res = 0
    for i in range(0, n):
        a, b = s[i]
        flag += ((a - res) + times[i])
        if i < n - 1:
            flag = max(flag + (0 - (a - b) // 2), b)
        res = b
    print(flag)

```
