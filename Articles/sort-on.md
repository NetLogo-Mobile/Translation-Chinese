*** Machine Translated
`sort-on`允许您对主体集合的主体进行排序。主体根据某些用户选择的主体变量或任意返回指令进行排序。其语法为：

`sort-on [ variable-or-reporter ] agentset`

例如，如果要获取按`xcor`排序的海龟列表，则可以使用`sort-on [xcor] turtles` ，或者如果要获取按其格子变量`"pollution"`的值排序的格子列表，您可以使用`sort-on [pollution] patches` 。

请注意，尽管在先前的示例中，返回指令只是方括号中的一个简单变量，但它可以包含更高级的返回程序。例如，假设我们要根据海龟的x坐标与0的接近程度对海龟进行排序，我们可以`sort on [abs xcor] turtles`使用`sort on [abs xcor] turtles`这将在传递到排序算法之前获得xcor的绝对值。

请注意，`sort-on`的输出始终是一个新创建的列表-它根本不会修改原始列表。它也像`sort`按升序排序，所以如果你想按降序排列的结果，你可以通过输出到`reverse` 。