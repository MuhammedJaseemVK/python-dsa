# Move all Zeros to the end of the array

```py
nums = [1 ,0 ,2 ,3 ,0 ,4 ,0 ,1]
n = len(nums)

# count_of_zeros = 0
# result_array = []
# for i in range(n):
#     if nums[i] != 0:
#          result_array.append(nums[i])
# count_of_zeros = n - len(result_array)
# for i in range(count_of_zeros):
#     result_array.append(0)
# print(result_array)
```
TC - O(N)
SC - O(x) where x is the number of non_zero elements

# Two pointer (Optimized)
```py
nums = [1 ,0 ,2 ,3 ,0 ,4 ,0 ,1]
n = len(nums)

def move_zeros_to_end(n,arr):    
    left = -1
    for i in range(n):
        if(nums[i]==0):
            left = i
            break
    # non zero elements
    if left == (-1):
        return nums

    right = left+1
    while(right<n):
        if(nums[right]!=0):
            temp = nums[left]
            nums[left] = nums[right]
            nums[right] = temp
            left+=1
        right+=1
    print(nums)
move_zeros_to_end(n,nums)
```
TC - O(N)
SC - O(1)
