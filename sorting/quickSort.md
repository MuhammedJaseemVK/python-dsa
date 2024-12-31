# quickSort
```py
def quickSort(self,arr,low,high):
    # code here
    if(low<high):
        partition_index = self.partition(arr,low,high)
        self.quickSort(arr,low,partition_index-1)
        self.quickSort(arr,partition_index+1,high)

def partition(self,arr,low,high):
    i=low
    j=high
    pivot=arr[low]
    while(i<j):
        while(arr[i]<pivot and i<j):
            i+=1
        while(arr[j]>=pivot):
            j-=1
        if (i<j):
            temp=arr[i]
            arr[i]=arr[j]
            arr[j]=temp
    temp = pivot
    pivot = arr[j]
    arr[j]=temp
    return j
n=len(nums)
quickSort(nums,0,n-1)
```
