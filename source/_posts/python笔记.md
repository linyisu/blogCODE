---
title: python 笔记
date: 2024-07-22 22:30:00
tags:
  - python
  - 笔记
categories: 
  - 语法
---

## python笔记

```python
ord()	// 查看字符的ascii码
chr(num)	// 将ascii码转化为字符
```

```python
str.replace("","")	// (查找,替换)
```

```python
math.log10()	// 可用于求数字的位数,如下
math.floor(math.log10(num)) + 1
```

```python
node != None	// 判断链表节点是否为尾节点
```

```python
nums = [1,0,1,1,1]
for num in nums:
    ans = ans * 2 + num		// 二进制转十进制
```

```PYTHON
nums = [8,1,2,2,3]
arr = nums    
"""
上下二种写法不同,若对arr进行排序,上者仅是为nums起别名arr,而下者是重新开辟一个空间并将nums中的数据复制过去
"""
nums = [8,1,2,2,3]
arr = nums[:]
```

```python
for index,val in enumerate(nums): 	// emumerate函数应用实例 
            if val == target:
                ans.append(index)
```

```python
string.ascii_lowercase	// 给出由小到大的小写字母表
```

```python
# 左对齐
left_aligned = "{:<10}".format("Hello")
# 右对齐
right_aligned = "{:>10}".format("World")
# 居中对齐
center_aligned = "{:^10}".format("Python")
# 填充字符
filled = "{:*^10}".format("Text")
```

```
';'.join([a,b,c])	// join函数用法
>>  'a;b;c'
```

```python
"""
异或运算符（^）、与运算符（&）、或运算符（|）、反运算符（~）、右移运算符（＞＞）、无符号右移运算符（＞＞＞）
"""
```

```python
names = ["Alice","Bob","Bob"]
heights = [155,185,150]
return [name for name, _ in sorted(zip(names,heights), key = lambda i: i[1], reverse = True)]
```

```python
ans = [[0]*num for i in range(num)]		// 二维列表定义
```

```python
// 判断num的置位 (整数的二进制表示中的 1 就是这个整数的"置位")
def count_1(num: int) -> int:
    count = 0
    while num:
        if num & 1 == 1:
            count += 1
        num = num >> 1
    return count
```

```python
collections.Counter(nums)	// 返回的是字典
max(Counter(nums).values()) // 返回的是字典中按值排序的最大值
```

