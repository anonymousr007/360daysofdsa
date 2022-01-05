# B. Napoleon Cake

**Solution:**

* The i-th layer is drenched in cream if there is such j >= i that j − a[j] < i.
* Then we can calculate answers for all layers i in reverse order (from n to 1) and maintain minimum over all values j − a[j] as some variable mn.
* As a result, when we move from i+1 to i, we update mn=min(mn, i−a[i]) and then check that mn < i.

**Code**

```python
for _ in range(int(input())):
    n = int(input())
    arr = list(map(int,input().split()))
    ans = [0 for item in range(n)]
    j = n - 1
    temp = 0
    while j >= 0:
        temp = max(arr[j], temp)
        if arr[j] or temp:
            ans[j] = 1
            temp -= 1
        j -= 1
    print(*ans)
```
