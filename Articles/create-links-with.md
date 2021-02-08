*** Machine Translated
`create-links-with`是一个海龟过程，它在当前海龟（自身）与提供的主体集合的每个成员之间创建链。（与比较`create-link-with` ，这产生来自电流海龟一个链到一个*单独的*其他海龟）。

使用`create-links-with`时要牢记的一件重要事情是，海龟创建到自己的链会导致错误。例如，如果您要编写：

```
ask turtles [
  create-links-with turtles in-radius 5
]
```
，您将得到一个错误，因为当前的“自我”海龟将包含在`turtles in-radius 5`内的`turtles in-radius 5` ，从而导致海龟尝试与其自身创建链，而不是允许的。为避免此问题，您经常会看到`other`命令与`create-turtles-with`以确保不会意外创建自链接。例如，要解决上述错误，您可以改写：

```
ask turtles [
  create-links-with other turtles in-radius 5
]
```
 在此示例中，`create-links-with`用于模拟联系人跟踪，其中我们跟踪每对交互的个体（在我们的示例中为链），然后使用该信息来跟踪可能接触过传染病的人。在我们的模型中，每个周期，每个人都在自己的小半径范围内与所有其他人创建链，表示“联系”。然后，我们可以使用“追溯”按钮通过沿这些链接进行追溯来突出显示已与潜在感染者联系的每个人。