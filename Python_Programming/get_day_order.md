### 题目要求

    给定一个日期字符串（eg：2013-12-31），判断输入日期是当年中的第几天？

**分析**

	1.对于输入，一定要谨记一条，所有的用户输入都是不可信的，所以一定要做好验证和异常处理
	2.对于以上格式的输入应该怎么去分割出我们需要的年月日整形数值
	3.对于单个日期数值的合理性判定
	4.对特殊输入特殊处理，比如月份为1，则可以直接返回day
	5.如果输入月份大于1，应该怎么考虑求和（列表求和）
	6.最后也很重要的一点，闰年和平年的判定一定要记准喽，这关系到当月份大于2的时候是否要多加一天


```python
def get_day_order(dateStr):
    try:
        year, month, day = map(int, dateStr.split('-'))
        #对于字符串的分割结果依然是字符列表，需要将字符列表转换为整形列表，否则后面执行求和操作出抛出异常
    except:
        return 'Not a legal date string!'
    days = [31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
    if year <1:
        return 'Ivalid year!'
    if month <1 or month >12:
        return 'Ivalid month!'
    if day>days[month-1] or day<1:
        return 'Ivalid day!'
    if month =1:
    #特殊情况特殊处理，如果不做处理的话下一步的列表求和是有缺陷的，因为当月份为1的时候reduce()函数的传值会出现空序列抛出异常
        return day
    fullMonth = month - 1
    result = reduce(lambda x,y:x+y,days[0:fullMonth])+day
    if not ((year % 400 == 0) or ((year % 4 == 0) and (year % 100 != 0))):
    #对于闰年的判断一定要记牢；能被400整除或者能被4整除但是不能被100整除
        if month > 2:
            result -= 1
        if month ==2 and day >28:
            return 'Ivalid days in Febrary!'
    return result
```