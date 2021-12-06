*** Machine Translated
补丁是 NetLogo 中一种特殊的固定主体，它构成了模型的世界。您可以将补丁视为构成棋盘的方块。

`patch`关键字报告具有给定坐标的特定格子。例如，如果我们想创建一个蚁群的模型，它的入口是中心的格子，我们可以编写以下代码：



```
ask patch 0 0 [
	set pcolor green
]
```


`patches`关键字报告模型中的所有补丁。该关键字有助于要求所有补丁执行相同的操作（例如，更改 pcolor）或缩小补丁子集的范围。例如，如果我们想创建一个森林火灾模型，其中一些绿色块代表树木，一些绿色块代表地面，最左边的块代表火（红色），我们将编写以下代码：



```
ask patches [
	set pcolor one-of [green brown]
]
ask patches with [pxcor = min-pxcor][
	set pcolor red
]
```


使用`patch`和`patches`时要记住的事情：

- 原始`patches`将始终返回相同的主体集合，但每次使用时补丁的顺序将是随机的。
- 像海龟一样，斑块也有特征。一些特性是预先构建的（例如， `pcolor` 、 `pxcor` 、 `pycor` 、 `plabel` ），但我们也可以使用`patches-own`关键字定义自定义特性，例如`patches own [minerals water]` 。
- 我们无法创建自定义格子品种。


在下面的模型示例中，我们有一个被围栏包围的农场。篱笆用棕色斑块表示，草原用绿色或石灰斑块表示。我们也有一个代表农场和几头牛谁各地随机移动，吃在每个格子的草地，直到没有剩下的草中间的黄色方块。