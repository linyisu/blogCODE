---
title: "最长上升子序列"     
date: 2025-02-05 22:35:41
math: true
tags: 
  - 动态规划
  - 贪心
  - 二分
  - 最长上升子序列问题
categories: 
  - 模板
---

## 最长上升子序列问题（Longest Increasing Subsequence）

##### 动态规划	$O(n^2)$

如果一个上升子序列的最大值小于一个在它后面的数，那么这个数和这个子序列可以拼成一个更长的上升子序列。

例如一组数据：`1,2,4,1,3,4` 。

我们知道，`1,2,3` 为一个上升子序列，但是 3 后面的 4 和这个上升子序列拼接后可以组成一个更长的上升子序列。

所以，我们可以设计 $f(i)$，表示以第 $i$ 个数为结尾的最长上升子序列的长度。

再以上面的数据为例子，就可以列出表格：

|     n     |  1   |  2   |  3   |  4   |  5   |  6   |
| :-------: | :--: | :--: | :--: | :--: | :--: | :--: |
| **$a_n$** |  1   |  2   |  4   |  1   |  3   |  4   |
|  $f(n)$   |  1   |  2   |  3   |  1   |  3   |  4   |

**代码实现：**

- 读入数据；
- 大循环开始，从 1 到 n，计算 $f_i$，记得初始值是 1；
- 小循环，从 1 到 $i−1$，如果 $a_j$ 小于 $a_i$ 的话，说明这个数可以和 $f_i$ 组成上升子序列，则 $f_i$ 取 $max⁡(f_i,f_j+1)$；
- 寻找最大值；

```cpp
int LIS(int n)
{
    int ans = 0;
    vector<int> dp(n + 1, 1);
    for (int i=0;i<n;i++)
    {
        for (int j=0;j<i;j++)
            if (v[i] > v[j])
                dp[i] = max(dp[i], dp[j] + 1);
        ans = max(ans, dp[i]);
    }
    return ans;
}
```

##### 贪心+二分	$O(nlog(n))$

```cpp
int LIS(int n)
{
    vector<int> a;
    for (int i=0;i<n;i++)
    {
        auto it = lower_bound(all(a), v[i]);
        if (it != a.end())	*it = v[i];
        else	a.push_back(v[i]);
    }
    return a.size();
}
```

