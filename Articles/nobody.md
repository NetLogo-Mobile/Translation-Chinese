*** Machine Translated
`nobody`是用于检查主体是否实际存在的特殊原语。另外，在海龟死亡的时候，也`nobody` 。例如，如果我们想创造一个每个海龟形成于相邻的格子与另一海龟链的模型，我们会写下面的代码：


    ask turtles [
    let my-potential-friend one-of turtles-on neighbors
    if my-potential-friend != nobody [
    create-link-with my-potential-friend
    ]
    ]


不使用`nobody`时要记住的事情

- `nobody`只和一个主体。如果需要检查主体集合是否为空，则需要使用`any?`原始的， `if any? turtles with [color = green]` 。
- 您可以将变量的值分配为`nobody`例如： `set my-friend nobody` 。这适用于使用`globals`原语创建的`globals`和使用`turtles-own` ， `patches-own`或`links-own`变量创建的代理变量。


在下面的模型示例中，我们在中间有一个篝火，有10个帐篷和10个营员。单击“开始”按钮后，每个露营者都会随机移动。只要将座席的`my-tent`变量设置为`nobody` ，他们就会继续移动。换句话说，露营者随机要求帐篷。