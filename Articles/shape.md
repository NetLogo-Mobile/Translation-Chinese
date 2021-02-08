*** Machine Translated
`shape`是一个海龟和链变量表示的主体的图形。将使用默认的对应形状创建新的海龟和链接，并可以在`ask`上下文中使用`set shape “shape-name”`格式进行更改，以更改海龟或链接的形状。您还可以像其他任何主体特征一样，将`shape`用作返回指令，例如 

```
ask turtles [ 
if shape = “rabbit” [ 
forward 1  
]
 ] 
```
**请注意**，形状必须用引号（“”）引起。

要在NetLogo中查看可用形状的列表，请单击“工具”菜单，然后选择“Turtle Shapes Editor”或“Link Shapes Editor”选项。每个新的NetLogo模型都预加载了少量形状（例如，绵羊，海龟，汽车，正方形），您可以在代码中直接使用它们。例如，以下代码将在任何新的NetLogo模型中工作： `ask turtles [set shape "person"]`但以下代码将引发错误： `ask turtles [ set shape “person lumberjack”]` 。您可以使用编辑器中的“从库中导入”选项来查找其他模型中使用的形状的详细列表。此外，您可以在编辑器中创建自己的形状。

在下面的模型中，有绵羊和狼四处游荡。只有绵羊吃草而不是狼，因此我们可以通过使用`shape`将主体集合范围缩小到`turtles with [ shape = "sheep" ]`来区分它们。