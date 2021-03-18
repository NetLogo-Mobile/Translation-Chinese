*** Machine Translated
通过处理具有特定特征的一组特定主体，使用`With`来缩小一组主体，通常是**格子**或**海龟**。使用`with`将仅解决集合中符合特定特征的主体。其语法为：

`agentset with [ desired-characteristic ]`

例如，`ask turtles with [color = blue] [forward 1]`的海龟只会使蓝色的海龟向前移动。您可以在`[ ]`使用多个必需的特性，`and`用`and`或`or`分隔它们，以进一步缩小主体集合。例如

`ask turtles with [color = red and size > 5] [`

`forward 1 ]`

只会使大于5的红海龟前进。