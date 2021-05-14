*** Machine Translated
只要给定的报告指令报告为真`while`开始无限期地重复提供的一组规则（例如`ask` ）。如果报告指令报告为**false** ， `while`停止重复提供的规则。例如，如果我们要创建一个房地产市场模型，在此模型中，每个买家继续寻找房子直到找到足够便宜的房子，我们可以编写以下代码：



```
ask turtles [
	let found-home? false
	while [not found-home?] [
		move-to one-of patches with [residents = 0]
		if [price] of patch-here < my-budget [
			set found-home? true
		]
	]
]
```


在下面的模型示例中，我们以网格布局放置了许多乌龟。每只海龟都是紫色或绿色，根据周围乌龟的数量，它们是高兴还是难过。如果一只海龟有两个以上不同颜色的邻居。我们使用`while`原语使每只海龟在网格中移动，直到它们找到使它们高兴的位置。