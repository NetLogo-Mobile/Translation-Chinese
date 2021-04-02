*** Machine Translated
`ifelse-value`是一个关键字`ifelse-value` ，它使我们可以快速简洁地检查许多条件并相应地选择一个值。此关键字帮助我们避免编写许多连续的`if`或`ifelse`语句。

例如，如果我们要检查给定海龟在世界四个象限中的哪个象限，那么我们的第一个选择是编写如下代码： 

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


但是，许多`if`语句使读取代码变得困难。相反，我们可以按如下方式使用`ifelse-value`关键字来编写更简洁的代码：



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

- 您应该将整个`ifelse-value`回绕在`ifelse-value` `()` 。
- 您可以在方括号内提供最后一组命令，但没有任何前面的条件。这最后一组命令将被视为`else`语句，它指定在没有条件满足的情况下将发生的情况。您也可以省略此最终条件。


在下面的模型示例中，我们有六个骰子。每次单击“*全部滚动”*按钮时，每只海龟选择1到6之间的一个随机数。然后，我们使用`ifelse-value`关键字来选择正确的海龟图形来表示相应的模具值。