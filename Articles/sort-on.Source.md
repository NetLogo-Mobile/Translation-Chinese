﻿`sort-on` allows you to sort the agents in an agentset. The agents are sorted based on some user-chosen agent variable or  an arbitrary reporter. Its syntax is:



``` sort-on [ variable-or-reporter ] agentset ```



For example, if you wanted to get a list of turtles sorted by their `xcor`, you could use `sort-on [xcor] turtles`, or if you wanted to get a list of patches sorted by the value of their patch variable `"pollution"`, you could use `sort-on [pollution] patches`.

Note that while in the prior examples the reporter was just a simple variable in square braces, it can include more advanced reporters. For example, say we wanted to sort turtles based on how close their x-coordinate was to 0, we could use `sort on [abs xcor] turtles` which would get the absolute value of the xcor before passing into the sorting algorithm. 

Note that the output of `sort-on` is always a newly created list -- it does not modify the original list at all. It also, like `sort` sorts in ascending order, so if you want the results in descending order, you can pass the output into `reverse`. 