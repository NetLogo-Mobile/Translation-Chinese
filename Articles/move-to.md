*** Machine Translated
`move-to`允许海龟将其x和y坐标设置为与另一只海龟或格子相同，而无需更改海龟的其他变量（例如，方向，颜色，大小）。其语法为：

`move-to desired-agent`

例如，如果我们想让每只兔子移动到随机挑选的绿色格子的确切位置，我们会说： 

```
ask rabbits [
	move-to one-of patches with [pcolor = green]
	eat-grass
]
```
**请注意**，如果目标海龟或格子不存在，则模型将给出错误。在下面的模型中，有一个家庭和他们的房子。我们希望一家人在他们的房子里，并使用`move-to`到将他们搬到那里。