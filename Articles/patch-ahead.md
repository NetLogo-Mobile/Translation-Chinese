*** Machine Translated
`patch-ahead`返回了单个格子，它是该海龟*之前*给定的距离。您可以将其想象为海龟看着它前面的一块格子。`patch-ahead`的语法是

`patch-ahead distance`

该距离可以是整数或十进制数，它是`patch-ahead`的格子要返回的修补`patch-ahead`距离。例如，要将格子3单位变成海龟绿色，我们会说：



```
ask patch-ahead 4 [ set pcolor green ] 
```


**注意**：如果格子不存在（即格子不在NetLogo的给定坐标范围内），返回指令将不返回`nobody` 。在下面的模型中，我们希望汽车仅在灰色区域行驶，而不在红色区域行驶。因此，我们使用`patch-ahead`使车停住，如果格子提前为红色。