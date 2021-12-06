*** Machine Translated
`neighbors4`报告一个主体集合，其中包含在北、东、西和南方向围绕主体当前格子的四个补丁。海龟和斑块都可以使用这个报告指令。例如，如果我们想创建一个模型，其中火从一个格子蔓延到它的邻居，我们将编写以下代码：



```
ask patches [
	if pcolor = red [
		ask neighbors4 [
			if pcolor = green [
				set pcolor red
			]
		]
	]
]
```


使用`neighbors4`时要记住的事情：

- 即使我们在`ask turtles`上下文中使用它， `neighbors4`也将始终返回补丁。如果您希望主体看到相邻的海龟，您可以使用`turtles-on neighbors4` 。
- 还有一个`neighbors`关键字报告所有八个相邻的补丁。
- 当使用`neighbors4`作为世界边缘的格子时，请注意*世界包装*会将模型另一端的格子返回为其邻居。如果关闭*world-wrapping* ，则格子将返回两个补丁（如果它在角落上）或三个补丁（如果它在边缘）。


在下面的模型示例中，火灾在森林中蔓延。着火的格子会沿着包含树木的主要方向蔓延到其相邻的补丁。如果火灾格子有棕色邻近碎片指示地面，它会变成接地片灰色指示森林火灾的边缘。