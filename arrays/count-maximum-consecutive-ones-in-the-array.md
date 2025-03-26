# Count Maximum Consecutive One's in the array

```py
nums = [1, 1, 0, 1, 1, 1]
n = len(nums)

count = 0
max_count = 0
for i in range(n):
    if nums[i]==1:
        count+=1
    else:
        count=0
    max_count = max(count,max_count)
print(max_count)
```
TC - O(n)
SC - O(1)
