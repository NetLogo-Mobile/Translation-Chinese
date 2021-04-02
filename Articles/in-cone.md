*** Machine Translated
`in-cone`是使我们模拟海龟前面的“视觉圆锥体”的关键字格子。它使我们可以对在他们前面有某种视觉或其他感觉，但在他们后面或侧面没有某种视觉或其他感觉的主体进行建模。

视锥由两个输入构成：主体可以看到多远（*半径*）和主体可以看到多宽（ *0到360之间的度*）。例如，如果我们希望某些兔子在前面有胡萝卜但不在后面或侧面有胡萝卜，则可以编写以下代码：



```
ask rabbits [
  if any? carrots in-cone 3 45 [ eat ]
]
```


使用`in-cone`时要记住的事情：

- 您还可以将浮点值用于半径和角度参数，例如`in-cone 1.25 66.66` 。
- *海龟*和*斑块*都可以使用`in-cone` 。
- 请记住，如果您使用的是同一个品种， `in-cone`也可能返回关键字海龟。确保使用`other`关键字在模型中考虑到这一点。例如，此代码将引发错误， `ask turtles [ create-links-with turtles in-cone 2 30 ]` ，而此代码可以正常工作， `ask turtles [ create-links-with other turtles in-cone 2 30 ]` 。
- 您可以结合使用`in-cone`和`with`关键字来缩小目标代理的范围，但请确保将第一个`with`语句封装在parantheses `( )` 。例如，您可以编写类似的代码`if any? (carrots with [color = orange]) in-cone 3 45 [ eat ]` 。


在下面的模型示例中，我们使用`in-cone`仿真四个运动激活的野生动物相机。当相机检测到有东西`any? animals in-cone 8 50` ，它会变成黄色以模拟拍照。 （请注意，突出显示的格子只是为了更好地从视觉上显示视锥。实际上， `in-cone`海龟检测与海龟站立的格子都不相关。）