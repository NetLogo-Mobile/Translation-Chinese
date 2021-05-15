*** Machine Translated
`Member?`可以与**列表**或**主体集**一起使用，但更常见于列表。`Member?`如果给定值或主体出现在给定列表或主体集合，则返回**True** ，并采用以下形式：

`member? value list or member? agent agentset`

例如，`show member? 5 [ 3 4 5 6 ]`将返回**True** ，并`show member? 5 [1 3 2 ]`将返回**False** ； `show member? turtle 0 turtle`会返回**True** ，而`show member? patch 0 turtles`会返回**False** 。

在下面的模型中，有一个专属俱乐部，只有在您进入会员名单时，您才能进入。当海龟接近俱乐部时，只有`member? self members-list`才能`member? self members-list`返回true即可进入。