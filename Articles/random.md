*** Machine Translated
`random`是使我们可以在模型中添加随机性的原语。当我们提供一个`random`数时，它将返回一个从0到N-1的随机数。想象一下，每次运行原始`random N` ，您都在滚动具有N个边数的模具。例如，如果我们要创建森林火灾，在其中将每个格子分配为一棵树（ `pcolor = green` ）或地面（ `pcolor = brown` ）但树密度为70％，我们将编写以下代码：



```
ask patches [
	ifelse random 100 < 70 [
		set pcolor green
	][
		set pcolor brown
	]
]
```


使用`random`时要记住的事情：

- 始终记住， `random`将为我们提供从0到N-1而不是1到N的数字。例如，如果我们运行`random 3` ，则可能得到0、1或2，而不是0。
- 如果要在自定义范围之间生成随机数，则可以使用以下格式： `minnumber + (random (maxnumber - minnumber))` 。例如，如果我们要生成4到7之间的随机浮点数，则可以编写以下代码： `4 + random 3` 。
- `random`仅生成正整数。如果需要生成浮点数，则应使用`random-float` 。
- `random`算法生成均匀分布。例如，每次我们运行`random 5` ，获得0、1、2、3或4的可能性均等。如果您想在*正态分布*上生成随机数，则应使用`random-normal` 。


在下面的模型示例中，我们有6只乌龟代表骰子的6个面。每次单击**掷骰子**按钮时，每只海龟选择一个1到6（包括6）之间的随机数，并相应地更新其图形。