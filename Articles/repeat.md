*** Machine Translated
`repeat`允许您执行*n*次任何命令集。它采取以下形式：

`repeat n [ commands ]`

例如，如果您让海龟`repeat 10 [ forward 1 ]` ，它将执行这些命令10次连续背对背，这将导致海龟向前移动10个单位。您可以在任何上下文中使用`repeat` ，只要它在Ask命令内或Ask命令外即可。画图形状时，`repeat`可以特别方便。例如，以下代码将使海龟绘制一个正方形：


    ask turtles [
    pen-down
    repeat 4 [
    forward 10
    right 90
    ]
    ]