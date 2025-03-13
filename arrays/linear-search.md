# Linear Search

```py
arr = [1, 2, 3, 4, 5]

def search(arr,element):
    n = len(arr)
    for i in range(n):
        if arr[i] == element:
            return i
    return -1

result = search(arr,3)
print(result)
```
TC - O(N)
SC - O(1)
