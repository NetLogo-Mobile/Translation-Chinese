*** Machine Translated
`let`创建一个新的局部变量并设置其初始值。局部变量是仅存在于在特定`ask`语句内或括号内创建的过程的变量。与`global`变量类似，所有海龟的局部变量值都相同。



```
ask turtles [
	let people-nearby (other turtles in-radius 2)
  if any? people-nearby [
  	let new-friend one-of people-nearby
  	set my-friends (lput new-friend my-friends)
  ]
]
```


一旦使用`let`创建了局部变量，就可以使用`set`关键字为它分配一个新值。 `let`对于计算临时值或创建临时代理集非常有用。例如，如果我们想让海龟投掷6个骰子并返回骰子的总和，则可以使用`let` ，如下所示：



```
to-report roll-six
	let total-outcome 0
	repeat 6 [
		let new-outcome (one-of [1 2 3 4 5 6])
		set total-outcome (total-outcome + new-outcome)
	]
	report total-outcome
end
```


在下面的模型示例中，我们有一些快乐的海龟和一些悲伤的海龟。每当两只海龟都在同一格子，一只海龟会要求另一只改变图形。从某种意义上说，要么是一只悲伤的海龟会让他的朋友悲伤，要么是一只快乐的海龟会让它的朋友开心。我们在此模型中使用`let`是因为它使我们不必一次又一次地重写较长的代码（ `other turtles-here` ）。