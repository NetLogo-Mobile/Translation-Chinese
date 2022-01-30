`ifelse-value`是一个关键字，它允许我们快速、简洁地检查多个条件并相应地选择一个值。这个关键字帮助我们不用写很多连续的`if`或`ifelse`语句。

例如，如果我们想检查给定海龟在世界的四个象限中的哪一个，我们的第一个选择是编写如下代码： 

```
to-report where-am-i
  if xcor > 0 and ycor > 0 [
    	report "upper-right"
  ]
  if xcor < 0 and ycor > 0 [
    	report "upper-left"
  ]
  if xcor < 0 and ycor < 0 [
    	report "lower-left"
  ]
  if xcor > 0 and ycor < 0 [
    	report "lower-right"
  ]  
end
```


但是，如此多的`if`语句使代码难以阅读。相反，我们可以使用`ifelse-value`关键字来制作更简洁的代码：



```
to-report where-am-i
  report (ifelse-value
    	xcor > 0 and ycor > 0 ["upper-right"]
    	xcor < 0 and ycor > 0 ["upper-left"]
    	xcor < 0 and ycor < 0 ["lower-left"]
    	["lower-right"] ; if none of the conditions are true
  )
end
```


使用`ifelse-value`时要记住的事情：

- 您应该将整个`ifelse-value`回绕在括号`()` 。
- 您可以在括号内提供最后一组命令，但无需任何前置条件。这最后一组命令将被视为`else`语句，指定如果没有一个条件为真会发生什么。您也可以省略此最终条件。


在下面的模型示例中，我们有六个骰子形状。每次我们点击*roll-all*按钮时，每只海龟选择一个 1 到 6 之间的随机数。然后，我们使用`ifelse-value`关键字来选择正确的海龟图形来表示相应的骰子值。
