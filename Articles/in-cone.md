*** Machine Translated
`in-cone`是一个关键字，可以帮助我们在海龟面前模拟“视锥”。它允许我们模拟一个在他们前面有一些视觉或其他感觉的主体，但没有在他们后面或旁边。

锥体由两个输入构成：主体可以看到多远（*半径*），以及主体可以看到多宽（ *0 到 360 之间的度数*）。例如，如果我们想让一些兔子吃前面有胡萝卜而不是后面或旁边的胡萝卜，我们可以编写以下代码：



```
ask rabbits [
  if any? carrots in-cone 3 45 [ eat ]
]
```


使用`in-cone`时要记住的事情：

- 您还可以对半径和角度参数使用浮点值，例如`in-cone 1.25 66.66` 。
- *海龟*和*补丁*都可以使用`in-cone` 。
- 请记住，如果您使用相同的品种， `in-cone`也可能返回来源海龟。请务必使用`other`关键字在您的模型中考虑到这一点。例如，这段代码会抛出一个错误`ask turtles [ create-links-with turtles in-cone 2 30 ]` ，而这个代码可以很好地执行`ask turtles [ create-links-with other turtles in-cone 2 30 ]` 。
- 您可以结合`in-cone`和`with`关键字来缩小目标主体的范围，但请确保将第一个`with`语句封装在括号`( )` 。例如，你可以写一个代码， `if any? (carrots with [color = orange]) in-cone 3 45 [ eat ]` 。


在下面的模型示例中，我们使用`in-cone`来模拟四个运动激活的野生动物摄像机。当相机检测到有`any? animals in-cone 8 50` ，它会变成黄色以模拟拍照。 （请注意，突出显示的补丁只是为了更好地直观地显示视锥。实际上， `in-cone`海龟检测与海龟站在哪个格子上没有任何关系。）