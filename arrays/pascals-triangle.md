# Pascal's Triangle

## Variation 1: Given row number r and column number c. Print the element at position (r, c) in Pascal’s triangle.

# better
```py
def factorial(n):
    if n == 0:
        return 1
    return n * factorial(n-1)

n_factorial = factorial(n)
r_factoral = factorial(r)
n_r_factoral = factorial(n-r)

result = n_factorial/(r_factoral * n_r_factoral)
print(result)
```
TC - O(n) + O(r) + O(n-r)
SC - O(1)

# Optimized
```py
n = 5
c = 2

def findNCR(n,r):
    if r > n-r: # reduce the loop even further
        r = n-r
    result = 1
    for i in range(r):
        result = result * (n-i)
        result = result // (i+1)
    return result

result = findNCR(n-1, c-1) # 1-indexed to 0-indexed
print(result)
```
TC - O(c)  - where c is the number choosen.
SC - O(1)

## Variation 2: Given the row number n. Print the n-th row of Pascal’s triangle.

# Better
```py
#
n = 5

def findNCR(n,r):
    if r > n-r: # reduce the loop even further
        r = n-r
    result = 1
    for i in range(r):
        result = result * (n-i)
        result = result // (i+1)
    return result
row = []
for j in range(n):
    result = findNCR(n-1, j) # 1-indexed to 0-indexed
    row.append(result)
print(row)
```
TC - O(n*c)  - where c is the number choosen.
SC - O(1)

# Optimized
```py
n = 5
row = [1]
result = 1
for i in range(n):
    result = result * (n-i)
    result = result // (i+1)
    row.append(result)

print(row)
```
TC - O(n)
SC - O(1)

## Variation 3: Given the number of rows n. Print the first n rows of Pascal’s triangle.

# Better
```py
n = 5
n = n+1

def find_ncr(n,r):
    if r < n-r:
        r = n-r
    
    result = 1

    for i in range(r):
        result = result * (n-i)
        result = result // (i+1)
    
    return result

pascals_triangle = []
for row in range(n):
    result = []
    for col in range(row):
        result.append(find_ncr(row-1,col))
    pascals_triangle.append(result)

for i in range(n):
    for j in range(i):
        print(pascals_triangle[i][j],end=',')
    if i!=0:
        print()
```
TC - O(n*n*r)
SC - O(1)

# optimized
```py
n = 5
pascals_triangle = []
for i in range(n):
    result = 1
    row = [1]
    for j in range(i):
        result = result * (i-j)
        result = result // (j+1)
        row.append(result)
    pascals_triangle.append(row)


for i in range(n):
    for j in range(i+1):
        print(pascals_triangle[i][j],end=',')
    print()
```

TC - O(n*n)
SC - O(1)
