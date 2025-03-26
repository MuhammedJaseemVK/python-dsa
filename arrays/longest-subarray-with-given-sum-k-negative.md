# Longest Subarray with given Sum K(Negative)

# Bruteforce
```py
nums = [2,3,5,1,9]
n = len(nums)
k = 10
 
temp_sub_array=[]
longest_subarray=[]
for i in range(n):
    temp_sub_array = []
    for j in range(i,n):
        temp_sub_array.append(nums[j])
        sum = 0
        for m in range(i,j+1):
            sum += nums[m]
        if sum==k:
            if len(temp_sub_array)>len(longest_subarray):
                longest_subarray=temp_sub_array
            break

print(longest_subarray)
print(len(longest_subarray))
```
TC - O(n^3)
SC - O(n)

# good bruteforce
```py
nums = [2,3,5,1,9]
n = len(nums)
k = 10

temp_sub_array=[]
longest_subarray=[]
for i in range(n):
    temp_sub_array = []
    sum = 0
    for j in range(i,n):
        temp_sub_array.append(nums[j])
        sum += nums[j]
        if sum==k:
            if len(temp_sub_array)>len(longest_subarray):
                longest_subarray=temp_sub_array
            break

print(longest_subarray)
print(len(longest_subarray))
```
TC - O(n^2)
SC - O(n)

# Better - hashmap
```py
nums = [2,3,5,1,9]
n = len(nums)
k = 10

hash_map ={}
sum = 0
max_subarray_length =0
for i in range(n):
    sum+=nums[i]
    if sum == k:
        max_subarray_length = i+1
    rem = sum - k
    if rem in hash_map:
        current_subarray_length = i - hash_map[rem]
        max_subarray_length =  max(max_subarray_length,current_subarray_length)
    if sum not in hash_map:
        hash_map[sum]=i

print(max_subarray_length)
```
TC - O(nlogn)
SC - o(n)
