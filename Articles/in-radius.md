`in-radius`是一个关键字，它返回当前主体一定半径内的所有主体。例如，海龟可能想知道在其自身的两个单位的半径内有多少其他海龟，或者一个格子可能想知道在其自身的三个单位内有多少海龟。



```
ask turtles [
	if any? other turtles in-radius 2 [
		create-link-with one-of other turtles in-radius 2
	]
]
```


使用`in-radius`时要记住的事情：

- 您还可以为半径参数使用浮点数，例如`in-radius 3.65` 。
- *海龟*和*格子*都可以使用`in-radius` 。
- 请记住，如果您使用相同的种类， `in-radius`也可能返回来源海龟。请务必在您的模型中考虑到这一点并使用上面示例中所示的`other`关键字。
- 您可以结合`in-radius`和`with`关键字来缩小目标主体的范围，但请确保将第一个`with`语句是被括号`( )`围起来的。例如，你可以写一个像这样的代码， `if any? (carrots with [color = orange]) in-radius 2 [ eat ]` 。


在下面的模型示例中，我们有一个用绿色格子表示的环境和一个位于中心的工厂。点击 go 按钮时，工厂会污染半径 5 内的所有格子，用深绿色格子表示。
