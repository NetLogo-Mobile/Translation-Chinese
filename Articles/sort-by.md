`sort-by`允许我们对列表或主体集合进行排序。 `sort-by`最适合在您对列表进行排序的特定情况下使用，并且您需要非常具体地控制该列表中元素的排序方式。作为如何使用`sort-by`的示例，请考虑根据长度对字符串列表进行排序的示例：



```
to-report smaller-length [a b]
  report (length a) < (length b)
end

show sort-by smaller-length ["xyz", "abcd" "12345"]
=> ["xyz" "abcd" "1234"]
```


确切的语法是`sort-by <reporter> <list>` ，所以在上面的例子中， `smaller-length`是报告指令。对于要通过`sort-by`使用的报告指令`sort-by`它必须 (1) 接受两个输入和 (2)返回`true`或`false`。给定两个输入`A`和`B` ，如果报告指令返回`true` ，则`A`放在`B`之前，如果返回`falze` ，则`B`放在`A`之前。或者，更直观地说，在排序后的输出列表从左到右看，报告指令对于每对数字都会返回`true`。即在列表`["xyz" "abcd" "1234"]` ，"xyz"的长度 &lt; "abcd"的长度，"abcd"的长度 &lt; "1234"的长度。

使用`sort-by`时要记住的事情：

- `sort-by`将始终按升序排序，因此如果您希望结果按降序排列，则可以对输出进行`reverse`，例如`reverse sort-by [size] smaller-length ["xyz", "abcd" "12345"]` 。
- `sort-by`的输出总是一个列表，即使输入是一个主体集合。在对主体集合进行排序时，顺序会随机。但是，在对列表进行排序时，排序是“稳定的”，这意味着如果两个“相等”的元素在输入列表中按特定顺序排列，则它们在排序列表中将保持该顺序。
- 尽管`sort-by`对主体集合和列表都有效，但您总是会使用`sort-on`因为使用它来对主体集合进行排序要方便得多。
