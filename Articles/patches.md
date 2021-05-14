*** Machine Translated
修补程序是NetLogo中一种特殊的固定代理，它构成了模型的世界。您可以将补丁视为构成国际象棋棋盘的正方形。

`patch`原语报告具有给定坐标的特定格子。例如，如果我们要创建一个蚁群模型，其入口是中心的格子，则可以编写以下代码：



```
ask patch 0 0 [
	set pcolor green
]
```


`patches`原语报告模型中的所有修补程序。该原语有助于要求所有补丁执行相同的操作（例如，更改pcolor）或缩小补丁子集的范围。例如，如果我们要创建一个森林火灾模型，其中一些绿色补丁代表树木，一些绿色补丁代表地面，最左边的补丁代表火（红色），我们将编写以下代码：



```
ask patches [
	set pcolor one-of [green brown]
]
ask patches with [pxcor = min-pxcor][
	set pcolor red
]
```


使用`patch`和`patches`时要记住的事情：

- 原始`patches`将始终返回相同的主体集合，但是每次使用补丁时，补丁的顺序将是随机的。
- 像乌龟一样，斑块也具有特征。一些特征是预先构建的（例如`pcolor` ， `pxcor` ， `pycor` ， `plabel` ），但是我们还可以使用`patches-own`原始内容（例如`patches own [minerals water]` ）定义自定义特征。
- 我们无法创建自定义格子品种。


在下面的模型示例中，我们有一个被栅栏包围的农场。篱笆用棕色补丁表示，草地用绿色或石灰补丁表示。我们中间还有一个黄色的正方形，代表一个牧场，一些奶牛随机地走来走去，在每个格子上吃草，直到没有草。