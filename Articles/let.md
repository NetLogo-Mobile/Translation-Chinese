*** Machine Translated
`Let`用于创建新的**局部变量**并设置其值。**局部变量**是只存在于括号内的可变`[...]`它在创建或过程，不像一个全局变量。它只能在声明*后*的代码中使用，其形式为：

`let variable-name initial-value`

例如，要创建一个新的局部变量`my-blue-friends`并将其值设置为所有蓝色的人形海龟，我们会说：


    let my-blue-friends turtles with [ color = blue and shape = “person” ]
    ask my-blue-friends [ forward 1 ]


然后，让`my-blue-friends`前进，将所有蓝色人形的海龟向前移动。要在创建变量后更改其值，请使用`set` 。