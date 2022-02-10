`pen-down` （简写为`pd` ）用于绘制海龟的运动轨迹。画笔的颜色和海龟的颜色是一致的。 `pen-down`开始绘制时，使用`pen-up` （简写为`pu`）可以停止绘制海龟的运动轨迹。想像一下，`pen-up`和`pen-down`像海龟的腹部上的一个画笔; `pen-down`可将画笔放到地面上，留下痕迹，而`pen-up`放笔可将画笔往上提，不再留下痕迹。 `Pen-down`和 `pen-up`是海龟命令。例如，`ask turtles [ pen-down]`将开始分别绘制所有海龟的运动轨迹，而`ask turtles [ pen-up]`将不再绘制运动轨迹。（ `Pen-down` ，`pen-up`和`pen-erase`都等同于将海龟的`pen-mode`设为`down` ，`up`或`erase` ）

以下代码将使海龟绘制正方形，然后移动到随机位置而不会留下痕迹：


    ask turtles [
    pen-down
    repeat 4 [ forward 10 right 90 ]
    pen-up
    setxy random-xcor random-ycor
    ]


`Pen-erase` （简写为`pe` ）在海龟经过以前绘制的轨迹时会擦除这些轨迹。可以把它当作海龟腹部的橡皮擦。

在下面的模型中，一架飞机在飞行。根据预定的代码，飞机将简单地四处飞行（使用上`pen-up` ），在离开跑道时四处飞行（使用`pen-down` ）或在擦除过去的线时四处飞行（使用`pen-erase` ）。
