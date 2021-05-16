*** Machine Translated
`pen-up` （简称`pu` ）用于停止追踪海龟的运动。画笔的颜色和海龟的颜色一样。当`pen-up`停止跟踪时， `pen-down` （ `pd`简短版本）开始跟踪乌龟的运动。

想到`pen-up`和`pen-down`像海龟的腹部画笔; `pen-down`可将画笔放到地面上，留下路径标记，而`pen-up`放笔可将画笔往上拉，不再标记地面。 `Pen-down`和`Pen-down` `pen-up`是仅与海龟一起使用的图元。例如，如果我们希望乌龟画一个正方形，我们将编写以下代码：



```
ask turtles [
	pen-down
	repeat 4 [
		right 90
		forward 5
	]
	pen-up
]
```


在下面的模型中，一架飞机在两个神话般的目的地之间飞行：亚特兰蒂斯和瓦尔哈拉。在飞行过程中，是否在`draw-path?`留下了痕迹`draw-path?`开关打开。飞机每次到达目的地并转身时，都会更改其颜色，从而产生新的尾迹颜色。如果`draw-path?`开关关闭后，我们的飞机拿起画笔停止画图。当`draw-path?`时，我们还使用`clear-drawing`原语清除所有先前`draw-path?`开关关闭。请注意， `clear-drawing`是仅用于观察者的基元，因此我们在`ask turtles`语句之外使用它。