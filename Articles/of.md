`of`是一个函数关键字，它使我们可以访问主体并返回其拥有的变量的值。通常，主体变量（例如`color` ， `size` ， `shape`以及使用`<agents>-own`命令定义的变量）是使用`ask`关键字在主体的代码中访问的。 `of`让我们获得在这样的代码块之外的变量或返回在主体集合中的每个主体的某个变量的值的列表。例如，如果我们想创建一个模型，每个人都挑选一个随机的朋友，如果那个朋友还没有苹果，就给那个朋友一个苹果，我们可以编写以下代码：



```
ask people [
	let my-friend one-of other people
	if [apple] of my-friend = 0 [
		ask my-friend [ set apple apple + 1 ]
	]
]
```


使用`of`时要记住的事情：

- `of`对于返回主体变量非常有用，例如返回海龟的平均大小（海龟的`mean [size] of turtles` ），最大海龟的大小（ `max [size] of turtles` ）等。
- 在控件区创建监视控件或图表时， `of`也是非常有用的。通常，我们需要提供某种汇总值，例如海龟的平均财富（海龟的`mean [wealth] of turtles` ）或`mean [wealth] of turtles`总财富（海龟的`sum [wealth] of turtles` ）。
- 您还可以在`of`前的报告指令中执行一些简单的操作。例如，`[checking-account + savings-account] of customers`可以获取客户帐户中的总金额，或者可以使用`[size / 2] of circles`自动计算出圆形的半径。
- 如果我们使用`of`作用于主体集合（一般配合其他函数关键字，如`mean` ），它将返回一个列表。例如，如果模型中有3只海龟，则`[size] of turtles`将返回`[1 1 1]` 。


在下面的模型示例中，我们有一个与前段时间比较流行的网页游戏[*agar.io*](https://en.wikipedia.org/wiki/Agar.io)相似的模型。我们有很多海龟代表圆圈，它们随机移动。当两只海龟互相接触时，较大的那个海龟会*吞食*较小的那个海龟。我们使用`of`来比较`ask`语句中的两只海龟，以选择较大的一只，然后将两只海龟的大小相加。
