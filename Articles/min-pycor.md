*** Machine Translated
`Max-pxcor`和`max-pycor`返回格子的最大x坐标和最大y坐标。面片的最大x和y坐标也决定了模型的大小，并且必须始终大于或等于零。不能在代码中更改`max-pycor` `Max-pxcor`和`max-pycor` ；只能通过编辑视图来更改世界的大小。

类似地，`min-pxcor`和`min-pycor`返回格子的最小x坐标和最小y坐标。最小x和y坐标必须小于或等于零。例如，`ask patches with [pxcor = min-pxcor or pycor = min-pycor] [ set pcolor blue ]`的格子`ask patches with [pxcor = min-pxcor or pycor = min-pycor] [ set pcolor blue ]`会将沿着模型底部和左侧的格子设置为蓝色。

注意：就像海龟如何使用`color`以及格子如何使用`pcolor` ，区分仅由海龟使用的`xcor`和`ycor`以及仅由格子使用的`pxcor`和`pycor` 。