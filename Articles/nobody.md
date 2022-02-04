`nobody`是一个特殊的关键字，我们用它来检查主体是否存在。此外，当海龟死了，它也会变成`nobody` 。例如，如果我们想创造一个每个海龟与其相邻的格子上的其它海龟建立链接的模型，我们会写下面的代码：

```
    ask turtles [
    let my-potential-friend one-of turtles-on neighbors
    if my-potential-friend != nobody [
    create-link-with my-potential-friend
    ]
    ]
```

使用`nobody`需要注意的事情：

- `nobody`仅针对单个主体。如果我们需要检查一个主体集合是否为空，我们需要使用`any?`关键字， `if any? turtles with [color = green]` 。
- 您可以将变量的值设置为`nobody`例如： `set my-friend nobody` 。这适用于使用`globals`关键字创建的全局变量和使用`turtles-own` 、 `patches-own`或`links-own`创建的主体变量。


在下面的模型示例中，我们在中间有一个篝火、10 个帐篷和 10 个露营者。当点击 go 按钮时，每个露营者都会随机移动。只要主体的`my-tent`变量设置为`nobody` ，他们就会继续四处走动。换句话说，露营者会随机索取帐篷。
