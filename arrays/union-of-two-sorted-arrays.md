# Union of Two Sorted Arrays

# Bruteforce - using hash map
```py
arr1 = [1,2,3,4,5]
arr2 = [2,3,4,4,5]

frequency = {}
result_array = []

for i in arr1:
    frequency[i] = frequency.get(i,0) + 1
for i in arr2:
    frequency[i] = frequency.get(i,0) + 1
for unique_element in frequency:
    result_array.append(unique_element)
print(result_array)
```
TC - O((m+n)log(m+n))
SC - O(m+n) where m,n are sizes of arrays

# Bruteforce - using set
```py
arr1 = [1,2,3,4,5]
arr2 = [2,3,4,4,5]

unique_elements = set()
result_array = []

for i in arr1:
    unique_elements.add(i)
for i in arr2:
    unique_elements.add(i)
for i in unique_elements:
    result_array.append(i)
print(result_array)
```
TC - O((m+n)log(m+n))
SC - O(m+n) where m,n are sizes of arrays

# Optimized - using two pointer
```py
# Optimized
arr1 = [1,2,3,4,5]
arr2 = [2,3,4,4,5]

m = len(arr1)
n = len(arr2)

result_array = []
hash_map = set()

left = 0
right = 0

while left<m and right<n:
    if arr1[left]<=arr2[right]:
        element = arr1[left]
        if len(result_array) == 0 or result_array[len(result_array)-1] != element:
            result_array.append(element)
        left +=1
    else:
        element = arr2[right]
        if len(result_array) == 0 or result_array[len(result_array)-1] != element:
            result_array.append(element)
        right +=1

while left<m:
    element = arr1[left]
    if len(result_array) == 0 or result_array[len(result_array)-1] != element:
        result_array.append(element)
    left +=1

while right<n:
    element = arr2[right]
    if len(result_array) == 0 or result_array[len(result_array)-1] != element:
        result_array.append(element)
    right +=1

print(result_array)
```
TC - O(m+n)
SC - O(1)
