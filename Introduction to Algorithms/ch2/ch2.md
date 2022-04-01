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