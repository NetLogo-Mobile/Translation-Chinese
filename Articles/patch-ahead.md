*** Machine Translated
`patch-ahead`报告单个格子，它是要问的海龟*之前*给定距离的信息。您可以将其想象为海龟看着它前面的一块格子。例如，如果我们正在创建高速公路交通模型，并且希望我们的汽车仅在前面没有其他汽车的情况下才行驶，则可以编写以下代码：



```
ask cars [
	set heading 90
	if count turtles-on patch-ahead 1 = 0 [
		forward 1
	]
]
```


使用`patch-ahead`时要记住的事情：

- 在某些情况下，当模型的世界*没有包裹时*， `patch-ahead`补丁可能不会返回`nobody`并可能会因为格子不存在而导致错误。我们可以通过使用if语句，例如`if patch-ahead 1 != nobody [ forward 1 ]`来避免此错误。
- 我们可以提供浮点数到`patch-ahead` ，以及整数，如`patch ahead 2.76` 。


在下面的模型示例中，我们有一些灰色的小块代表一条道路，一个红色的格子代表停车标志。只要`patch-ahead 1`的`patch-ahead 1`的`pcolor`是灰色，我们的汽车就会向东行驶。如果没有，我们的汽车就不会移动，这意味着它会在停车标志处停止。