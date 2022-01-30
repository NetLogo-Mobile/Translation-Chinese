`let`命令会创建一个新的局部变量并设置其初始值。局部变量是只存在于它所在的特定的`ask`语句中或括号内代码运行的过程中的变量。与`global`变量类似，局部变量的值对于所有主体都是相同的。



```
ask turtles [
	let people-nearby (other turtles in-radius 2)
  if any? people-nearby [
  	let new-friend one-of people-nearby
  	set my-friends (lput new-friend my-friends)
  ]
]
```


使用`let`创建局部变量后，就可以使用`set`关键字为其分配初始值。 `let`对于计算临时值或创建临时主体集非常有用。例如，如果我们想要一只海龟选择 6 个随机数并返回随机数的总和，我们可以使用`let` ，如下所示：



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


在下面的模型示例中，我们有一些快乐的海龟和一些悲伤的海龟。每当两只海龟在同一个格子，一只海龟就会使另一只改变它的图形。可能会出现两种情况：要么一只悲伤的海龟会让另一只海龟悲伤，要么一只快乐的海龟会让另一只快乐。我们在这个模型中使用`let`是因为它允许我们不会一次又一次地重写一段较长的代码（ `other turtles-here` ）。
