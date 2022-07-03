<!--
 * @Author: Ada J
 * @Date: 2022-07-03 14:25:05
 * @LastEditTime: 2022-07-03 15:22:38
 * @Description: 
-->
# Day 27 - VSpaceCode

`cmd + ;` -> show VSpaceCode operations

**init**
[setting](https://github.com/VSpaceCode/VSpaceCode/blob/master/src/configuration/settings.jsonc)
[keybindings](https://github.com/VSpaceCode/VSpaceCode/blob/master/src/configuration/keybindings.jsonc)

**override/create**
```json
  "vspacecode.bindingOverrides": [
    {
      "keys": "g",
      "name": "go...",
      "type": "bindings",
      "bindings": [
        {
          "key": "g",
          "name": "go to",
          "type": "command",
          "command": "workbench.action.gotoLine"
        }
      ]   
    }
  ]
```

**custom**

```json
  "vspacecode.bindings": [
    {
      "key": "g",
      "name": "go...",
      "type": "bindings",
      "bindings": [
        {
          "key": "g",
          "name": "go to",
          "type": "command",
          "command": "workbench.action.gotoLine"
        }
      ]   
    }
  ]
```
