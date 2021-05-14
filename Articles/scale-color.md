*** Machine Translated
`scale-color`是一个基本元素，它报告与给定数字的值成比例的颜色阴影。例如，如果我们要创建一个交通模型，在该模型中，装满油箱的汽车要比装满油箱的汽车更亮，我们可以编写以下代码：



```
ask cars [
	set color scale-color white tank-level 0 100
]
```


或者，如果我们要模拟一群绵羊的草丛，其中茂密的草丛比已经被吃掉的草丛还要亮，我们可以编写以下代码：



```
ask patches [
	set pcolor scale-color green lushness 0 100
]
```


使用`scale-color`时要记住的事情：

- `scale-color`的语法可能很难记住。如下`scale-color base_color exact_point lowest_value highest_value` 。
- 您可以将*base\_color*值视为所提供范围内的中间点。例如，如果我们将`scale-color green 50 0 100`写`scale-color green 50 0 100` ，则将获得完全绿色。
- 别忘了首先要输入所需的基色，然后是确切的值， `number`是您要缩放的值（通常是海龟或格子变量），而`range1`和`range2`是用于描述以下项的最小值和最大值的参数： `number` 。如果`range1`小于`range2` ，则较大的数字将导致较亮的颜色，但是如果`range2`小于`range` ，则较大的数字将导致较暗的颜色。如果`number`超出范围，则选择最亮或最暗的阴影。
- 默认情况下， `scale-color`对于较小的值将生成较深的阴影，对于较大的值将生成较暗的浅色。但是，可以通过将最大值记为`range1` ，将最小值记为`range2`例如`scale-color lushness 50 100 0`来扭转这种情况。我们在下面的示例示例中正是针对每个格子的营养水平进行了此操作。


在下面的模型示例中，我们使用`scale-color`调整每个格子的颜色以反映其营养水平（1为最低，5为最高）。每当我们的农民搬到一块格子，它都会检查那里的营养水平。如果营养水平高于3，则农民种蔬菜。我们还根据蔬菜格子的营养水平，使用`scale-color`色为蔬菜`scale-color` 。营养丰富的蔬菜具有较亮的绿色。