*** Machine Translated
`in-radius`是报告当前主体一定半径内的所有代理程序的关键字。例如，一只海龟可能想知道在其两个单位的半径内还有多少其他海龟，或者一个格子可能想知道在其三个单位的半径内有多少只海龟。



```
ask turtles [
	if any? other turtles in-radius 2 [
		create-link-with one-of other turtles in-radius 2
	]
]
```


使用`in-radius`时要记住的事情：

- 您也可以为半径参数使用浮点值，例如`in-radius 3.65` 。
- *海龟*和*斑块*都可以`in-radius`使用。
- 请记住，如果您使用的是相同品种， `in-radius`也可能返回关键字海龟。确保使用上面示例中所示的`other`关键字在模型中考虑到这一点。
- 您可以`in-radius`和`with`关键字来缩小目标代理的范围，但请确保将第一个`with`语句封装在parantheses `( )` 。例如，您可以编写类似的代码`if any? (carrots with [color = orange]) in-radius 2 [ eat ]` 。


在下面的模型示例中，我们有一个用绿色格子表示的环境，一个工厂位于中心。单击“执行”按钮时，工厂会污染半径5范围内的所有色块，以深绿色的色块表示。