# insertionSort(Recursive)
```py
def swap(arr,index):
    if(index==0):
        return
    if(arr[index-1]<arr[index]):
        return
    temp = arr[index]
    arr[index] = arr[index-1]
    arr[index-1]=temp
    swap(arr,index-1)

def insertionSort(arr,index,n):
    if index==n:
        return
    swap(arr,index)
    insertionSort(arr,index+1,n)

n=len(arr)
insertionSort(arr,1,n)
```
