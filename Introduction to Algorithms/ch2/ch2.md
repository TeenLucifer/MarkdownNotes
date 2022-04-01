# Chapter 2
## 2.1 Insertion Sort
To be honest you should probably ***know all major sorting algorithms***, not just insertion sort. It's just basic knowledget and you never know when it can help.
（***需要去看所有排序的方法，因为那些是基础***）

### 2.1.1 插入排序伪代码和理解
```C++
for j = 2 to A.length
{
    key = A[j];
    i = j - 1;
    while(i > 0 && A[i] > key)
    {
        A[i + 1] = A[i];
        i = i - 1;
    }
    A[i + 1] = key;
}
```
想象手里拿一副已经排好顺序的牌，再摸一张牌按照从大到小或者从小到大的顺序比对插入进行排序。伪代码中的``while``从``i = j - 1``开始是因为key已经保存下一个待排数据，已排序的序列可以向``A[j]``位置移动一个位置，使序列中间有空间插入``key``。

### 2.1.2 冒泡排序

升序（降序同理）
```C++
for(int i = 0; i < A.length; ++i)
{
    for(int j = 0; j < A.length - i - 1; ++j)
    {
        if(A[j] > A[j + 1])
        {
            swap(A[j], A[j + 1]);
        }
    }
}
```
思想类比于水里泡泡浮上去，每趟是在未排序的数列中进行的。

### 2.1.3 选择排序

```C++
int min = 0;
for(int i = 0; i < A.length; ++i)
{
    min = i;
    for(int j = i + 1; j < A.length; ++j)
    {
        if(A[j] < A[min])
        {
            min = j;
        }
    }
    if(min != i)
    {
        swap(A[i], A[min]);
    }
}
```
每趟从未排序的数列中选出最小或最大的（即降序与升序的区别），放到已排序的数列末尾

### 2.1.4 希尔排序

1. 选择步长k，按照k将原始数列分割为不同长度的子序列，对子序列进行排序（一般用插入排序）
2. 逐步缩小步长，重复上一步，直至步长为1
3. 对数列整体进行排序（插入排序），使其有序

希尔排序的思想是先将数列分割为各子序列，对各子序列使用插入排序子算法，使整体排列大致有序，后再对整体进行使用插入排序。子算法使用插入排序的原因是，在数列短或整体有序的情况下，效率相对较高。

### 2.1.5 归并排序
### 2.1.6 快速排序
### 2.1.7 堆排序
### 2.1.8 计数排序
### 2.1.9 桶排序
### 2.1.10 基数排序

## 2.2 Analysis of Algorithms
You can skip the small introduction, but know the rest.

一个``for``或者``while``循环按照通常的方式（即由于循环头中的测试）退出时，执行测试的次数比执行循环体的次数多1

往往只考虑最坏情况运行时间，最坏情况运行给出了任何输入的运行时间的上限