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
## 4.STL函数解析
### binary_search(arr[],size,val)
- brief 返回有序数列中是否有某个值
- param arr 有序数列
- param size 有序数列的大小
- param val 查找的数
- return bool 在arr中是否查找到index
### lower_bound(arr[],size,val)
- brief 返回有序数列中第一个大于等于某数的下标
- param arr 有序数列
- param size 有序数列的大小
- param val 查找的数
- return int 下标
### upper_bound(arr[],size,val)
- brief 返回有序数列中第一个大于某数的下标
- param arr 有序数列
- param size 有序数列的大小
- param val 查找的数
- return int 下标

>STL函数使用指导：    
>　（1）查找第一个大于x的元素的位置：upper_bound()。代码例如：    
>　　　　　　　pos = upper_bound(a, a+n, test) - a;    
>　（2）查找第一个等于或者大于x的元素：lower_bound()。   
>　（3）查找第一个与x相等的元素：lower_bound()且 = x。    
>　（4）查找最后一个与x相等的元素：upper_bound()的前一个且 = x。    
>　（5）查找最后一个等于或者小于x的元素：upper_bound()的前一个。    
>　（6）查找最后一个小于x的元素：lower_bound()的前一个。   
>　（7）单调序列中数x的个数：upper_bound() - lower_bound()。   
