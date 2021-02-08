*** Machine Translated
`Nobody`是一个特殊值，用于表示您要查找的主体不存在。当海龟死亡时，它等于`nobody` 。`Nobody`经常被用来检查是否有处于主体集合的主体，以避免错误。例如，您可以包含

```
if one-of turtles with [color = red] != nobody [ 
   ask turtles with [color = red ] forward 1 ]
```
，以便在没有任何红色海龟的情况下防止出现错误。

重要的是要注意，空的主体集合不等于`nobody` 。`nobody`寻找单主体时，通常是在的上下文仅用于`turtle` ，`one-of` ，或`max-one-of` 。