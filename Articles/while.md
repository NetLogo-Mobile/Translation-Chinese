*** Machine Translated
`While`开始执行一个**命令块的**循环，只要给定的**返回指令**程序返回**True即可**。如果返回指令返回**False** ，则退出循环。它采用以下形式：

`while [ reporter ] [ commands ]`

例如，要使海龟0继续前进直到遇到上面没有其他海龟的格子，我们可以这样说： 

```
ask turtle 0 [ 
    while [ any? Other turtles-here ] [ 
    	forward 1] ]
```


注意：在NetLogo模型中，不经常使用while循环和其他循环。在下面的模型中，我们使用`while`循环使海龟绘制正方形。