*** Machine Translated
`count`是一种关键字，报告在给定主体集合代理的数量。例如， `count turtles`数量报告模型中所有`count turtles`的总数，而`count turtles with [color = green]`的海龟数量则报告模型中绿海龟的数量。您可以对海龟，格子和链接使用`count` 。

您还可以将`count`与海龟品种结合使用，并将其与链接品种（例如`count dogs` ）结合使用，或与其他报告指令代理关键字结合使用，作为`count turtles-here` 。

在下面的模型示例中，我们在中心有一个狗公园，并且有一堆海龟代表附近的狗。我们的狗完全随机地走动。在任何给定时间，如果操场上有5只以上的狗，我们的模型都会显示*“操场太拥挤”的*消息。