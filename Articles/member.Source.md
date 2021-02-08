﻿`Member?` can be used with **lists** or **agentsets**, but is more commonly used with lists. `Member?` reports **True** if the given value or agent appears in the given list or agentset, and takes the form:



```member? value list or member? agent agentset```



For example, `show member? 5 [ 3 4 5 6 ]` would report **True**, and `show member? 5 [1 3 2 ]` would report **False**; `show member? turtle 0 turtle` would report **True**, while `show member? patch 0 turtles` would report **False**. 



In the model below, there is an exclusive club which you can only enter if you are on the Memeber's List. When a turtle approaches the club, only if `member? self members-list` returns true can they enter. 