**报告指令**是一个预定义的过程，它返回一个值，与命令不同，它不能是一个独立的代码元素。 NetLogo 有一些有用的内置报告器，它们不能直接更改，例如`ticks` 、 `pi` 、 `e` 、 `world-width`和`world-height` 等。例如，我们不能只在代码中写`ticks` 。我们需要在其他一些算法中使用ticks，例如：



```
if ticks > 9 [ 
	wake-up 
]
```


我们用于过滤主体集或操作列表的其他关键字，例如`of` 、 `with` 、 `sort-on`和`word`等也是报告器。

许多海龟、格子和链接属性（如`color`或`label`都可以被认为是我们可以使用`set`命令更改的变量，以及为我们提供这些变量值的报告器。请注意，在以下示例中，方括号`[ ]`应该在 `of`之前：



```
if xcor < 0 [ 
	if [pycor] of patch-here > 0 [ 
		set label “Quadrant II” 
	] 
]
```


最后，您可以使用创建自定义报告器的`to-report`的关键字，告诉程序你的报告指令开始了并运行代码并在你的过程结束指令时使用`report`命令，最后是`end`关键字。 报告器可用于整理您的代码并防止您重复代码行；如果您多次使用相同的公式或长代码行，则可以使用`to-report`过程来替换它。

例如，如果我们要使用多次`ask turtles with [ shape = “person” and color = green and size > 5 ]` ，我们可以定义一个报告指令过程，如下所示：



```
to-report big-green-people 
	report turtles with [ shape = “person” and color = green and size > 5 ]
end
```


一旦我们定义了这个报告器，我们就可以用`big-green-people`代码中的`turtles with [ shape = “person” and color = green and size > 5 ]`语句替换每个`turtles with [ shape = “person” and color = green and size > 5 ]` ，例如`ask big-green-people [ do-things ]` 。

`to-report`通常用于复杂的计算。例如，如果我们想在代码中多次计算圆的面积，我们可以定义以下报告指令：



```
to-report circle-area [ r ]
	report ( pi * ( r  ^ 2 ) )
end
```


现在，每当我们想计算圆的面积时，我们可以简单地写成`circle-area radius` 。

在下面的模型示例中，我们有许多大大小小的圆圈。这些圆圈代表气体容器内的颗粒。每个粒子都具有相同的能量。然而，它们中的每一个都有不同的速度，因为粒子的动能等于其质量乘以速度的平方除以 2 ($E = \frac

```
if xcor < 0 [ 
	if [pycor] of patch-here > 0 [ 
		set label “Quadrant II” 
	] 
]
```


```
to-report big-green-people 
	report turtles with [ shape = “person” and color = green and size > 5 ]
end
```
 mv^2$)。我们没有编写复杂的代码来在`go`过程计算粒子的速度，而是定义了一个*速度*报告指令。虽然我们特意让这个模型示例的代码保持简单，但如果我们有一个更复杂的模型，我们需要在代码的许多不同部分计算粒子的速度，那么定义这个报告指令会产生很大的不同。
