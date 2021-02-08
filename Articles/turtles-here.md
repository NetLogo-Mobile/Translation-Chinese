*** Machine Translated
`Turtles-here`返回呼叫方格子上所有海龟的**主体集合** ，如果呼叫方是海龟，则返回自身。例如，

```
create-turtles 3 
ask turtles [ show count turtles-here ]
```
将返回`3` 。您也可以使用`<breed>-here`指定种类。如果模型中同时有`ask cats [ if any? mice-here [ chase ] ]` ，`ask cats [ if any? mice-here [ chase ] ]`在相同的格子上，猫就会追逐老鼠。

在下面的模型中，一些青蛙在池塘中四处移动。如果青蛙跳到一块Lilypad（绿色格子）上，它的重量会将Lilypad推入水中，使其变成蓝色。我们使用`turtles-here`检查在lilypad上是否有青蛙。