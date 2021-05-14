*** Machine Translated
`layout-circle`是将一组海龟移动到给定半径的均匀间隔的圆中的基元。例如：



```
create-turtles 100 [
	set shape "person"
]
layout-circle turtles 10
```


使用`layout-circle`时要记住的事情：

- `layout-circle`是*仅*用于*观察者的*原语，因此您不能在`ask`语句中使用它。
- 每当您将此基元与*主体集合*一起使用时，海龟在圆形布局的实际放置位置将是随机的。
- 您可以将布局圆与自定义海龟品种一起使用，例如`layout-circle tables 3` 。


下面的模型示例演示了`layout-circle`工作方式。它有两个*设置*按钮：一个用于创建一个空模型，另一个用于创建在随机位置有10个房屋的模型。单击“开始”按钮时，如果少于10个房屋（即，如果使用设置为空的按钮），则在每个周期创建一个新房屋。然后，我们使用`layout-turtle`来组织我们的社区。该模型还包括一个可变半径，并在每个周期处对其进行递增，以显示`layout-turtle`如何在不同的半径值下工作。