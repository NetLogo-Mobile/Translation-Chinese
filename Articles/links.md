*** Machine Translated
`links`是NetLogo中代理的一种特殊类别（如海龟和格子），代表海龟之间的连接。链接本身就是任意两个（不同的）海龟之间的连接，并附加了一些信息。只需使用这种简单的海龟之间连接工具，我们就可以表示海龟之间非常复杂的关系，例如家谱，社交媒体上的“朋友”关系（通常称为“社交图”），甚至是导航软件的路线图，例如谷歌地图或位智。

您可以使用`create-link-with`和`create-links-with`关键字在海龟之间创建新链接。请注意， `create-link-with`仅在两个海龟之间创建一个链接，并且需要一个特定的海龟，而`create-links-with`一次可以创建多个海龟，并且需要一个主体集合。



```
ask turtles [
	create-link with one-of other turtles
	create-links-with other turtles with [color = green]
]
```


使用`links`时要记住的事情：

- NetLogo在“*工具”*菜单下有一个“*链接形状编辑器*”。您可以使用此编辑器来设计自定义链接形状，例如虚线，多条平行线或曲线。
- 以同样的方式，你可以参考一下所有的海龟在世界上的关键字`turtles` ，你可以参考的所有环节，在世界拥有的关键字`links` 。例如，您可以使用此关键字来更改链接的可视表示形式的颜色或粗细，例如`ask links [set color grey]` 。
- 您可以使用`links-own`基本类型（类似于`turtles-own`和`patches-own` ）创建自定义链接特征。例如，如果您要创建农村互联网基础设施模型，则您的链接可能具有*带宽*特征： `links-own [ bandwidth ]` 。
- 您可以使用`undirected-link-breed`关键字创建自定义链接品种。例如，如果您的模型将具有两种类型的链接，例如`cables`和`satellite-connection` ，则可以创建单独的品种，例如`undirected-link-breed [cables cable]`和`undirected-link-breed [satellite-connections satellite-connection]` 。


在下面的模型示例中，我们有一个计算机网络，该网络以中心的服务器为代表，而其他终端计算机则以圆形布局。每台计算机都通过灰色虚线链接连接到服务器，灰色虚线链接表示被动连接。在每次周期，我们的服务器都会启动与随机终端的活动连接。我们用绿色链接表示活动连接。对于活动连接，我们还使用两种不同的链接形状：表示信息检索的简单直线链接和表示文件下载的弯曲三线连接。