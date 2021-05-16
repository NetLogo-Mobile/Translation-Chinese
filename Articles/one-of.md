*** Machine Translated
`one-of`报告从提供的主体集合或列表随机选择的成员。例如，如果我们正在创建一个森林火灾模型，其中在随机格子发生火灾，我们将编写以下代码：



```
create-trees 100 [
	set shape "tree"
	set color green
	move-to one-of patches
]
ask one-of trees [
	set color red
]
```


使用以下`one-of`时要记住的事情：

- 我们还可以将`one-of`与列表一起使用。例如，如果我们希望每只海龟都从预定列表选择随机颜色，则可以编写以下代码： `ask turtles [set color one-of [red green blue yellow]]` 。
- 如果`one-of`对空主体集合或列表时，会的NetLogo显示一个错误，你的模式是行不通的。


在下面的模型示例中，我们有一小部分代表健康人的蓝海龟。我们使用`one-of`将一只随机挑选的海龟变成红色，这表示被感染的主体（即患者零）。