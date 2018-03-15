### 题目要求

    判断输入的字符串或者数字是否是回文形式（回文串指正反都一样的字符串）

```python
def if_a_Palindrom(string):
    if not isinstance(string, basestring):
        string = str(string)
    front = 0
    end = len(string) -1
    while front<end:
        if string[front] != string[end]:
            return False
        front += 1
        end -= 1
    return True
```