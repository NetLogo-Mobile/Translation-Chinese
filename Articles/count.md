*** Machine Translated
`Count`返回主体的数量在指定主体集合。（注意：您可以使用`with`来缩小给定的主体集合。）例如，`show count turtles`将显示模型中的海龟总数，而`show count turtles with [color = green]`将显示其中的绿海龟数量。该模型。

在下面的模型中，一群球员试图组织一场篮球比赛。因为一场篮球需要10名球员，所以如果少于10名球员，没有人可以参加比赛。因此，我们使用`if count players < 10`来确保有足够的玩家来玩游戏。