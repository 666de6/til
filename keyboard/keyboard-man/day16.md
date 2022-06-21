<!--
 * @Author: Ada J
 * @Date: 2022-06-19 17:54:01
 * @LastEditTime: 2022-06-21 11:01:53
 * @Description: delete a function 
-->
# Day 16
## delete a function
* `%` -> match brackets( () or {} or [])

**vim-indent-object**
* `operation + ii` -> within function
* `operation + ai` -> the whole function(such as python)
* `operation + aI` -> the whole function(javascript)

* *tips: "ai" => "aI" in setting.json*

**delete a function**
* `dap` -> functions which doesn't have any blanks
* `dai` -> you have to operate within functions
* `v$%d` -> change setting to `leader + d + f` 
