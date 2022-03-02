`max-pxcor`返回模型中最右边的格子的`pxcor` 。此关键字及其同级关键字`min-pxcor` ， `max-pycor` ， `min-pycor`在对涉及世界边界的主体行为进行建模时非常有用。例如，如果我们要构建一个在世界边缘有墙的模型，则可以编写以下代码：



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


或者，如果我们希望海龟不走出世界边界，我们可以编写以下代码：



```
ask turtles [
	if [pxcor] of patch-ahead 1 < min-pxcor [
		forward 1
	] 
]
```


使用`max-pxcor`时要记住的事情：

- `max-pxcor` ， `min-pxcor` ， `max-pycor`和`min-pycor`不是变量；他们是恒定的常量。也就是说，诸如`set max-pxcor 30`类的代码将显示错误消息。
- 您可以通过“**界面**”选项卡中的“**设置**”按钮（netlogo桌面版）或控件编辑区的“世界设置”（海龟实验室）或使用`resize-world`关键字来更改模型的大小。


在下面的模型示例中，我们使用`max-pxcor`及其同级关键字创建代表容器的墙。容器内的球会从绿色墙壁弹起，但是会*粘*在红色墙壁上。
