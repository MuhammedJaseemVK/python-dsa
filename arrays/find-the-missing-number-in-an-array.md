# Find the missing number in an array

# Bruteforce
```py
nums = [1,2,4,5]
n = 5

for i in range(1,n+1):
    is_not_in_array = True
    for j in range(len(nums)):
        if i == nums[j]:
            is_not_in_array = False
            break
    if is_not_in_array == True:
        print(i)
        break

TC - O(N^2)
SC - O(1)
```
TC - O(N^2)
SC - O(1)

# Bruteforce - hashmap
```py
nums = [1,2,4,5]
n = 5

hash_array = [0] * (n+1)
for i in range(n-1):
    hash_map[nums[i]] = 1
for i in range(1,n+1):
    if hash_array[i]!=0:
        print(i)
        break
```
TC - O(N)
SC - O(N)

# Optimized - using sum of natural numbers
```py
nums = [1,2,4,5]
n = 5
sum_of_array = 0
for i in range(len(nums)):
    sum_of_array+=nums[i]
sum_of_first_n_elements = (n*(n+1))//2
result =  sum_of_first_n_elements -sum_of_array
print(result)
```
TC - O(N)
SC - O(1)


# Optimized - using XOR
```py
nums = [1,2,4,5]
n = 5

# a ^ a = 0
# a ^ 0 = a

xor1 = 0
xor2 = 0
for i in range(n-1):
    xor1 = xor1 ^ nums[i]
    xor2 = xor2 ^ (i+1)
xor2 = xor2 ^ n
result = xor1 ^ xor2
print(result)
```
TC - O(N)
SC - O(1)
