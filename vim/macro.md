<!--
 * @Author: Ada J
 * @Date: 2022-06-21 22:44:01
 * @LastEditTime: 2022-06-21 23:17:20
 * @Description: 
-->
# Day 17 - macro in vim

**record**
* `qa` -> start recording(a is the name of register, you can use any letter instead)
* `q`-> stop recording
* `:reg a` -> view a macro

**call**
* `@a` -> call a macro
* `@@` -> call the last macro
* `number + @a` -> repeat calling

**modify**
* `qA` -> add something to the end

**edit a existing macro**
* `:put a` (take it out) -> `do some changes` (modify) -> `"ayy/"ayw` (put it away) 


