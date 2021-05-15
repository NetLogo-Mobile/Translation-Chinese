*** Machine Translated
**报告指令**程序是一个预定义的过程，它返回一个值，并且与命令不同，它不能是独立的代码元素。 NetLogo具有一些无法直接更改的有用的内置报告器，例如`ticks` ， `pi` ， `e` ， `world-width`和`world-height` 。例如，我们不能只在代码中写`ticks` 。我们需要在其他一些算法中使用刻度，例如：



```
if ticks > 9 [ 
	wake-up 
]
```


我们用于过滤代理集或处理列表的其他原语（例如`of` ， `with` ， `sort-on`和`word`也是报告程序。

许多海龟， 格子和链属性（例如`color`或`label`都可以被视为我们可以使用`set`命令更改的变量，也可以被视为为我们提供这些变量的值的报告器。请注意以下示例中位于方括号`[ ]`之前`of` ：



```
if xcor < 0 [ 
	if [pycor] of patch-here > 0 [ 
		set label “Quadrant II” 
	] 
]
```


最后，您可以使用`to-report`关键字创建自定义`to-report`程序，以开始一个报告指令过程，并在该过程的末尾，即`end`关键字之前，创建`report`命令。记者可以使您整理代码并使您避免重复代码行。如果您多次使用相同的方程式或较长的代码行，则可以使用`to-report`过程来替换它。

例如，我们可以定义一个报告指令过程，而不是多次写`ask turtles with [ shape = “person” and color = green and size > 5 ]` ：



```
to-report big-green-people 
	report turtles with [ shape = “person” and color = green and size > 5 ]
end
```


一旦定义了此变量，我们就可以在代码中使用[ `big-green-people` `turtles with [ shape = “person” and color = green and size > 5 ]`来替换每只`turtles with [ shape = “person” and color = green and size > 5 ]` ，例如`ask big-green-people [ do-things ]` 。

`to-report`通常用于复杂的计算。例如，如果我们想在代码中多次计算圆的面积，则可以定义以下报告指令：



```
to-report circle-area [ r ]
	report ( pi * ( r  ^ 2 ) )
end
```


现在，只要我们想计算圆的面积，就可以简单地写出`circle-area radius` 。

在下面的模型示例中，我们有许多大大小小的圆圈。这些圆圈代表气体容器内的颗粒。每个粒子具有相同的能量。但是，它们每个都有不同的速度，因为粒子的动能等于其质量乘以其速度的平方除以2（$ E = \ frac 

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
 mv ^ 2 $）。我们定义了一个*速度*报告指令，而不是编写复杂的代码来计算`go`过程的粒子*速度*。尽管我们故意使此模型示例的代码保持简单，但是如果我们有一个更复杂的模型（需要在代码的许多不同部分中计算粒子的速度），则定义此报告指令将有很大的不同。