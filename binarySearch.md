# 二分查找
**输入是一个有序数列（二分查找仅对于有序数列有效）**
## 1.算法思想
通过区间端点与目标项的不断比较，来缩小区间，逼近目标

## 2.Python描述
```Python
def binarySearch(list,item):
  low = 0
  high = len(list)
  
  while low <= high:
    mid = (low+high) / 2
    guess = list[mid]
    if guess == item
      return mid
    else if guess > item
      high = mid
    else if guess <item
      low = mid
  return None
  
list = [1,3,5,7,9]
print(binarySearch(list,3))
print(binarySearch(list,-1))
```

## 3.C++代码实现
```C++
int binarySearch(int* a,int n,int i)
{
}
```
