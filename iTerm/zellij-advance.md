<!--
 * @Author: Ada J
 * @Date: 2022-07-19 22:11:46
 * @LastEditTime: 2022-07-19 22:52:00
 * @Description: 
-->
# Day 40 - zellij advanced operations

**session**
* `ctrl+o d` -> create session with a random name
* `zj attach -c "session name"` -> create and name a session 
* `zj a "session name"` -> use session
* `zj ls` -> check session list
* `zj k "session name"` -> kill session
* `zj ka` -> kill all session

**sync**
**scroll**
**clear**

**change the config if you need** 
* create the config file
```bash
mkdir ~/.conﬁg/zellij 
zellij setup --dump-conﬁg > ~/.conﬁg/zellij/conﬁg.yaml
```
* edit config.yaml

[docs: keybindings-keys](https://zellij.dev/documentation/keybindings-keys.html)