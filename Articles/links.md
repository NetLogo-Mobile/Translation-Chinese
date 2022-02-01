`links`是 NetLogo 中一类特殊的主体（与海龟和格子同级），用于表示海龟之间的连接。链接本身只是任何两个（不同的）海龟之间的连接，并附加了一些信息。只需使用这个简单的海龟之间连接工具，我们就可以表示海龟之间非常复杂的关系，例如家谱、社交媒体上的“朋友”关系（通常称为“社交图”），甚至是导航软件的路线图，例如谷歌地图或位智。

您可以使用`create-link-with`或`create-links-with`关键字在海龟之间创建新链接。请注意， `create-link-with`只在两个海龟之间创建一个链接，它需要一个特定的海龟，而`create-links-with`会一次创建多个海龟并需要一个主体集合。



```
ask turtles [
	create-link with one-of other turtles
	create-links-with other turtles with [color = green]
]
```


使用`links`时要记住的事情：

- 原版NetLogo 在*工具*菜单下有一个*链接形状编辑器*。您可以使用此编辑器设计自定义链接形状，例如虚线、多条平行线或曲线。**但海龟实验室暂时没有这个功能。**
- 以同样的方式，你可以参考一下所有的海龟在世界上的关键字`turtles` ，你可以参考所有`turtles`拥有的关键字并用在`links` 上。例如，您可以使用此关键字来更改链接的颜色或粗细，例如`ask links [set color grey]` 是改变链接的颜色，而`ask links [set thickness 2]`是改变链接的粗细。
- 您可以使用`links-own`关键字（类似于`turtles-own`和`patches-own` ）创建自定义链接变量。例如，如果您正在创建农村互联网基础设施模型，您的链接可能具有*带宽*变量： `links-own [ bandwidth ]` 。
- 您可以使用`undirected-link-breed`关键字创建自定义链接种类。例如，如果您的模型将有两种类型的链接，例如`cables`和`satellite-connection` ，您可以创建单独的种类，例如`undirected-link-breed [cables cable]`和`undirected-link-breed [satellite-connections satellite-connection]` 。


在下面的模型示例中，我们有一个计算机网络，其他终端计算机以服务器为中心，以圆形布局。每台计算机都通过灰色虚线链接表示连接到服务器。在每个时间步，我们的服务器都会启动与随机终端的活动连接。我们用绿色链接表示活动连接。我们还为活动连接使用了两种不同的链接形状：表示信息检索的简单直线链接和表示文件下载的弯曲三线连接。
