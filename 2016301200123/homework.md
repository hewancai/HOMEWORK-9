# 	第五章

## 课后习题

### P3

| 步骤 | N'      | D(t), p(t) | D(u), p(u) | D(v), p(v) | D(w), p(w) | D(y), p(y) | D(z), p(z) |
| ---- | ------- | ---------- | ---------- | ---------- | ---------- | ---------- | ---------- |
| 0    | x       | ∞          | ∞          | 3, x       | 6, x       | 6, x       | 8, x       |
| 1    | xv      | 7, v       | 6, v       |            | 6, x       | 6, x       | 8, x       |
| 2    | xvu     | 7, v       |            |            | 6, x       | 6, x       | 8, x       |
| 3    | xvuw    | 7, v       |            |            |            | 6, x       | 8, x       |
| 4    | xvuwy   | 7, v       |            |            |            |            | 8, x       |
| 5    | xvuwyt  |            |            |            |            |            | 8, x       |
| 6    | xvuwytz |            |            |            |            |            |            |

### P5

节点z的表初始状态如下，此时节点z还没有从节点v、x收到任何东西，所以第二、三行表项中被初始化为无穷大。

<table>
    <caption align="top">节点z的表</caption>
    <tr>
        <th></th>
        <th colspan=6>到…开销</th>
    </tr>
    <tr>
        <th rowspan=4>从</th>
		<th></th> <td>u</td><td>v</td><td>x</td><td>y</td><td>z</td>
    </tr>
    <tr>
        <th>z</th> <td>∞</td><td>6</td><td>2</td><td>∞</td><td>0</td>
    </tr>
	<tr>
        <th>v</th> <td>∞</td><td>∞</td><td>∞</td><td>∞</td><td>∞</td>
    </tr>
	<tr>
        <th>x</th> <td>∞</td><td>∞</td><td>∞</td><td>∞</td><td>∞</td>
    </tr>
</table>

初始化后，每个节点向它的邻居发送其距离向量，其中包括节点v、x分别向节点z发送自己的初始状态下的距离向量。节点z接收到更新后，重新计算它自己的距离向量，节点z的表更新如下。

<table>
    <caption align="top">节点z的表</caption>
    <tr>
        <th></th>
        <th colspan=6>到…开销</th>
    </tr>
    <tr>
        <th rowspan=4>从</th>
		<th></th> <td>u</td><td>v</td><td>x</td><td>y</td><td>z</td>
    </tr>
    <tr>
        <th>z</th> <td>7</td><td>5</td><td>2</td><td>5</td><td>0</td>
    </tr>
	<tr>
        <th>v</th> <td>1</td><td>0</td><td>3</td><td>∞</td><td>6</td>
    </tr>
	<tr>
        <th>x</th> <td>∞</td><td>3</td><td>0</td><td>3</td><td>2</td>
    </tr>
</table>

理想、简化的情景下，节点v、x在节点z更新距离表的同时也更新了自己的表，并再一次通知邻居z这个变化，节点z接收到更新后，重新计算它自己的距离向量，节点z的表更新如下。

<table>
    <caption align="top">节点z的表</caption>
    <tr>
        <th></th>
        <th colspan=6>到…开销</th>
    </tr>
    <tr>
        <th rowspan=4>从</th>
		<th></th> <td>u</td><td>v</td><td>x</td><td>y</td><td>z</td>
    </tr>
    <tr>
        <th>z</th> <td>6</td><td>5</td><td>2</td><td>5</td><td>0</td>
    </tr>
	<tr>
        <th>v</th> <td>1</td><td>0</td><td>3</td><td>3</td><td>5</td>
    </tr>
	<tr>
        <th>x</th> <td>4</td><td>3</td><td>0</td><td>3</td><td>2</td>
    </tr>
</table>

比较特殊的是，节点v、x的距离表经历一次初始化、一次更新后便不会更新了，所以它们不会向节点z发送第三次通知。节点z的距离表稳定，算法进入静止状态。

### P9

不会。DV算法好消息传播得快，坏消息传播得慢，因为后者会产生路由选择环路，使得某些节点基于“历史信息”反复计算，从到导致无穷计数问题。

相当于将一条链路的开销从∞减小到一个有限值，减小一条链路的开销不会导致无穷计数问题。