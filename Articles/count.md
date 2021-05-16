*** Machine Translated
`count`是一种原始，报告在给定主体集合代理的数量。例如， `count turtles`数量报告模型中所有`count turtles`的总数，而`count turtles with [color = green]`的海龟数量报告模型中绿海龟的数量。您可以对海龟，补丁和链接使用`count` 。

我们还可以将`count`与海龟品种结合使用，并链诸如`count dogs`品种，或与其他报告指令代理原语结合使用，例如`count turtles-here` 。

在下面的模型示例中，我们在中心有一个狗公园，并且有一堆乌龟代表附近的狗。我们的狗完全随机地走动。在任何给定时间，如果操场上有5只以上的狗，我们的模型都会显示*“操场太拥挤”的*消息。