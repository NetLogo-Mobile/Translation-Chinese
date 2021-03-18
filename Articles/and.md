*** Machine Translated
`and`是一种关键字，它允许我们将两个true-false语句组合为一个单独的语句，*当且仅当*两个语句都为true*时，才*为true。

例如，如果我们想要一个海龟**仅**当（A）吃饿*和*（B）如果有在同一格子的食物，我们可以说：



```
if my-hunger-level > 100 and food-here > 0 [
  eat-food
  set my-hunger-level 0
]
```

  

使用`and`时要记住的事情：

- 您可以在同一条件原始中使用多个`and`原始，例如，`if color = red and size > 3 and xcor < 0 [ ... ]`或`ask turtles with [hunger > 1 and food < 1 and money > 10 ]` 。
- `and`本身并不做任何事情;您应该在条件语句中使用它，例如`if`和`if-else`或其他需要true-false值的关键字，例如`while` 。