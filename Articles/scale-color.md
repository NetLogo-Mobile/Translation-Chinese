*** Machine Translated
`scale-color`是一个关键字`scale-color` ，它返回与给定数字的值成比例的颜色阴影。例如，在交通模型中，可能使用`scale-color`为满油箱比在空油箱中加油的汽车`scale-color` ，或者在成群的绵羊模型中，为更多茂盛的草块着色比已经吃过的更明亮。

实际上，您可以这样使用`scale-color` ：

`scale-color color number range1 range2`

其中`color`是所需的基本色相（红色，蓝色，绿色等），`number`是您希望缩放的值（通常是海龟或格子变量），`range1`和`range2`是用于描述的最小和最大值的参数`number` 。如果`range1`小于`range2` ，则较大的数字将导致较亮的颜色，但是如果`range2`小于`range` ，则较大的数字将导致较暗的颜色。如果`number`超出范围，则选择最亮或最暗的阴影。

在此模型中，使用`scale-color`来模拟塔信号强度。距离信号塔更近的贴片具有更好的信号强度，因此其颜色比距离信号塔太远而无法获得任何信号的贴片更亮。