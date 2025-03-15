# Find the missing number in an array

# Bruteforce
```py
nums = [4,1,2,1,2]
n = len(nums)

unique_element = -1
for i in range(n):
    is_appearing_once = False
    for j in range(n):
        if i!=j and nums[i]==nums[j]:
            is_appearing_once = True
    if is_appearing_once == False:
        unique_element = nums[i]
        break
print(unique_element)
```
TC - O(N^2)
SC - O(1)

# Better - hash array
```py
nums = [4,1,2,1,2]
n = len(nums)

max_element = 0
unique_element = -1
for i in range(n):
    if max_element<nums[i]:
        max_element = nums[i]

hash_array = [0] * (max_element +1)

for i in range(n):
    hash_array[nums[i]] +=1
for i in range(len(hash_array)):
    if hash_array[i]==1:
        unique_element = i
        break
print(unique_element)
```
TC - O(n)
SC - O(max_element+1)

# Better - hashmap (Data structure)
```py
nums = [4,1,2,1,2]
n = len(nums)

hash_map = {}
for number in nums:
    if number not in hash_map:
        hash_map[number] =1
    else:
        hash_map[number]+=1
result = -1
for i in hash_map:
    if hash_map[i]==1:
        result=i
print(result)
```
TC - O(n)
SC - O((n/2)+1) since every element appears twice except one element which appears only once

# Optimized - using XOR
```py
nums = [4,1,2,1,2]
n = len(nums)

# a ^ a = 0
# a ^ 0 = a

xor = 0
for i in range(n):
    xor = xor ^ nums[i]
print(xor)
```
TC - O(N)
SC - O(1)
