*** Machine Translated
`max-pycor`报告模型中最顶层补丁的`pycor` 。此原语及其兄弟`min-pycor` `min-pxcor` ， `max-pxcor`和`min-pycor`在建模涉及环境边界的主体行为时非常有用。例如，如果我们要构建一个在边缘有墙的模型，则可以编写以下代码：



```
ask patches [
	if pxcor = max-pxcor or
	   pxcor = min-pxcor or
	   pycor = max-pycor or
	   pycor = min-pycor [
	   		set pcolor gray
	   ]
]
```


或者，如果我们希望乌龟不走出世界边界，我们可以编写以下代码：



```
ask turtles [
	if [pxcor] of patch-ahead 1 < max-pycor [
		forward 1
	] 
]
```


使用`max-pycor`时要记住`max-pycor` ：

- `max-pxcor` ， `min-pxcor` ， `max-pycor`和`min-pycor`不是变量；他们是恒定的记者。也就是说，诸如`set max-pycor 30`类的代码将显示错误消息。
- 您可以通过**“**界面”选项卡中的**“设置”**按钮或使用`resize-world`原语来更改模型的大小。


在下面的模型示例中，我们使用`max-pycor`及其兄弟姐妹创建代表容器的墙。容器内的球从绿色墙壁弹起，但*粘*在红色墙壁上。