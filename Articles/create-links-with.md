*** Machine Translated
`create-links-with`是一个海龟过程，它在当前海龟（自身）与提供的主体集合的每个成员之间创建链。



```
ask turtles [
	create-links-with other turtles-here
]
```


请注意，我们在代码中使用了`other`原语，因为如果不使用`other` ，我们的代码将给出错误。的NetLogo显示了这个错误，因为`turtles-here`的原始报告，所有的海龟模型中，包括谁是试图创建链接的海龟，但海龟不能创建自己的链。所以，不要忘记使用`other primitive`当你使用类似主体集合报告指令原语，如`in-radius`和`turtles` 。

还请记住，他的原语用于一次创建多个链接，因此您需要提供一个主体集合 。如果你想创建只有一个特定海龟的链，你应该使用`create-link-with`原始。

在下面的模型示例中，我们使用`create-links-with`原始`create-links-with`的`create-links-with`模拟联系人跟踪。每当两个人在同一格子，就会在他们之间创建一个新链。然后，追溯按钮/过程将使用个体之间的链接来追溯可能已暴露给感染者的人们。