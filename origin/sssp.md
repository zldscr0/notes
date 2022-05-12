##### Djkstra算法解决单源最短路径问题（SSSP）



##### BestFS贪心遍历框架

```
BEST-FIRST-SEARCH():
Initialize the priority queue Frindge as empty;
Insert some node v to Frindge
while Findge not empty do:
	v:=Frindge.EXTRACT-MIN();
	<process v>;
	UPDATE-FRINDGE(v,Frindge)

subroutine UPDATE-FRINDGE(v,Frindge)begin
	foreach neighbor w of v which are Fresh do:
			Set the priority of w,insert w to Frindge;
	foreach neighbor w of v which are Fresh do:
		update thr priority of w in Frindge if neccessary;
```

##### 路由问题

边和点都有权重

```
UPDATE中，边权要加上顶点权重。
```

![image-20220507192551760](C:\Users\hanabi\AppData\Roaming\Typora\typora-user-images\image-20220507192551760.png)



eg:

![image-20220507192612449](C:\Users\hanabi\AppData\Roaming\Typora\typora-user-images\image-20220507192612449.png)

##### 管道问题

pipe problem 最小权重的边最大

![image-20220507192839995](C:\Users\hanabi\AppData\Roaming\Typora\typora-user-images\image-20220507192839995.png)



DAG有向无环图上的SSSP问题

![image-20220507192926860](C:\Users\hanabi\AppData\Roaming\Typora\typora-user-images\image-20220507192926860.png)

对顶点进行拓扑排序，有负权值也不会有问题。



考试不考与图无关的贪心算法，做题会哈哈。

![image-20220507193439861](C:\Users\hanabi\AppData\Roaming\Typora\typora-user-images\image-20220507193439861.png)

贪心策略：

1.最早时间优先

2.最短任务优先

3.最少冲突数优先



答案：按最短完成时间选择

排序：nlogn

