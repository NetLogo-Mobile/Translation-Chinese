`and`允许我们将两个真/假（true/false）的判断语句组合为一个新的语句，*当且仅当*两个语句都为true时，*整个*语句才为true。

例如，如果我们想要一个海龟**仅**当（A）感到饥饿*并且*（B）格子上存在食物，我们可以说：

```
if my-hunger-level > 100 and food-here > 0 [
  eat-food
  set my-hunger-level 0
]
```

使用`and`时要记住的事情：

- 您可以在同一条件语句中使用多个`and`关键字，例如，`if color = red and size > 3 and xcor < 0 [ ... ]`或`ask turtles with [hunger > 1 and food < 1 and money > 10 ]` 。
- `and`不是一个命令。应该在条件语句中使用它，例如`if`和`if-else`或其他需要true/false值的关键字，例如`while` 。

在下面的模型示例中，我们使用`and`在世界中部生成一条河流。格子会变成蓝色，*当且仅当*它的x坐标是*既*是偏左的`(width / 2)`*又*偏右`- (width / 2)`否则，它仍然是一个绿色的格子。
