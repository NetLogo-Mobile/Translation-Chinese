*** Machine Translated
`ifelse-value`是一种原始`ifelse-value` ，它使用户可以快速简洁地检查许多条件，并根据结果执行不同的代码。`ifelse-value`不能与一系列`if`或`ifelse`语句一起完成，但是`ifelse-value`的优势在于其语法效率。例如，假设您要检查给定海龟在世界四个象限中的哪个象限。与`if`版本相比，`ifelse-value`一个可以说更干净。

```
to-report report-quadrant-if
  if xcor > 0 and ycor > 0 [
	report 1
  ]
  if xcor < 0 and ycor > 0 [
	report 2
  ]
  if xcor < 0 and ycor < 0 [
	report 3
  ]
  if xcor > 0 and ycor < 0 [
	report 4
  ]  
end

to-report report-quadrant-ifelse-value
  report (ifelse-value
	xcor > 0 and ycor > 0 [1]
	xcor < 0 and ycor > 0 [2]
	xcor < 0 and ycor < 0 [3]
                      	[4] ; else
  )
end
```
 使用`ifelse-value`要注意的一件事是，如果使用多个条件，则必须用括号将整个内容回绕。另外，要知道您可以省略最终条件，并且您写的最后一组括号将被视为`else`语句，并指定了在没有条件成立的情况下将发生的情况。

下面的示例显示了一个地方，可以在其中使用`ifelse-value`来使代码更简洁，并且您熟悉的一个地方更易读：将六个模具图标中的一个选择为六个