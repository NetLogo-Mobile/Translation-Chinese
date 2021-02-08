*** Machine Translated
尽管`self`和`myself`听起来很相似，但是它们用在不同的情况下，一定不要混淆。`Myself`时使用的主体需要参照本身而试图解决内的不同的主体或主体集合 `ask`命令或返回指令（例如，与）。例如，如果您希望仅当一个人拥有正确的键码时才打开房门，那么您可以在`myself`指的是**人1的**地方写上

```
ask person 1 [ 
    ask houses [ 
        if keycode = [keycode] of myself [ open-front-door ] ] ]
```
。`Myself`经常与`of`一起使用以返回或设置询问主体的变量（ `ask turtles with [pcolor = [pcolor] of myself]` `ask turtles with [size < [size] of myself ]`或`ask turtles with [size < [size] of myself ]` ）。有关更多**示例**，请参见模型库中的**我自己的**示例。

当有一个单独的`ask`命令，并且海龟，链或格子试图引用自己时，使用`Self` 。例如，

```
let my-turtle nobody 
create-turtles 1 [ set shape “turtle” set my-turtle self] 
ask my-turtle [ forward 2]
```
会将变量`my-turtle`设置为新创建的海龟。它很少使用，因为`[color] of self`等同于说`color` 。

在下面的模型中，`if color = [ color ] of myself [ stay home ]` ，我们使用`myself`使人们只能进入他们相同颜色的房子。