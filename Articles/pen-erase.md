*** Machine Translated
`Pen-down` （缩写为`pd` ）用于跟踪海龟的运动。画笔的颜色和海龟的颜色一样。当下`pen-down`开始追踪时，上`pen-up` （简称`pu` ）停止追踪海龟的运动。想到`pen-up`和`pen-down`像海龟的腹部画笔; `pen-down`可将画笔放到地面上，留下路径标记，而`pen-up`放笔可将画笔向上提起，不再标记地面。`Pen-down`和`Pen-down` `pen-up`是仅与海龟一起使用的图元。例如，`ask turtles [ pen-down]`将开始从海龟的运动中画图线条，而`ask turtles [ pen-up]`将不再跟踪该运动。（ `Pen-down` ，`pen-up`和`pen-erase`都等同于将海龟的`Pen-down` `pen-mode`为`down` ，`up`或`erase` ）

以下代码将使海龟绘制正方形，然后移动到随机位置而不会留下痕迹：


    ask turtles [
    pen-down
    repeat 4 [ forward 10 right 90 ]
    pen-up
    setxy random-xcor random-ycor
    ]


`Pen-erase` （缩写为`pe` ）在海龟经过它们时会删除以前绘制的线条。可以把它当作海龟腹部的橡皮擦。

在下面的模型中，一架飞机在飞行。根据选择的过程，飞机将简单地四处飞行（使用上`pen-up` ），在离开跑道时四处飞行（使用`pen-down` ）或在擦除过去的线时四处飞行（使用`pen-erase` ）。