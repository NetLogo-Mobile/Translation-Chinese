*** Machine Translated
`create-links-with`是一个海龟过程，它在当前海龟（self）与提供的主体集合 的每个成员之间创建一个链接。



```
ask turtles [
	create-links-with other turtles-here
]
```


请注意，我们在代码中使用了`other`关键字，因为如果我们不使用`other` ，我们的代码就会出错。的NetLogo显示了这个错误，因为`turtles-here`的原始报告，所有的海龟模型中，包括谁是试图创建链接的海龟，但海龟不能创建自己的链接。因此，当您使用类似的主体集合报告指令关键字（例如`in-radius`和`turtles`时，不要忘记使用`other primitive` 。

另请记住，此关键字用于一次创建多个链接，因此您需要提供一个主体集合 。如果你只想用一个特定的海龟创建一个链接，你应该使用`create-link-with`关键字。

在下面的模型示例中，我们使用`create-links-with`关键字来模拟联系人跟踪。每当两个人在同一个格子，就会在他们之间创建一个新的链接。然后，追溯按钮/过程使用个人之间的联系来追溯可能接触过感染者的人。