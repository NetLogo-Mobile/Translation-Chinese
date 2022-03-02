`shape`是一个表示主体的形状且允许我们使用`set`关键字来改变主体的图形的海龟和链接的变量。默认会使用相应的默认形状创建新的海龟和链接。我们可以在`ask`上下文中使用`set shape “shape-name”`格式更改主体的图形。此外，我们可以使用`shape`作为报告指令/变量来创建条件等。例如，如果要创建一个模型，使海龟看起来像绵羊或狼，然后使它们变大，则可以编写下面的代码：



```
ask turtles [ 
	set shape one-of ["wolf" "sheep"]
	if shape = "wolf"[
		set size 1.5
	]
] 
```


使用“shape”时要记住的事情：

- 形状必须使用引号（ `“”` ）。
- 要查看可用形状的列表，请使用shapes，这将返回所有预加载的海龟图形，如果还要自定义图形，在Netlogo desktop中请单击“工具”菜单，然后选择“ Turtle Shapes Editor”或“ Link Shapes Editor”选项，在海龟实验室中，你可以使用自定义资源包---**注意：该功能尚未开放**。每个新的NetLogo模型都预加载了少量形状（例如，绵羊，海龟，汽车，正方形），您可以在代码中直接使用它们。例如，以下代码将能够在任何新的NetLogo模型中工作： `ask turtles [set shape "plant"]`但以下代码将引发错误： `ask turtles [ set shape “cactus”]` 。您可以使用Netlogo desktop编辑器中的“从库中导入”选项来查找其他模型中使用的形状的详细列表。此外，您还可以在编辑器中创建自己的形状。


在下面的模型示例中，到处都是绵羊和狼。只有绵羊吃草，而不是狼，因此我们可以通过使用`shape`将可能吃草的主体范围缩小`turtles with [ shape = "sheep" ]`来区分它们。
