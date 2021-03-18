*** Machine Translated
`face`设置一个海龟的方向朝另一个特定的主体点。`face`通常用于将一只海龟指向另一只海龟或特定格子。例如，如果两只海龟在模型的相对边缘上，`ask one-of turtles [ face other-turtle ]`会使该海龟转向另一只海龟。`ask turtles [ face patch 0 0 ]`将使所有海龟面向模型的中心。

在下面的模型中，有一只猫在追老鼠。鼠标正在从猫中奔跑，并试图逃脱到其鼠标孔中。为了使猫追逐鼠标并使鼠标跑到其孔中，我们使用`face` 。