`scale-color`是一个关键字，它报告与给定数字的值成比例的颜色阴影。例如，如果我们想创建一个交通模型，其中油箱满的汽车比油箱空的汽车更亮，我们将编写以下代码：



```
ask cars [
	set color scale-color white tank-level 0 100
]
```


或者，如果我们想模拟一群绵羊，其中更茂密的草地比已经吃过的那些草地更亮，我们将编写以下代码：



```
ask patches [
	set pcolor scale-color green lushness 0 100
]
```


使用`scale-color`时要记住的事情：

- `scale-color`的语法可能很难记住。如下`scale-color base_color exact_point lowest_value highest_value` 。
- 您可以将*base\_color*值视为所提供范围的中点。例如，如果我们编写`scale-color green 50 0 100` ，我们将得到完全绿色。
- 不要忘记先给定所需的基色，再是确切的值， `number`是您希望缩放的值（通常是海龟或格子变量），而`range1`和`range2`是描述最小值和最大值的参数`number` 。如果`range1`小于`range2` ，则较大的数字会产生更亮的颜色，但如果`range2`小于`range` ，则较大的数字会产生更暗的颜色。如果`number`超出范围，则选择最浅或最深的阴影。
- 默认情况下， `scale-color`为较小的值生成较深的阴影，为较大的值生成较浅的阴影。但是，可以通过将最大值写为`range1`并将最小值写为`range2`来反转这一点，例如`scale-color lushness 50 100 0` 。我们在下面的模型示例中正是这样做的，用于每个格子的营养水平。


在下面的模型示例中，我们使用`scale-color`调整每个格子的颜色以反映其营养水平（1 表示最低，5 表示最高）。每次我们的农民移动到一个格子，它都会检测那个格子的营养水平。如果营养水平高于 3，农民会种植蔬菜。我们还根据其格子的营养水平使用`scale-color`颜色为蔬菜着色。获得更多营养的蔬菜具有更亮的绿色。
