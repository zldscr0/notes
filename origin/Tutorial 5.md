## Tutorial 5 图遍历相关

2022/4/19

无向图的DFS：TE、BE 有BE就有环

有向图的BFS：TE、BE、CE

无向图的BFS：TE、CE



##### Q1：

undirected graph G with n nodes , determine whether G is a forest in time O(n+m)

一个连通分量只要没有环就是树，判断是否有环，只要有BE就有环。

```
判断BE：
w.color == GRAY && v.parent!=w
```



##### Q2:

带权[price]顶点，cost[u],表示从u出发能到达的点中price最小的一个

![image-20220419165741765](C:\Users\hanabi\AppData\Roaming\Typora\typora-user-images\image-20220419165741765.png)

与邻居的cost比较，更新一个小的cost在邻居dfs过后，无论是什么颜色都比。



##### Q3：![image-20220419171204321](C:\Users\hanabi\AppData\Roaming\Typora\typora-user-images\image-20220419171204321.png)

是否有一个环包含e(uv)

去掉这个边，看看还能不能从u到v。



##### Q4：

![image-20220419172137838](C:\Users\hanabi\AppData\Roaming\Typora\typora-user-images\image-20220419172137838.png)

捣蛋的小孩：

①i讨厌j->i必须站在j前面 拓扑排序

②

方法一：关键路径问题，找到最大的eft即可

方法二：采用队列找拓扑排序的方式（ds讲的方法真的是太通俗易懂了



##### Q5：

![image-20220419173017307](C:\Users\hanabi\AppData\Roaming\Typora\typora-user-images\image-20220419173017307.png)

①遍历判断即可。

②线性时间判断是否存在一个点能到所有顶点

没有限制时间的话比较简单。

Ⅰ执行强连通分支算法，找出所有的强连通分支

收缩图是无环的，所以说存在拓扑排序，一定会有一个入度为0的顶点（这个顶点说的是收缩图的顶点，不是G上的顶点）。

Ⅱ

入度为0的点超过一个，说明不存在，只有一个的话，做一次dfs就知道可不可以了

（老师在讲这个习题时很奇怪，他在一开始提供的算法中并没有说需要先执行强连通算法，直接去找了入度为0的点有几个？如果多于1个的话确实是没有一个满足要求的点，但是只有1个或者是没有的时候的判断感觉存在着很大的问题。



##### Q6

![image-20220419174528520](C:\Users\hanabi\AppData\Roaming\Typora\typora-user-images\image-20220419174528520.png)

①遍历

②找到一个可以到达所有地方的点，跟Q5是一样的？是的



##### Q7

![image-20220419174732831](C:\Users\hanabi\AppData\Roaming\Typora\typora-user-images\image-20220419174732831.png)

①不是的，有环和存在这样的点不冲突

②转置之后调用强连通分量算法，找到入度为0的那一个，然后遍历

难点在于考场上能不能把强连通分量算法给写得比较明白（😄

（其实这里做复杂了

端点还有比较明确的定义就是它不到达其它顶点，所以直接看出度为0的点是否唯一且该店到其它点可不可达就可以了。

③O(n+m)

![image-20220419175534826](C:\Users\hanabi\AppData\Roaming\Typora\typora-user-images\image-20220419175534826.png)

##### Q8

![image-20220419175953215](C:\Users\hanabi\AppData\Roaming\Typora\typora-user-images\image-20220419175953215.png)

有向图，线性时间算法看是否所有城市都是可达的

①用图论的语言来描述这个图：

顶点表示城市，城市和城市之间有单向道路则它们在有向图中有一条边。

②互相可达说明是一个强连通图，做强连通片算法，看是不是成为了一个强连通片，也就是说从sink SCC开始能不能遍历到所有的顶点。



第二个问题是说town hall是否存在于一个sink SCC中，存在的话就说明是正确的（在一个连通分量里面转，转不到别的连通分量里去，这个也比较好判断，只要找出sink SCC ,看town hall是否在连通分量内即可。

