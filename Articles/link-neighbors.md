`link-neighbors`是一个海龟关键字，它报告一个主体集合，其中包含通过链接连接到来源海龟的所有海龟。例如，如果我们使用链接来表示友谊关系，海龟可以使用`link-neighbors`关键字向它的朋友发送新消息。例如，以下代码将使朋友少于 2 个的海龟结交新朋友。



```
ask turtles [
	if count link-neighbors < 2 [
		make-new-friends
	]
]
```


在下面的模型示例中，我们使用`link-neighbors`来模拟跟踪密切接触者。每当两只海龟间很接近，它们之间会形成链接。链接代表两只海龟之间的“联系”，可以用`link-neighbors`报告这个人与之接触过的人。当我们在代码中（第 26 行）实现`trace-back`过程时，我们要求任何与目标个体（红色）接触过的的所有`link-neighbors`自己变红，以表示他们被标记为密接者了。
