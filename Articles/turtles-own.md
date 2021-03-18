*** Machine Translated
`Turtles-own`定义属于模型中所有海龟的变量。变量通常是海龟特有的特征或方面，例如*饥饿吗？*或*能量*。它的语法是：

`turtles-own [ variable1 variable2 ... ]`

像全局变量和其他主体变量一样，它必须在任何过程定义之前的代码顶部定义。您可以定义一个或多个变量，但是它们必须全部在方括号内。

如果您定义了多个海龟品种，则拥有`turtles-own`会将变量应用于所有品种。但是，您可以使用`<breed>-own`为特定种类定义变量，其中<breed>是你的种类的名字。例如，如果您已经通过定义龟的种类<code>breed [birds bird]</code> ，您可以通过创建只小鸟变<code>birds-own [wing-size]</code> 。</breed>

在以下模型中，汽车行驶时的油箱中存有一定量的汽油。我们使用`turtles-own`定义变量`gas` ，该变量代表汽车拥有多少汽油。之后，我们使用`gas`变量来确定汽车是否可以继续行驶。