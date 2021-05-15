*** Machine Translated
`sort-by`允许我们使用用户定义的比较来对列表或代理集进行排序。在要对列表进行排序的特定情况下，最好使用`sort-by` ，并且需要对列表中元素的排序方式进行非常具体的控制。作为如何使用`sort-by`的示例，请考虑根据字符串的长度对字符串列表进行排序的示例：



```
to-report smaller-length [a b]
  report (length a) < (length b)
end

show sort-by smaller-length ["xyz", "abcd" "12345"]
=> ["xyz" "abcd" "1234"]
```


确切的语法是`sort-by <reporter> <list>` ，因此在上面的示例中， `smaller-length`是报告指令。对于`sort-by`方式使用的报告指令，必须（1）接受两个输入，并且（2）返回是或否。给定两个输入`A`和`B` ，如果报告指令报告为true，则将`A`放置在`B`之前，如果报告为false，则将`B`放置在`A`之前。或者，更直观地说，在排序后的输出列表从左到右工作，对于每对数字，报告指令都是正确的。也就是说，在列表`["xyz" "abcd" "1234"]` ，长度“ xyz” &lt;长度“ abcd”，长度“ abcd” &lt;“ 1234”。

使用`sort-by`时要记住的事情：

- `sort-by`始终会以升序排序，因此，如果您希望结果以降序排列，则可以将输出传递给`reverse`例如`reverse sort-by [size] smaller-length ["xyz", "abcd" "12345"]` 。
- 即使输入是主体集合 ，要进行`sort-by`的输出也始终是一个列表。在对业务代表集进行排序时，关系是随机断开的。但是，在对列表进行排序时，排序是“稳定的”，这意味着，如果两个“相等”元素在输入列表中处于特定顺序，则它们将在该排序列表保持该顺序。
- 尽管`sort-by`确实适用于代理集和列表，但是您几乎总是要使用`sort-on`因为排序代理集非常容易使用。