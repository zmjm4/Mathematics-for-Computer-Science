#### Problem 1

(a)数量为
$$
10^9 - 8\times 9^8
$$
(b)剩余$14$本书有$15$个间隔，只要从这$15$各间隔中挑$6$个即可。



#### Problem 2

(a)假设编码的长度为$n-2$，那么数字树的元素为
$$
1,\ldots , n
$$
因为不在编码中的最大元素必然是叶节点，并且其父节点为编码的第一个元素，所以可以产生如下递归算法：

假设节点集为$V$，编码为长度为$|V|-2$的字符串$S$，记不在编码中且在$V$中的最大元素为$l$，那么$l$必为叶节点，并且其父节点为$S$第一个字符。现在对$V-\{l\}$和$S[1:]$递归调用该算法即可，终止条件为$|V|=2$。

(b)由(a)可知数字树和$n-2$位的编码一一对应，所以数字树的数量为
$$
n^{n-2}
$$


参考资料：https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-042j-mathematics-for-computer-science-fall-2005/lecture-notes/cp9wsol.pdf



#### Problem 3

(a)考虑长度为$n+k$的bit串，其中有$n$个$0$，$k$个$1$。记第$1$个$1$之前$0$的数量为$x_1$，第$i$个$1$和第$i-1$个$1$直接$0$的数量为$x_{i}$，那么必然有
$$
\sum_{i=1}^k x_i \le n
$$
于是构成了双射。

(b)定义
$$
\begin{aligned}
y_i & =\sum_{j=1}^i x_j
\end{aligned}
$$
即可。



#### Problem 4

(a)
$$
|X|\times |Y|
$$
(b)对于全函数$f$，$\forall x \in X$，$f(x)​$有定义。假设
$$
X= \{x_1,\ldots x_n\}
$$
$f$与如下向量一一对应
$$
(f(x_1),\ldots, f(x_n))  \in Y^{|X|}
$$
所以结论成立，因此
$$
|[X\to Y]| =|Y^{|X|}| =  |Y|^{|X|}
$$
(c)将函数视为从$X$的子集到$Y$的映射即可，元素为$k$的子集构成的映射数量为
$$
|Y|^k
$$
因为元素为$k​$的子集有$C_{|X|}^k​$个，所以总共数量为
$$
\sum_{i=1}^{|X|} C_{|X|}^k |Y|^k
=(1+|Y|)^{|X|} -1
$$
最后计算上式和$ |Y|^{|X|}​$的比值：
$$
\begin{aligned}
\frac{(1+|Y|)^{|X|} -1}{ |Y|^{|X|}}
&\le \frac{(1+|Y|)^{|X|} }{ |Y|^{|X|}}\\
&=\left(1+\frac{1}{|Y|}\right)^{|X|}\\
&\le 2^{|X|}
\end{aligned}
$$
所以数量级为
$$
O(2^{|X|})
$$
(d)对于一个全函数$f$，$\forall x\in X$，如果
$$
f(x) =1
$$
那么定义
$$
x\in B \subseteq X
$$
反之，对于$X$的子集$B$，定义
$$
f(x)=\begin{cases}
1 &x\in B\\
0 & x\notin B
\end{cases}
$$
所以一个全函数与$X$的一个子集一一对应，因此几个全函数就与$X$的幂集意义对应。

(e)假设
$$
X= \{x_1,\ldots x_n\}
$$
用向量的形式表示集合：
$$
(x_1,\ldots ,x_n)
$$
对于双射$f$，定义向量
$$
(f(x_1), \ldots , f(x_n))
$$
该向量即为一个置换。

反之，对于置换
$$
(x_1',\ldots ,x_n')
$$
定义双射$f​$：
$$
f(x_1) =x_1 ', f^{-1}(x_1')=x_1
$$
所以双射和置换构成一一对应关系，因此双射的数量为$n!$。

