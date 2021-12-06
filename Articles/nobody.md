*** Machine Translated
`nobody`是一个特殊的关键字，我们用它来检查主体是否确实存在。此外，当海龟死了，它也变成了`nobody` 。例如，如果我们想创造一个每个海龟形成于相邻的格子与其它海龟链接的模型，我们会写下面的代码：


    ask turtles [
    let my-potential-friend one-of turtles-on neighbors
    if my-potential-friend != nobody [
    create-link-with my-potential-friend
    ]
    ]


使用`nobody`

- `nobody`仅与单个主体。如果我们需要检查一个主体集合是否为空，我们需要使用`any?`原始的， `if any? turtles with [color = green]` 。
- 您可以将变量的值分配为`nobody`例如： `set my-friend nobody` 。这适用于使用`globals`关键字创建的`globals`和使用`turtles-own` 、 `patches-own`或`links-own`变量创建的主体变量。


在下面的模型示例中，我们在中间有一个篝火、10 个帐篷和 10 个露营者。当点击 go 按钮时，每个露营者都会随机移动。只要主体的`my-tent`变量设置为`nobody` ，他们就会继续四处走动。换句话说，露营者随机索取帐篷。