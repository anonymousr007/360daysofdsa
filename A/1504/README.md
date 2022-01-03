# A. Déjà Vu

* If s is the character 'a' repeated some number of times, there is no solution. Otherwise, I claim either 'a' + s or s + 'a' is a solution (or both).
* Let's prove it. Assume for contradiction that 'a' + s and s + 'a' are both palindromes.
* Then the first and last characters of s are 'a'.
* Then the second and second to last characters of s are 'a'.
* Repeating this, we see that all characters of s are 'a', but we assumed we are not in this case. Therefore, the claim is true.
* The solution is simply to check if 'a' + s and s + 'a' are palindromes and output the correct one.
* Complexity is O(n).

```python
for t in range(int(input())):
    s = input()
    if set(s) == {'a'}:
        print("NO")
    else:
        print("YES")
        if s + 'a' == (s + 'a')[::-1]:
            print('a' + s)
        else:
            print(s + 'a')
```
