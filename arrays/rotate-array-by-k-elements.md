# Left rotate an array by k places

# Bruteforce
```py
nums = [1,2,3,4,5,6,7]
n = len(nums)
k = 3

temp_array = []
for i in range(n-k,n):
    temp_array.append(nums[i])
for i in range(n-k-1,-1,-1):
    nums[i+k] = nums[i]
for i in range(len(temp_array)):
    nums[i] = temp_array[i]
print(nums)
```
TC - O(N)
SC - O(k)

# Reversal algorithm (optimized)
```py
nums = [1,2,3,4,5,6,7]
n = len(nums)
k = 3

def reverse(arr,start,end):
    while(start<end):
        temp =nums[start]
        nums[start] =nums[end]
        nums[end] = temp
        start+=1
        end-=1

reverse(nums,n-k,n-1)
reverse(nums,0,n-k-1)
reverse(nums,0,n-1)
print(nums)
```
TC - O(N)
SC - O(1)
