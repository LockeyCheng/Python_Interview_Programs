**分析**

    添加一个flag记录每趟冒泡是否有数值交换，如果有数值交换则继续下一轮冒泡，否则表明列表已经有序，退出循环。

```python
def improved_bubble_sort(lst):
    lstlen = len(lst)
    flag = True
    while flag:
        flag = False
        for j in range(1,lstlen):
            if lst[j-1] > lst[j]:
                flag = True
                lst[j],lst[j-1] = lst[j-1],lst[j]
    return lst
```