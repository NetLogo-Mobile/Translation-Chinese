*** Machine Translated
`link-neighbors`是一个海龟格子，它报告一个主体集合，其中包含通过链接连接到关键字海龟的所有海龟。例如，如果我们使用链接来表示友谊关系，那么海龟可以使用`link-neighbors`关键字向其朋友发送新消息。例如，以下代码将确保少于2个朋友的海龟结识新朋友。



```
ask turtles [
	if count link-neighbors < 2 [
		make-new-friends
	]
]
```


在下面的模型示例中，我们使用`link-neighbors`来模拟联系人跟踪。每次两只海龟去接近对方，形成它们之间的链接。每个链接代表两个海龟之间的“联系”，因此呼叫某个人的`link-neighbors`会向该人报告与该人联系过的每个其他人。当我们在代码中执行`trace-back`过程时（第26行），我们要求所有暴露的（红色）个人的所有`link-neighbors`都将自己变成红色，以表示他们也已暴露。