*** Machine Translated
`Max-n-of`返回一个座席集，该主体集合包含**指定数量的座席**，并**具有给定返回指令**的**最高价值**。它采取以下形式：

`max-n-of number agentset [ reporter ]`

例如，`max-n-of 3 patches [ count turtles-here ]`将返回三个海龟数量最多的格子的主体集合集。如果给定的主体集合的海龟数量少于指定的数量，则`max-n-of`将返回整个主体集合。例如，如果我们的模型中只有5只海龟，并且运行`max-n-of 10 turtles [ size ]` ，则将全部5只海龟退回。领带随机断裂。

在下面的模型中，细胞正在生长和分裂。每隔十分周期，我们要求最大的三个像元使用`max-n-of`进行除法。