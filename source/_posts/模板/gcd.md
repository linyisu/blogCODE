---
title: "gcd && ecgcd"     
date: 2025-02-05 13:20:33
math: true
tags: 
  - 数论
categories: 
  - 模板
---

#### exgcd还未更新！！

### gcd

##### 性质

①  $gcd(k* a, k* b) = k*gcd(a,b)$

②  $gcd(a,b) = gcd(a,a-b)$

性质②证明如下：

设 $a=p*c$, $b = q*c$, 则 $gcd(a,b) = c$, 且 $p,q$互质( $gcd(p,q)=1$ )。

由性质①可知，$gcd(a, a-b)=gcd(p*c, (p-q)*c)=c*gcd(p,p-q)$。

现在转化为：在 $gcd(p,q)=1$ 的情况下，证明 $gcd(p,p-q)=gcd(p,q)=1$ .

分类讨论：[以下证明出处](https://www.cnblogs.com/dancewithautomation/archive/2012/06/23/2559451.html)

① $p,q$ 没有为2的情况，所以 $p$ 与 $q$ 分别可以写成 $p=2m+1,q=2n+1$,（ $m$ 与 $n$ 皆为素数）, $p-q=2(m-n)$ ，是一个偶数，该偶数显然与 $q$ 互素。

② $p,q$ 有一个为2的情况，不妨假设 $q=2，p=2m+1,p-q=2m-1$ ,显然 $p,q$ 互素。

由此得证。



##### 结论

$gcd(a,b)=gcd(b,a\bmod b)$ 

##### 实现代码

```cpp
int gcd(int a, int b) {return (!b ? a : gcd(b, a % b));}
```

也可以使用`<algorithm>`库中的`__gcd()`函数

```cpp
#include <algorithm>
int g = __gcd(a, b);
```

