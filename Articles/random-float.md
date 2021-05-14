*** Machine Translated
`random-float`是一个数学基元，它报告一个介于0到给定数字之间的任意浮点数。例如， `random-float 10`可以返回6.9105、7、4.2、0.451、0.0000001、9.99999等。 `random-float`在需要连续数字的现象建模中非常有用。例如，如果我们想创建一个模型来容纳不同身高的人，我们可以编写以下代码，使每个人的身高在5英尺至7英尺之间：



```
create-people 100 [
	set size 5 + random-float 2
]
```


使用`random-float`时要记住的事情：

- 如果要在自定义范围之间生成随机数，则可以使用以下格式： `minnumber + (random-float (maxnumber - minnumber))` 。例如，如果我们想生成一个4到7之间的随机浮点数，我们将编写以下代码： `4 + random-float 3` 。
- 在常见的情况下，如果您想获取介于最小和最大x或y坐标之间的随机值，则可以使用`random-xcor`和`random-ycor` ，它们还会返回非整数值。
- 因为`random-float`将返回0到（n-1）之间的数字，所以`random-float 5.0`可以返回`0.0` ，但永远不会返回`5.0` 。可以返回的最大`random-float`是`4.999999....`


在下面的模型示例中，我们使用`random-float`将飞镖随机放置在飞镖板上（或从飞镖板上移出）的某个位置。通过使用`random-float` ，我们可以确保飞镖可以降落在飞镖板上的每个可能的点上，而不仅仅是整数点。