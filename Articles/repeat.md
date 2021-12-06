*** Machine Translated
`repeat`允许我们连续执行任何一组命令*n*次。当与`pen-down`和`pen-up`元一起画图几何形状时， `repeat`特别有用。例如，如果我们想让海龟画一个正方形，我们将编写以下代码：



```
ask turtles [
	pen-down
	repeat 4 [
		right 90
		forward 5
	]
	pen-up
]
```


在下面的模型示例中，当单击*设置*按钮时，我们有 36 只海龟，它们最初被放置在圆形布局。当我们点击 go 按钮时，每只海龟向右转 1 度，向前移动 0.03 个单位 360 次。这种简单的重复行为产生了一个非常有趣的图形。