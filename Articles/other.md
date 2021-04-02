*** Machine Translated
`other`报道的主体集合其是与输入主体集合但是省略了询问主体。换句话说，它会将自己从结果主体集合排除。例如：



```
show count turtles-here
=> 10
show count other turtles-here
=> 9  
```


显示了如何将一个主体（调用该命令的关键字海龟）从主体集合排除，从而最终计数为“9”。`other`时候，我们希望我们的主体与其他药物相互作用常常是有用的。例如，

`ask turtles [ if any? turtles-here [`

`set color red ] ]`

会使所有海龟变红，因为`turtles-here`返回了关键字的海龟。总是有至少1海龟当我们使用`turtles-here` 。但是，如果我们写

`ask turtles [if any? other turtles-here [`

`set color red ] ]`

只有在同一格子上有另一只海龟的海龟才会变成红色。