*** Machine Translated
`hatch`是一种关键字的东西，可以提供一定数量的海龟相同的副本。与`create-turtles`关键字相似，它需要一个数字，并且还可以通过在其后面加上方括号`[]`来为新的Turtle定义可选规则。



```
ask turtles [
	if season = "spring" [
		hatch 3 [
			set size 0.1
			set shape "penguin egg"
			set color white
		]
	]
]
```


使用`hatch`时要记住的事情：

- `hatch`只能由`ask`语句中的海龟使用。如果您需要格子来创建新的海龟，则应使用`sprout`关键字。
- 您也可以通过使用`hatch-pluralbreedname`约定将`hatch`用于自定义海龟品种。例如，如果模型中有*企鹅*种类，则可以使用`hatch-penguins` ；如果您有`eggs`种类，则可以使用`hatch-eggs` 。


在下面的模型示例中，我们有一只海龟代表一只虫子，还有一些棕色斑块代表食物。当虫子随机走动时碰到格子食物时，它会吃掉食物，然后*孵出*一个新的虫子。请注意，每次我们用`hatch`关键字创建一个新的bug时，都会在方括号`[ right random 360 ]`内添加以下命令，因为如果不添加此代码，则新海龟的位置，大小和方向将完全相同它的母海龟，几乎使我们无法区分两者。