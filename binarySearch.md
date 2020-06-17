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
int binarySearch(array<int,5>& list, int item)
{
	int low = 0;
	int high = list.size();

	while (low < high)
	{
		if (item < list[low] || item > list[high-1])
			return -1;
		int mid = (low + high) / 2;
		int guess = list[mid];

		if (guess == item)
			return mid;
		else if (guess < item)
			low = mid;
		else
			high = mid;
	}

	return -1;
}

int main()
{
	array<int,5> list = { 1,3,5,7,9 };
	cout << binarySearch(list,5) << endl;
	cout << binarySearch(list,2) << endl;
	return 0;
}
```
## 4.STL函数解析

### binary_search(begin,end,val)

- brief 返回有序数列中是否有某个值
- param begin有序数列起始地址
- param end 有序数列的终止地址
- param val 查找的数
- return bool 在有序数列中是否查找到val

### lower_bound(begin,end,val)

- brief 返回有序数列中第一个大于等于某数的下标
- param begin有序数列起始地址
- param end 有序数列的终止地址
- param val 查找的数
- return index 元素位置

### upper_bound(begin,end,val)

- brief 返回有序数列中第一个大于某数的下标
- param begin有序数列起始地址
- param end 有序数列的终止地址
- param val 查找的数
- return index 元素位置

> STL函数使用指导：    
>
> - 查找第一个大于x的元素的位置：upper_bound()。代码例如：    
>
>   pos = upper_bound(a, a+n, test) - a;    
>
> - 查找第一个等于或者大于x的元素：lower_bound()。   
>
> - 查找第一个与x相等的元素：lower_bound()且 = x。    
>
> - 查找最后一个与x相等的元素：upper_bound()的前一个且 = x。    
>
> - 查找最后一个等于或者小于x的元素：upper_bound()的前一个。    
>
> - 查找最后一个小于x的元素：lower_bound()的前一个。   
>
> - 单调序列中数x的个数：upper_bound() - lower_bound()。
>
> - sort()用于对数组排序，一般在二分查找之前使用
>
> - unique()，用于对数组去重，某些情况下可用到   



## 5.二分法扩展

### 三分法

在逼近函数的极大（极小）值，需要用到l,m1,m2,r四个点来确定。l、r可以是函数与坐标轴的两个交点，也是整个数据区间的两个端点。m1、m2认为是用来无限逼近极值的两个点。根据f(m1)和f(m2)与极值的大小比较，不断缩短区间(m1,m2)

### 二叉查找树

**中序遍历可以得到一个关键字的有序序列**

左子树上所有节点均小于根节点，右子树上所有节点均大于根节点
