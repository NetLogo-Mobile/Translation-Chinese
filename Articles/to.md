*** Machine Translated
`To`用于开始命令过程。您可以将`to`作为一种为NetLogo定义一组动作/动词的方式，例如`to go` ，`to add-money`等。您可以在代码中的任何位置使用这些过程。**注意**：您必须将`end`在该过程的结束，以便为它工作。也可以通过按钮调用程序！例如，使用`go`按钮（位于“接口”选项卡上）可以运行创建的过程，以...结束。让我们看看实际情况。

```
to setup
clear-all
create-turtles 100
end
```
 `Setup`是过程名称。`Clear-all`和`create-turtles 100`是此过程中的命令。`end`告诉NetLogo该过程已完成。当将此用作按钮时，所有这些都立即发生。

此关键字的另一个目的是将代码分成较小的部分。例如：

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
fd 1
end
```
看看在第一段代码中，您是如何调用海龟*摆动*然后*移动的*。然后**将** **摆动**和**移动**作为命令过程编写。最终为您节省了很多空间和重复时间！