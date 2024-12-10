# Merge sort
```py
def merge(nums,low,mid,high):
    left=low
    right=mid+1
    temp=[]
    while(left<=mid and right<=high):
        if(nums[left]<=nums[right]):
            temp.append(nums[left])
            left+=1
        else:
            temp.append(nums[right])
            right+=1
    while(left<=mid):
        temp.append(nums[left])
        left+=1
    while(right<=high):
        temp.append(nums[right])
        right+=1
    for i in range(low,high+1):
        nums[i]=temp[i-low]
    
def mergeSort(nums,low,high):
    if(low<high):
        mid=(low+high)//2
        mergeSort(nums,low,mid)
        mergeSort(nums,mid+1,high)
        merge(nums,low,mid,high)

n=len(nums)
mergeSort(nums,0,n-1)
```
