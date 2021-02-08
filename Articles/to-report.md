*** Machine Translated
**返回指令**是返回值的东西，与命令不同，它不能是独立的代码元素。NetLogo具有一些无法直接更改的有用的内置返回器，例如`ticks` ，`pi` ，`e` ，`world-width`和`world-height` 。例如，我们不能只在代码中写`ticks` 。我们需要在其他一些算法中使用滴答，例如： `if ticks > 9 [ wake-up ]`或设置`let world-area (world-width * world-height)` 。

我们用于过滤主体集或处理列表的其他关键字（例如`of` ，`with` ，`sort-on`和`word`也是返回程序。

许多海龟，格子和链属性（例如`color`或`label`都可以被视为我们可以通过`set`命令更改的变量，也可以被视为为我们提供这些变量值的返回器。请注意，在下面的示例中，前面的括号`[ ]` 

```
if xcor < 0 [ 
If [pycor] of patch-here > 0 [ 
set label “Quadrant II” ] 
]
```
 最后，您可以使用`to-report`关键字创建自定义`to-report`程序，以开始一个返回指令过程，并在该过程的末尾，即`end`关键字之前，创建`report`命令。记者可以使您整理代码并使您避免重复执行代码行。如果您多次使用相同的方程式或较长的代码行，则可以使用`to-report`过程来替换它。

例如，如果您多次编写`ask turtles with [ shape = “person” and color = green and size > 5 ]` ，则可以改为添加返回指令过程，例如

```
to-report big-green-people 
report turtles with [ shape = “person” and color = green and size > 5 ]
end
```
 然后为代码中的`big-green-people`替换每只`turtles with [ shape = “person” and color = green and size > 5 ]` ，例如`ask big-green-people [ do-things ]` 。计算完要从过程返回的值后，将原始`report`添加到该值的前面。

`to-report`通常用于计算。例如，如果您想在代码中多次计算圆的面积，则可以编写 

```
To-report circle-area [ r ]
Report ( pi * ( r  ^ 2 ) )
end
```
现在，每当您想要计算`circle-area [ radius ]` ，只需编写`circle-area [ radius ]` 。