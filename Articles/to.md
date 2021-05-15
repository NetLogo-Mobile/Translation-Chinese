*** Machine Translated
`to`用于开始命令过程。您可以将`to`作为一种定义NetLogo动作/动词的方法，例如`to go` ， `to add-money` ， `to move`等。我们可以在代码中的任何位置使用这些过程。

每个以`to`开头的过程`to`必须始终以`end`原语来完成，以使其起作用。也可以通过按钮调用程序！例如，使用`go`按钮（位于“接口”选项卡上）运行在代码选项卡中创建为`go ... end`的过程。让我们看看实际情况：



```
to go
	ask turtles [
		wiggle
		forward 1
	]
	tick
end
```


`to`原语的另一个目的是允许我们将代码分成较小的部分。例如：



```
ask turtles [
  wiggle  ;; first turn a little bit
  move    ;; then step forward
]

to wiggle
  rt random 90
  lt random 90
end

to move
	forward speed 
end
```


在第一段代码中，您如何调用乌龟*摆动*，然后*移动*。然后**将** **摆动**和**移动**作为命令过程编写。最终为您节省了很多空间和重复时间！

在下面的模型示例中，我们有一个非常简单的模型，其中包含三个按钮。单击`setup`按钮后，由NetLogo运行在代码中`to setup`创建的*设置*过程，该过程使我们的补丁`to setup`绿色，并在模型的随机位置上创建了一些蝴蝶。单击“ `move`按钮后，由NetLogo运行`to move`创建代码的*移动*过程，该*移动*过程使蝶形在随机方向上向前移动1步。单击“ `grow`按钮时，由NetLogo运行我们`to grow`在代码中`to grow`的*g*行过程，这使蝶形变大了一点。